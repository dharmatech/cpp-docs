---
title: "Allocating and Releasing Memory for a BSTR"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTRs, memory allocation"
  - "memory deallocation, string memory"
  - "memory [C++], releasing"
  - "memory allocation, BSTRs"
  - "memory deallocation, BSTR memory"
  - "strings [C++], releasing"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 11
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
# Allocating and Releasing Memory for a BSTR
When you create `BSTR`s and pass them between COM objects, you must take care in treating the memory they use in order to avoid memory leaks. When a `BSTR` stays within an interface, you must free its memory when you are done with it. However, when a `BSTR` passes out of an interface, the receiving object takes responsibility for its memory management.  
  
 In general, the rules for allocating and releasing memory allocated for `BSTR`s are as follows:  
  
-   When you call into a function that expects a `BSTR` argument, you must allocate the memory for the `BSTR` before the call and release it afterwards. For example:  
  
     [!code[NVC_ATLMFC_Utilities#192](../atl/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code[NVC_ATLMFC_Utilities#193](../atl/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   When you call into a function that returns a `BSTR`, you must free the string yourself. For example:  
  
     [!code[NVC_ATLMFC_Utilities#194](../atl/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code[NVC_ATLMFC_Utilities#195](../atl/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   When you implement a function that returns a `BSTR`, allocate the string but do not free it. The receiving the function releases the memory. For example:  
  
     [!code[NVC_ATLMFC_Utilities#196](../atl/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## See Also  
 [Strings (ATL/MFC)](../atl/strings--atl-mfc-.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](assetId:///9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](assetId:///8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)