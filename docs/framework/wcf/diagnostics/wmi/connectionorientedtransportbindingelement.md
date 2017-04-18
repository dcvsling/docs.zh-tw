---
title: "ConnectionOrientedTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## 語法  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## 方法  
 ConnectionOrientedTransportBindingElement 類別不會定義任何方法。  
  
## 屬性  
 ConnectionOrientedTransportBindingElement 類別有下列屬性：  
  
### ChannelInitializationTimeout  
 資料型別：日期時間  
  
 存取類型：唯讀  
  
 指定在逾時之前必須完成通道初始化的時間範圍。  
  
### ConnectionBufferSize  
 資料型別：sint32  
  
 存取類型：唯讀  
  
 用於從用戶端或服務在網路上傳輸已序列化訊息之區塊的緩衝區大小。  
  
### HostNameComparisonMode  
 資料型別：字串  
  
 存取類型：唯讀  
  
 代表主機名稱是否用於連線到服務的值 \(當符合 URI 時\)。  
  
### MaxBufferSize  
 資料型別：sint32  
  
 存取類型：唯讀  
  
 要使用之緩衝區的大小上限。  
  
### MaxOutputDelay  
 資料型別：日期時間  
  
 存取類型：唯讀  
  
 訊息區塊或完整訊息在送出之前，可以在記憶體中保持緩衝的最大時間間隔。  
  
### MaxPendingAccepts  
 資料型別：sint32  
  
 存取類型：唯讀  
  
 可用來處理服務之連入連線的擱置中非同步接受執行緒數目上限。  
  
### MaxPendingConnections  
 資料型別：sint32  
  
 存取類型：唯讀  
  
 服務的擱置連線數目上限。  
  
### TransferMode  
 資料型別：字串  
  
 存取類型：唯讀  
  
 指定訊息是否使用連線導向傳輸進行緩衝或資料流處理的值。  
  
## 需求  
  
|MOF|於 Servicemodel.mof 中宣告。|  
|---------|-----------------------------|  
|命名空間|於 root\\ServiceModel 中定義|  
  
## 請參閱  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>