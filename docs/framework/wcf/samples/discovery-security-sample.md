---
title: "探索安全性範例 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8db01f4-b4a1-43fe-8e31-26d4e9304a65
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# 探索安全性範例
探索規格不會要求參與探索程序的端點是安全的。  增強探索訊息的安全性會減少各種攻擊 \(訊息變更、阻斷服務、重新執行、詐騙\)。  此範例使用精簡簽章格式 \(如 WS\-Discovery 規格的第 8.2 節所述\) 實作計算與驗證訊息簽章的自訂通道。  此範例同時支援 [2005 探索規格](http://go.microsoft.com/fwlink/?LinkId=177912)與 [1.1 版](http://go.microsoft.com/fwlink/?LinkId=179677)。  
  
 自訂通道會針對探索和公告端點，套用到現有通道堆疊的頂端。  如此一來，每個傳送的訊息都會套用簽章標頭。  系統會驗證收到之訊息上的簽章，而且當該簽章不符或訊息沒有簽章時，就會捨棄訊息。  為簽署與驗證訊息，此範例使用憑證。  
  
## 討論  
 WCF 可以延伸，而且可讓使用自訂所需的通道。  此範例會實作可建立安全通道的探索安全繫結項目。  安全通道會套用並驗證訊息簽章，而且會套用到目前堆疊的頂端。  
  
 安全繫結項目會建立安全通道處理站與通道接聽項。  
  
## 安全通道處理站  
 安全通道處理站會建立將精簡簽章加入至訊息標頭的輸出或雙工通道。  為了讓訊息保持越小越好，請使用精簡簽章格式。  精簡簽章的結構顯示在下列範例中。  
  
```  
<d:Security ... >   
  [<d:Sig Scheme="xs:anyURI"   
         [KeyId="xs:base64Binary"]?  
          Refs="..."  
         [PrefixList]=”xs:NMTOKENS”   
          Sig="xs:base64Binary"   
          ... />]?  
  ...   
</d:Security>  
  
```  
  
> [!NOTE]
>  `PrefixList` 會在 2008 探索版本通訊協定中加入。  
  
 為計算簽章，此範例決定展開的簽章項目。  XML 簽章 \(`SignedInfo`\) 會使用 WS\-Discovery 規格所要求的 `ds` 命名空間前置詞建立。  探索與定址命名空間中的本文和所有標頭都會在簽章中參考，因此無法進行竄改。  每個參考的項目都會使用「獨佔標準化」\(http:\/\/www.w3.org\/2001\/10\/xml\-exc\-c14n\#\) 轉換，然後計算 SHA\-1 摘要值 \(http:\/\/www.w3.org\/2000\/09\/xmldsig\#sha1\)。  根據所有參考的項目及其摘要值，系統會使用 RSA 演算法 \(http:\/\/www.w3.org\/2000\/09\/xmldsig\#rsa\-sha1\) 計算簽章值。  
  
 訊息會使用用戶端指定的憑證簽署。  建立繫結項目時，必須指定存放位置、名稱和憑證主體名稱。  精簡簽章中的 `KeyId` 表示簽章權杖的金鑰識別碼，而且是簽署權杖的主體金鑰識別碼 \(SKI\)，或 \(如果 SKI 不存在\) 簽署權杖公開金鑰的 SHA\-1 雜湊。  
  
## 安全通道接聽項  
 安全通道接聽項會建立可驗證收到之訊息中精簡簽章的輸入或雙工通道。  為驗證簽章，系統會使用訊息內附加之精簡簽章中指定的 `KeyId` 來選取指定之存放區中的憑證。  如果訊息沒有簽章或簽章檢查失敗，就會捨棄訊息。  為使用安全繫結，此範例會使用加入的探索安全繫結項目，定義可建立自訂 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 和 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> 的處理站。  這些安全端點可用於探索公告接聽項和可搜尋的服務。  
  
## 範例詳細資料  
 此範例包含程式庫和 4 個主控台應用程式：  
  
-   **DiscoverySecurityChannels**：公開安全繫結的程式庫。  此程式庫會計算與驗證傳出\/傳入訊息的精簡簽章。  
  
-   **Service**：公開 ICalculatorService 合約的自我裝載服務。  此服務會標示為可搜尋。  使用者會透過指定存放位置和名稱、憑證的主體名稱或其他唯一識別碼，以及用戶端憑證所在的存放位置 \(用來檢查傳入訊息之簽章的憑證\)，指定簽署訊息所使用之憑證的詳細資料。  根據這些詳細資料，就會建立並使用具有額外安全性的 UdpDiscoveryEndpoint。  
  
-   **Client**：此類別會嘗試探索 ICalculatorService 並呼叫服務上的方法。  同樣地，系統會建立並使用具有額外安全性的 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 來簽署與驗證訊息。  
  
-   **AnnouncementListener**：自我裝載的服務，此服務會接聽線上與離線公告，並使用安全公告端點。  
  
> [!NOTE]
>  如果多次執行 Setup.bat，憑證管理員會因為有重複的憑證而提示您選擇要加入的憑證。  在該情況下，應該中止 Setup.bat 並呼叫 Cleanup.bat，因為已經產生重複。  Cleanup.bat 也會提示您選擇要刪除的憑證。  選取清單中的憑證並繼續執行 Cleanup.bat，直到沒有剩下任何憑證為止。  
  
#### 若要使用這個範例  
  
1.  從 Visual Studio 命令提示字元執行 Setup.bat 指令碼。  此範例會使用憑證來簽署與驗證訊息。  指令碼會使用 Makecert.exe 建立憑證，然後使用 Certmgr.exe 進行安裝。  此指令碼必須以系統管理員權限的身分來執行。  
  
2.  若要建立並執行範例，開啟 Visual Studio 中的 Security.sln 檔案，然後選擇 \[**全部重建**\]。  更新方案屬性以啟動多個專案：針對 DiscoverySecureChannels 之外的所有專案，選取 \[**啟動**\]。  按照一般方式執行方案。  
  
3.  完成此範例之後，請執行 Cleanup.bat 指令碼，以移除針對此範例建立的憑證。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。  請先檢查下列 \(預設\) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[適用於 .NET Framework 4 的 Windows Communication Foundation \(WCF\) 與 Windows Workflow Foundation \(WF\) 範例](http://go.microsoft.com/fwlink/?LinkId=150780)，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。  此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DiscoveryScenario`  
  
## 請參閱