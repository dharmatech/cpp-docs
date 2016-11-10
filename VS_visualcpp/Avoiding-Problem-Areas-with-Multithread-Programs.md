---
title: "Avoiding Problem Areas with Multithread Programs"
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
ms.topic: article
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
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
# Avoiding Problem Areas with Multithread Programs
There are several problems you might encounter in creating, linking, or executing a multithread C program. Some of the more common problems are described in the following table. (For a similar discussion from the MFC point of view, see [Multithreading: Programming Tips](../VS_visualcpp/Multithreading--Programming-Tips.md).)  
  
|Problem|Probable cause|  
|-------------|--------------------|  
|You get a message box showing that your program caused a protection violation.|Many Win32 programming errors cause protection violations. A common cause of protection violations is the indirect assignment of data to null pointers. Because this results in your program trying to access memory that does not belong to it, a protection violation is issued.<br /><br /> An easy way to detect the cause of a protection violation is to compile your program with debugging information and then run it through the debugger in the Visual C++ environment. When the protection fault occurs, Windows transfers control to the debugger and the cursor is positioned on the line that caused the problem.|  
|Your program generates numerous compile and link errors.|You can eliminate many potential problems by setting the compiler's warning level to one of its highest values and heeding the warning messages. By using the level 3 or level 4 warning level options, you can detect unintentional data conversions, missing function prototypes, and use of non-ANSI features.|  
  
## See Also  
 [Multithreading with C and Win32](../VS_visualcpp/Multithreading-with-C-and-Win32.md)