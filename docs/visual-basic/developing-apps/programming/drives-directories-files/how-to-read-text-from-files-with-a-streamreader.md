---
title: "如何：以 StreamReader 從檔案讀取文字 (Visual Basic) | Microsoft Docs"
ms.custom: 
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
- reading files, text
- text, reading from files
- reading text from files
- files, reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: e53fe99a3b3292fc465271d667ef76053e61af51
ms.contentlocale: zh-tw
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>如何：以 StreamReader 從檔案讀取文字 (Visual Basic)
`My.Computer.FileSystem` 物件提供方法來開啟 <xref:System.IO.TextReader> 和 <xref:System.IO.TextWriter>。 除非您選取 [全部] 索引標籤，否則 `OpenTextFileWriter` 和 `OpenTextFileReader` 這兩種方法是未出現在 IntelliSense 中的進階方法。  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>使用文字讀取器從檔案讀取一行  
  
-   使用 `OpenTextFileReader` 方法來開啟 <xref:System.IO.TextReader>，並指定檔案。 這個範例會開啟名為 `testfile.txt` 的檔案，並讀取其中一行，然後顯示訊息方塊中的行。  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a>穩固程式設計  
 讀取的檔案必須是文字檔。  
  
 請勿根據檔案名稱來判斷檔案內容。 例如，檔案 Form1.vb 可能不是 Visual Basic 來源檔案。  
  
 在應用程式中使用這些資料之前，請先驗證所有輸入值。 檔案內容可能與預期不同，並從檔案讀取資料的方法會失敗。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 若要讀取檔案，您的組件需要 <xref:System.Security.Permissions.FileIOPermission> 類別所授與的權限等級。 如果要在部分信任內容中執行，則程式碼可能會因權限不足而擲回例外狀況。 如需詳細資訊，請參閱[程式碼存取安全性基本概念](https://msdn.microsoft.com/library/33tceax8)。 使用者也需要存取檔案。 如需詳細資訊，請參閱 [ACL 技術概觀](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [SaveFileDialog 元件](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)   
 [從檔案讀取](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
