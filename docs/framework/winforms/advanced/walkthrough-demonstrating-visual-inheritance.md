---
title: "逐步解說：示範視覺化繼承 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "表單繼承, 逐步解說"
  - "繼承, 逐步解說"
  - "視覺化繼承"
  - "逐步解說 [Windows Form], 視覺化繼承"
  - "Windows Form, 繼承"
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 逐步解說：示範視覺化繼承
視覺化繼承可讓您查看基底表單上的控制項，並加入新的控制項。  在本逐步解說中，您將建立基底表單，並編譯為類別庫。  您將匯入此類別庫至另一個專案，並建立繼承自基底表單的新表單。  在這個逐步解說期間，您將了解如何：  
  
-   建立包含基底表單的類別庫專案。  
  
-   加入屬性可由基底表單衍生類別修改的按鈕。  
  
-   加入無法由基底表單繼承者修改的按鈕。  
  
-   建立包含繼承自 `BaseForm` 表單的專案。  
  
 最後，本逐步解說將示範繼承的表單上私用和受保護控制項之間的差異。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 \[說明\] 中描述的不同。  若要變更設定，請從 \[**工具**\] 功能表中選取 \[**匯入和匯出設定**\]。  如需詳細資訊，請參閱 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/zh-tw/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
> [!CAUTION]
>  並非所有控制項都支援來自基底表單的視覺化繼承。  下列控制項並不支援在此逐步解說中所描述的案例：  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  繼承的表單中的這些控制項永遠唯讀，不論您使用的修飾詞為何 \(`private``protected` 或 `public`\)。  
  
## 案例步驟  
 第一個步驟是建立基底表單。  
  
#### 建立包含基底表單的類別庫專案：  
  
1.  從 \[檔案\] 功能表，選取 \[新增\]，然後選取 \[專案\]，以開啟 \[新增專案\]  對話方塊。  
  
2.  建立命名為 `BaseFormLibrary` 的 Windows Form 應用程式。  
  
3.  若要建立類別庫，而非標準的 Windows Form 應用程式，在 \[方案總管\] 以滑鼠右鍵按一下 \[BaseFormLibrary\]  專案節點，然後選取 \[屬性\] 。  
  
4.  在專案屬性中，將 \[輸出類型\] 從 \[Windows 應用程式\] 變更為 \[類別庫\]。  
  
5.  從 \[檔案\] 功能表上，選擇 \[全部儲存\] ，將專案和檔案儲存到預設位置。  
  
 下面兩個程序將按鈕加入至基底表單。  為了示範視覺化繼承，您將藉由設定 `Modifiers` 屬性，授與這些按鈕不同存取層級。  
  
#### 加入基底表單繼承者可以修改的按鈕：  
  
1.  在設計工具中，開啟 \[Form1\]。  
  
2.  在 \[工具箱\] 的 \[所有 Windows Form\]  索引標籤，按兩下 \[Button\]，將按鈕新增至表單。  使用滑鼠來定位並調整按鈕的大小。  
  
3.  在屬性視窗中設定下列按鈕屬性：  
  
    -   將 \[Text\] 屬性設定為 \[Say Hello\]。  
  
    -   將 \[\(Name\)\] 屬性設為 \[btnProtected\]。  
  
    -   將 \[Modifiers\] 屬性設為 \[Protected\]。  這可讓繼承自 \[Form1\]  的表單修改 \[btnProtected\] 的屬性。  
  
4.  按兩下 \[Say Hello\] 按鈕來加入 \[Click\]  事件的事件處理常式 。  
  
5.  將下列這行程式碼加入至事件處理常式：  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### 加入無法由基底表單繼承者修改的按鈕：  
  
1.  按一下程式碼編輯器上的 \[Form1.vb \[Design\], Form1.cs \[Design\], or Form1.jsl \[Design\]\] 索引標籤，或按 F7 鍵，以切換到設計檢視。  
  
2.  加入第二個按鈕，並設定其屬性，如下所示：  
  
    -   將 \[Text\] 屬性設定為 \[Say Goodbye\]。  
  
    -   將 \[\(Name\)\] 屬性設為 \[btnPrivate\]。  
  
    -   將 \[Modifiers\] 屬性設為 \[Private\]。  這可讓繼承自 \[Form1\]  的表單無法修改 \[btnPrivate\] 的屬性。  
  
