---
title: "實體資料模型：命名空間 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 實體資料模型：命名空間
實體資料模型 \(EDM\) 中的命名空間是抽象的容器，用於[實體類型](../../../../docs/framework/data/adonet/entity-type.md)、[複雜類型](../../../../docs/framework/data/adonet/complex-type.md)和[關聯](../../../../docs/framework/data/adonet/association-type.md)。  EDM 中的命名空間類似於程式設計語言中的命名空間：針對它們所包含的物件提供內容，並且提供方法讓名稱相同 \(但包含在不同命名空間中\) 的物件意義清楚。  
  
## 範例  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 會使用稱為概念結構定義語言 \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) 的特定定義域語言 \(DSL\) 來定義概念模型。  下列 CSDL 程式碼使用命名空間來識別在不同概念模型中定義的型別。  此範例定義的實體類型 \(`Publisher`\) 具有從 `ExtendedBooksModel` 命名空間匯入的複雜類型屬性 \(`Address`\)。  請注意，`Using` 項目代表已匯入命名空間。  亦請注意，`Address` 屬性的型別是利用其完整名稱 \(`ExtendedBooksModel.Address`\) 來定義，表示此型別是在 `ExtendedBooksModel` 命名空間中定義的。  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## 請參閱  
 [實體資料模型索引鍵概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [實體資料模型](../../../../docs/framework/data/adonet/entity-data-model.md)