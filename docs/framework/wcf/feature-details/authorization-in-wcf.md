---
title: "WCF 的授權 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "授權 [WCF]"
  - "安全性 [WCF], 授權"
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# WCF 的授權
授權是控制資源 \(例如服務或檔案\) 存取與權限的程序。本章節的主題將說明如何在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 以各種方式執行此基本工作。  
  
## 在本節中  
 [存取控制機制](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 提供 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中驗證機制的概述，以及建議用法。  
  
 [HOW TO：使用 PrincipalPermissionAttribute 類別來限制存取](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 示範限制存取具有 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 之服務的程序。  
  
 [HOW TO：使用 ASP.NET 角色提供者搭配服務](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 逐步執行服務的組態設定，讓它能使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 的角色提供者功能。  
  
 [HOW TO：使用 ASP.NET 授權管理員角色提供者搭配服務](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 可以使用授權管理員管理網站的授權。[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 同樣可以對用戶端使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\/授權管理員的組合進行授權。  
  
 [使用身分識別模型來管理宣告與授權](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 解釋對宣告型授權使用「識別模型」基礎結構的基本概念。  
  
 [委派和模擬](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 解釋委派與模擬之間的差異。  
  
## 參考  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## 相關章節  
 [驗證](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## 請參閱  
 [安全性概觀](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Windows Server AppFabric 的資訊安全模型](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)