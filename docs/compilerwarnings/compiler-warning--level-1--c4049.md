---
title: "Compiler Warning (level 1) C4049"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
ms.author: "corob"
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
# Compiler Warning (level 1) C4049
compiler limit : terminating line number emission  
  
 The file contains more than 16,777,215 (2<sup>24</sup>-1) source lines. The compiler stops numbering at 16,777,215.  
  
 For code after line 16,777,215:  
  
-   The image will contain no debug information for line numbers.  
  
-   Some diagnostics may be reported with incorrect line numbers.  
  
-   .asm listings (/FAs) may have incorrect line numbers.