---
title: "OnCmdMsg Handler"
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
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
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
# OnCmdMsg Handler
To accomplish the routing of commands, each command target calls the `OnCmdMsg` member function of the next command target in the sequence. Command targets use `OnCmdMsg` to determine whether they can handle a command and to route it to another command target if they cannot handle it.  
  
 Each command-target class may override the `OnCmdMsg` member function. The overrides let each class route commands to a particular next target. A frame window, for example, always routes commands to its current child window or view, as shown in the table [Standard Command Route](../VS_visualcpp/Command-Routing.md).  
  
 The default `CCmdTarget` implementation of `OnCmdMsg` uses the message map of the command-target class to search for a handler function for each command message it receives — in the same way that standard messages are searched. If it finds a match, it calls the handler. Message-map searching is explained in [How the Framework Searches Message Maps](../VS_visualcpp/How-the-Framework-Searches-Message-Maps.md).  
  
## See Also  
 [How the Framework Calls a Handler](../VS_visualcpp/How-the-Framework-Calls-a-Handler.md)