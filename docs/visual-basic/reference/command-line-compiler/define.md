---
title: "/define (Visual Basic) |Microsoft 文件"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48c3bae1c6cf5831f95ce86dbcf6adadab9d5db8
ms.lasthandoff: 03/13/2017

---
# <a name="define-visual-basic"></a>/define (Visual Basic)
定義條件式編譯器常數。  
  
## <a name="syntax"></a>語法  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>引數  
  
|詞彙|定義|  
|---|---|  
|`symbol`|必要項。 要定義的符號。|  
|`value`|選擇項。 要指派 `symbol` 的值。 如果`value`是一個字串，它必須以反斜線/引號的順序括住 (\\」) 而不是引號。 如果未指定值，則會認為是 True。|  
  
## <a name="remarks"></a>備註  
 `/define` 選項有一個類似在原始程式檔中使用 `#Const` 前置處理器指示詞的效果，除了以 `/define` 定義的常數是公開的，且適用於專案中的所有檔案。  
  
 您可以使用此選項建立的符號，搭配 `#If`...`Then`...`#Else` 指示詞，有條件地編譯原始程式檔。  
  
 `/d` 是 `/define` 的簡短形式。  
  
 您可以使用逗號分隔符號定義，以 `/define` 定義多個符號。  
  
|在 Visual Studio 整合式開發環境中設定 / 定義|  
|---|  
|1.在 **方案總管**中選取專案。 在**專案**] 功能表上，按一下 [**屬性**。 如需詳細資訊，請參閱[專案設計工具簡介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。<br />2.按一下 [編譯]**** 索引標籤。<br />3.按一下 [ **進階**]。<br />4.修改中的值**自訂常數**方塊。|  
  
## <a name="example"></a>範例  
 下列程式碼會定義然後使用兩個條件式編譯器常數。  
  
 [!code-vb[VbVbalrCompiler #&45;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>另請參閱  
 [Visual Basic 命令列編譯器](../../../visual-basic/reference/command-line-compiler/index.md)   
 [#If......#Else 指示詞](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [#Const 指示詞](../../../visual-basic/language-reference/directives/const-directive.md)   
 [編譯命令列範例](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
