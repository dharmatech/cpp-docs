---
title: "jitintrinsic"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: language-reference
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
manager: ghogen
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
---
# jitintrinsic
Marks the function as significant to the 64-bit common language runtime. This is used on certain functions in Microsoft-provided libraries.  
  
## Syntax  
  
```  
__declspec(jitintrinsic)  
```  
  
## Remarks  
 `jitintrinsic` adds a MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic?qualifyHint=False>) to a function signature.  
  
 Users are discouraged from using this `__declspec` modifier, as unexpected results can occur.  
  
## See Also  
 [__declspec](../VS_visualcpp/__declspec.md)   
 [Keywords](../VS_visualcpp/Keywords--C---.md)