3.  按兩下 \[Say Goodbye\] 按鈕來加入 \[Click\]  事件的事件處理常式 。  將下列這行程式碼放在事件程序：  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  從 \[建置\] 功能表上，選擇 \[建置 BaseForm 程式庫\]  以建置類別庫。  
  
     一旦建立程式庫之後，您可建立新專案，其繼承自剛建立的表單。  
  
#### 若要建立包含表單的專案，其表單繼承自基底表單  
  
1.  從 \[檔案\] 功能表，選取 \[新增\]，然後選取 \[新增專案\]，以開啟 \[加入新的專案\] 對話方塊。  
  
2.  建立命名為 `InheritanceTest` 的 Windows Form 應用程式。  
  
#### 若要加入繼承的表單  
  
1.  在 \[方案總管\] 中，以滑鼠右鍵按一下 \[InheritanceTest\]，選取 \[加入\]，然後選取 \[新增項目\]。  
  
2.  在 \[加入新項目\] 對話方塊中，選取 \[Windows Form\] 類別目錄 \(如果您有分類清單\)，然後選取 \[繼承的表單\] 範本。  
  
3.  保留預設名稱 `Form2`，然後按一下 \[加入\]。  
  
4.  在 \[繼承選取器\] 對話方塊中，從 \[BaseFormLibrary\]  專案選取 \[Form1\] 做為要繼承的表單，然後按一下 \[確定\]。  
  
     這會在 \[InheritanceTest\] 專案中建立表單，其為衍生自 \[BaseFormLibrary\] 的表單。  
  
5.  如果尚未開啟，請在設計工具中按兩下開啟繼承的表單 \(\[Form2\] \)。  
  
     在設計工具中，繼承的按鈕在其上方角落有符號 \(![VisualBasicInheritanceSymbol 螢幕擷取畫面](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\)，表示受到繼承。  
  
6.  選取 \[Say Hello\] 按鈕，並觀察調整大小控點。  因為此按鈕已受到保護，所以繼承者可以移動它、調整大小、變更標題和進行其他修改。  
  
7.  選取私用 \[Say Goodbye\] 按鈕，並注意它沒有調整大小控點。  此外，在 \[屬性\] 視窗中，這個按鈕的屬性會呈現灰色，表示無法修改它們。  
  
8.  如果您使用的是 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]：  
  
    1.  在 \[方案總管\] 中，以滑鼠右鍵按一下 \[InheritanceTest\] 專案中的 \[Form1\] ，然後選擇 \[刪除\]。  在出現的訊息方塊中，按一下 \[確定\] 以確認刪除。  
  
    2.  開啟 Program.cs 檔案並變更 `Application.Run(new Form1());` 為 `Application.Run(new Form2());`。  
  
9. 在 \[方案總管\] 中，以滑鼠右鍵按一下 \[InheritanceTest\] 專案，然後選取 \[設定為啟始專案\]。  
  
10. 在 \[方案總管\] 中，以滑鼠右鍵按一下 \[InheritanceTest\] 專案，然後選取 \[屬性\]。  
  
11. 在 **InheritanceTest** 屬性頁中，設定 \[啟始物件\]  為繼承的表單 \(\[Form2\]\)。  
  
12. 按 F5 執行應用程式，並觀察繼承的表單之行為。  
  
## 後續步驟  
 使用者控制項的繼承以非常類似的方式運作。  開啟一個新的類別庫專案，並加入使用者控制項。  將構成控制項放在上面，然後編譯專案。  開啟另一個新的類別庫專案，並加入已編譯類別程式庫的參考。  此外，請嘗試加入繼承的控制項至專案 \(透過 \[加入新項目\] 對話方塊\)，並嘗試使用 \[繼承選取器\]。  加入一個使用者控制項，並變更 `Inherits` 陳述式 \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 中的 `:`\)。  如需詳細資訊，請參閱[如何：繼承 Windows Form](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)。  
  
## 請參閱  
 [如何：繼承 Windows Form](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Windows Form 視覺繼承](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Windows Form](../../../../docs/framework/winforms/index.md)