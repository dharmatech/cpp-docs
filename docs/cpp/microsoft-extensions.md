---
title: "Microsoft Extensions"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Microsoft extensions to C/C++"
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
caps.latest.revision: 9
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Microsoft Extensions
*asm-statement*:  
 **__asm**  *assembly-instruction* **;**opt  
  
 **__asm {**  *assembly-instruction-list*  **};**opt  
  
 *assembly-instruction-list*:  
 *assembly-instruction* **;**opt  
  
 *assembly-instruction* **;** *assembly-instruction-list* **;**opt  
  
 *ms-modifier-list*:  
 *ms-modifier ms-modifier-list*opt  
  
 *ms-modifier*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **__syscall** (reserved for future implementations)  
  
 **__oldcall** (reserved for future implementations)  
  
 **__unaligned** (reserved for future implementations)  
  
 *based-modifier*  
  
 *based-modifier*:  
 **__based (** *based-type* **)**  
  
 *based-type*:  
 *name*  
  
## See Also  
 [Grammar Summary](../notintoc/grammar-summary--c---.md)