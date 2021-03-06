---
title: "^= 運算子 (C# 參考) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^= 運算子 [C#]"
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# ^= 運算子 (C# 參考)
Exclusive\-OR 指派運算子。  
  
## 備註  
 這種形式的運算式  
  
```  
x ^= y  
```  
  
 將評估為  
  
```  
x = x ^ y  
```  
  
 不同的是，`x` 只被評估了一次。  [^ 運算子](../../../csharp/language-reference/operators/xor-operator.md)會對整數運算元執行位元排除 OR 運算，對 [bool](../../../csharp/language-reference/keywords/bool.md) 運算元則是執行邏輯排除 OR 運算。  
  
 不可直接多載 ^\= 運算子，但使用者定義的型別可以多載 [^ 運算子](../../../csharp/language-reference/operators/xor-operator.md) \(請參閱 [運算子](../../../csharp/language-reference/keywords/operator.md)\)。  
  
## 範例  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## 請參閱  
 [C\# 參考](../../../csharp/language-reference/index.md)   
 [C\# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [C\# 運算子](../../../csharp/language-reference/operators/index.md)