---
title: "在 .NET Framework 中變更大小寫 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "區分大小寫"
  - "小寫"
  - "字串 [.NET Framework], 大小寫"
  - "ToLower 方法"
  - "ToUpper 方法"
  - "大寫"
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 在 .NET Framework 中變更大小寫
如果您要撰寫接受使用者輸入的應用程式，則無法確定使用者輸入資料時會使用大寫或小寫。  通常，您會希望字串的大小寫一致，特別是要在使用者介面中顯示這些字串時。  下表描述三種變更大小寫的方法。  前兩種方法提供接受文化特性的多載。  
  
|方法名稱|用法|  
|----------|--------|  
|<xref:System.String.ToUpper%2A?displayProperty=fullName>|將字串中的所有字元轉換成大寫。|  
|<xref:System.String.ToLower%2A?displayProperty=fullName>|將字串中的所有字元轉換成小寫。|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>|將字串轉換成字首大寫。|  
  
> [!WARNING]
>  請注意，您不應該使用 <xref:System.String.ToUpper%2A?displayProperty=fullName> 和 <xref:System.String.ToLower%2A?displayProperty=fullName> 方法來轉換字串，以便對字串進行比較或測試字串是否相等。  如需詳細資訊，請參閱[比較混合大小寫的字串](#Comparing)一節。  
  
<a name="Comparing"></a>   
## 比較混合大小寫的字串  
 若要比較混合大小寫的字串以決定其順序，請使用 `comparisonType` 參數呼叫 <xref:System.String.CompareTo%2A?displayProperty=fullName> 方法的其中一個多載，並為 `comparisonType` 引數提供 <xref:System.StringComparison?displayProperty=fullName>、<xref:System.StringComparison?displayProperty=fullName> 或 <xref:System.StringComparison?displayProperty=fullName> 的值。  若要使用目前文化特性以外的特定文化特性進行比較，請使用 `culture` 和 `options` 參數呼叫 <xref:System.String.CompareTo%2A?displayProperty=fullName> 方法的多載，並提供 <xref:System.Globalization.CompareOptions?displayProperty=fullName> 的值做為 `options` 引數。  
  
 若要比較混合大小寫的字串以決定字串是否相等，請使用 `comparisonType` 參數呼叫 <xref:System.String.Equals%2A?displayProperty=fullName> 方法的其中一個多載，並為 `comparisonType` 引數提供 <xref:System.StringComparison?displayProperty=fullName>、<xref:System.StringComparison?displayProperty=fullName> 或 <xref:System.StringComparison?displayProperty=fullName> 的值。  
  
 如需詳細資訊，請參閱[使用字串的最佳作法](../../../docs/standard/base-types/best-practices-strings.md)。  
  
## ToUpper  
 <xref:System.String.ToUpper%2A?displayProperty=fullName> 方法會將字串中的所有字元變更為大寫。  下列範例會將字串 "Hello World\!" 從混合大小寫轉換成大寫。  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 上述範例預設會區分文化特性，它會套用目前文化特性的大小寫慣例。  若要執行不區分文化特性的大小寫變更，或套用特定文化特性的大小寫慣例，請使用 <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=fullName> 方法多載，並將 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 的值或代表指定文化特性的 <xref:System.Globalization.CultureInfo?displayProperty=fullName> 物件提供給 *culture* 參數。  如需示範如何使用 <xref:System.String.ToUpper%2A> 方法，以執行不區分文化特性之大小寫變更的範例，請參閱[執行不區分文化特性的大小寫變更](../../../ocs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)。  
  
## ToLower  
 <xref:System.String.ToLower%2A?displayProperty=fullName> 方法類似於前一個方法，但會改將字串中的所有字元轉換成小寫。  下列範例會將字串 "Hello World\!" 轉換成小寫。  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 上述範例預設會區分文化特性，它會套用目前文化特性的大小寫慣例。  若要執行不區分文化特性的大小寫變更，或套用特定文化特性的大小寫慣例，請使用 <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=fullName> 方法多載，並將 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 的值或代表指定文化特性的 <xref:System.Globalization.CultureInfo?displayProperty=fullName> 物件提供給 *culture* 參數。  如需示範如何使用 <xref:System.String.ToLower%28System.Globalization.CultureInfo%29> 方法，以執行不區分文化特性之大小寫變更的範例，請參閱[執行不區分文化特性的大小寫變更](../../../ocs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)。  
  
## ToTitleCase  
 <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> 會將每個字的第一個字元轉換成大寫，並將其餘字元轉換成小寫。  不過，全部大寫的字會假設為縮略字，而且不會轉換。  
  
 <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> 方法區分文化特性；也就是說，它會使用特定文化特性的大小寫慣例。  若要呼叫方法，請先從特定文化特性的 <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=fullName> 屬性，擷取代表特定文化特性之大小寫慣例的 <xref:System.Globalization.TextInfo> 物件。  
  
 下列範例會將陣列中的每個字串傳遞給 <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> 方法。  這些字串包含適當的字首大寫字串和縮略字。  這些字串使用英文 \(美國\) 文化特性的大小寫慣例轉換成字首大寫。  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 請注意，雖然它區分文化特性，但 <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> 方法不會提供語言正確的大小寫規則。  例如，在上述範例中，這個方法會將 "a tale of two cities"  轉換成 "A Tale Of Two Cities"。  不過，對於 en\-US 文化特性而言語言正確的字首大寫為 "A Tale of Two Cities"。  
  
## 請參閱  
 [基本字串作業](../../../docs/standard/base-types/basic-string-operations.md)   
 [執行不區分文化特性的字串作業](../../../ocs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)