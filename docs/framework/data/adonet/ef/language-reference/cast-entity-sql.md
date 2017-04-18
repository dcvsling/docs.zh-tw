---
title: "CAST (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# CAST (Entity SQL)
將一種資料類型的運算式轉換成另一種。  
  
## 語法  
  
```  
  
CAST ( expression AS data_type)  
```  
  
## 引數  
 `expression`  
 可以轉換為 `data_type` 的任何有效運算式。  
  
 `data_type`  
 目標系統提供的資料型別。 它必須是基本 \(純量\) 型別。 使用的 `data_type` 視查詢空間而定。 如果查詢是以 <xref:System.Data.EntityClient.EntityCommand> 執行的，資料型別會是在概念模型中定義的型別。 如需詳細資訊，請參閱[CSDL 規格](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)。 如果查詢是以 <xref:System.Data.Objects.ObjectQuery%601> 執行的，則資料型別為 Common Language Runtime \(CLR\) 型別。  
  
## 傳回值  
 傳回 `data_type` 的相同值。  
  
## 備註  
 轉型運算式的語意很類似 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT 運算式。 轉型運算式是用來將某個型別的值轉換成另一個型別的值。  
  
```  
CAST( e as T )  
```  
  
 如果 e 為 S 型別，且 S 可轉換成 T，則上述運算式便是有效的轉型運算式。 T 必須是基本 \(純量\) 型別。  
  
 轉型為 `Edm.Decimal` 時可選擇性提供有效位數和小數位數 Facet 的值。 如果沒有明確提供，則有效位數和小數位數的預設值將分別為 18 和 0。 更明確地講，下列多載支援 `Decimal`：  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 使用轉型運算式會視為明確轉換。 而明確轉換可能會截斷資料或遺失有效位數。  
  
> [!NOTE]
>  只有在基本型別和列舉成員型別上能支援 CAST。  
  
## 範例  
 下列 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查詢使用 CAST 運算子將某個資料型別的運算式轉型為另一個資料型別。 此查詢是根據 AdventureWorks Sales Model。 若要編譯及執行此查詢，請遵循以下步驟：  
  
1.  遵循 [HOW TO：執行可傳回 PrimitiveType 結果的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md) 中的程序進行。  
  
2.  將下列查詢當成引數，傳遞至 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## 請參閱  
 [Entity SQL 參考](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)