---
title: "_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l"
ms.custom: na
ms.date: 10/04/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - _ismbstrail
  - _ismbslead_l
  - _ismbslead
  - _ismbstrail_l
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
  - api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
caps.latest.revision: 22
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
# _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
Performs context-sensitive tests for multibyte-character-string lead bytes and trail bytes and determines whether a given substring pointer points to a lead byte or a trail byte.  
  
> [!IMPORTANT]
>  This API cannot be used in applications that execute in the Windows Runtime. For more information, see [CRT functions not supported with /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbslead(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbstrail(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbslead_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
int _ismbstrail_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### Parameters  
 `str`  
 Pointer to the start of the string or the previous known lead byte.  
  
 `current`  
 Pointer to the position in the string to be tested.  
  
 `locale`  
 The locale to use.  
  
## Return Value  
 `_ismbslead` returns –1 if the character is a lead byte and `_ismbstrail` returns –1 if the character is a trail byte. If the input strings are valid but are not a lead byte or trail byte, these functions return zero. If either argument is `NULL`, the invalid parameter handler is invoked, as described in [Parameter Validation](../VS_visualcpp/Parameter-Validation.md). If execution is allowed to continue, these functions return `NULL` and set `errno` to `EINVAL`.  
  
## Remarks  
 `_ismbslead` and `_ismbstrail` are slower than the `_ismbblead` and `_ismbbtrail` versions because they take the string context into account.  
  
 The versions of these functions that have the `_l` suffix are identical except that for their locale-dependent behavior they use the locale that's passed in instead of the current locale. For more information, see [Locale](../VS_visualcpp/Locale.md).  
  
## Requirements  
  
|Routine|Required header|Optional header|  
|-------------|---------------------|---------------------|  
|`_ismbslead`|<mbctype.h> or <mbstring.h>|<ctype.h>,* <limits.h>, <stdlib.h>|  
|`_ismbstrail`|<mbctype.h> or <mbstring.h>|<ctype.h>,* <limits.h>, <stdlib.h>|  
|`_ismbslead_l`|<mbctype.h> or <mbstring.h>|<ctype.h>,* <limits.h>, <stdlib.h>|  
|`_ismbstrail_l`|<mbctype.h> or <mbstring.h>|<ctype.h>,* <limits.h>, <stdlib.h>|  
  
 \* For manifest constants for the test conditions.  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md).  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## See Also  
 [Character Classification](../VS_visualcpp/Character-Classification.md)   
 [_ismbc Routines](../VS_visualcpp/_ismbc-Routines.md)   
 [is, isw Routines](../VS_visualcpp/is--isw-Routines.md)   
 [_ismbb Routines](../VS_visualcpp/_ismbb-Routines.md)