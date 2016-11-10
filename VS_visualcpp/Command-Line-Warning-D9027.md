---
title: "Command-Line Warning D9027"
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
ms.topic: error-reference
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
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
# Command-Line Warning D9027
source file '<filename\>' ignored  
  
 CL.exe ignored the input source file.  
  
 This warning can be caused by a space between the /Fo option and an output filename on a command line with the /c option. For example:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Because there is a space between /Fo and `output.obj,` CL.exe takes `output.obj` as the name of the input file. To fix the problem, remove the space:  
  
```  
cl /c /Fooutput.obj input.c   
```