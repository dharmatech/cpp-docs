---
title: "Event Sink Maps"
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
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 11
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
# Event Sink Maps
When an embedded OLE control fires an event, the control's container receives the event using a mechanism, called an "event sink map," supplied by MFC. This event sink map designates handler functions for each specific event, as well as parameters of those events. For more information on event sink maps, see the article             [ActiveX Control Containers](../VS_visualcpp/ActiveX-Control-Containers.md).  
  
### Event Sink Maps  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|Starts the definition of an event sink map.|  
|[DECLARE_EVENTSINK_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|Declares an event sink map.|  
|[END_EVENTSINK_MAP](../Topic/END_EVENTSINK_MAP.md)|Ends the definition of an event sink map.|  
|[ON_EVENT](../Topic/ON_EVENT.md)|Defines an event handler for a specific event.|  
|[ON_EVENT_RANGE](../Topic/ON_EVENT_RANGE.md)|Defines an event handler for a specific event fired from a set of OLE controls.|  
|[ON_EVENT_REFLECT](../Topic/ON_EVENT_REFLECT.md)|Receives events fired by the control before they are handled by the control's container.|  
|[ON_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|Defines a handler for handling property notifications from an OLE control.|  
|[ON_PROPNOTIFY_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|Defines a handler for handling property notifications from a set of OLE controls.|  
|[ON_PROPNOTIFY_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|Receives property notifications sent by the control before they are handled by the control's container.|  
  
##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP  
 Begins the definition of your event sink map.  
  
```  
  
BEGIN_EVENTSINK_MAP(  
theClass  
,   
baseClass  
)  
  
```  
  
### Parameters  
 `theClass`  
 Specifies the name of the control class whose event sink map this is.  
  
 `baseClass`  
 Specifies the name of the base class of                                 `theClass`.  
  
### Remarks  
 In the implementation (.cpp) file that defines the member functions for your class, start the event sink map with the                         `BEGIN_EVENTSINK_MAP` macro, then add macro entries for each event to be notified of, and complete the event sink map with the                         `END_EVENTSINK_MAP` macro.  
  
 For more information on event sink maps and OLE control containers, see the article                         [ActiveX Control Containers](../VS_visualcpp/ActiveX-Control-Containers.md).  
  
##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP  
 An OLE container can provide an event sink map to specify the events your container will be notified of.  
  
```  
  
DECLARE_EVENTSINK_MAP(  
)  
  
```  
  
### Remarks  
 Use the                         `DECLARE_EVENTSINK_MAP` macro at the end of your class declaration. Then, in the .CPP file that defines the member functions for the class, use the                         `BEGIN_EVENTSINK_MAP` macro, macro entries for each of the events to be notified of, and the                         `END_EVENTSINK_MAP` macro to declare the end of the event sink list.  
  
 For more information on event sink maps, see the article                         [ActiveX Control Containers](../VS_visualcpp/ActiveX-Control-Containers.md).  
  
##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP  
 Ends the definition of your event sink map.  
  
```  
  
END_EVENTSINK_MAP(  
)  
  
```  
  
##  <a name="on_event"></a>  ON_EVENT  
 Use the                 `ON_EVENT` macro to define an event handler function for an event fired by an OLE control.  
  
```  
  
ON_EVENT(  
theClass  
,   
id  
,   
dispid  
,   
pfnHandler  
,   
vtsParams  
)  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 `id`  
 The control ID of the OLE control.  
  
 `dispid`  
 The dispatch ID of the event fired by the control.  
  
 `pfnHandler`  
 Pointer to a member function that handles the event. This function should have a                                 **BOOL** return type, and parameter types that match the event's parameters (see                                 `vtsParams`). The function should return                                 **TRUE** to indicate the event was handled; otherwise                                 **FALSE**.  
  
 `vtsParams`  
 A sequence of                                 **VTS_** constants that specifies the types of the parameters for the event. These are the same constants that are used in dispatch map entries such as                                 `DISP_FUNCTION`.  
  
### Remarks  
 The                         `vtsParams` argument is a space-separated list of values from the                         **VTS_** constants. One or more of these values separated by spaces (not commas) specifies the function's parameter list. For example:  
  
 [!CODE [NVC_MFCAutomation#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#11)]  
  
 specifies a list containing a short integer followed by a                         **BOOL**.  
  
 For a list of the                         **VTS_** constants, see                         [EVENT_CUSTOM](../Topic/EVENT_CUSTOM.md).  
  
##  <a name="on_event_range"></a>  ON_EVENT_RANGE  
 Use the                 `ON_EVENT_RANGE` macro to define an event handler function for an event fired by any OLE control having a control ID within a contiguous range of IDs.  
  
```  
  
ON_EVENT_RANGE(  
theClass  
,   
idFirst  
,   
idLast  
,   
dispid  
,   
pfnHandler  
,   
vtsParams  
)  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 `idFirst`  
 The control ID of the first OLE control in the range.  
  
 `idLast`  
 The control ID of the last OLE control in the range.  
  
 `dispid`  
 The dispatch ID of the event fired by the control.  
  
 `pfnHandler`  
 Pointer to a member function that handles the event. This function should have a                                 **BOOL** return type, a first parameter of type                                 **UINT** (for the control ID), and additional parameter types that match the event's parameters (see                                 `vtsParams`). The function should return                                 **TRUE** to indicate the event was handled; otherwise                                 **FALSE**.  
  
 `vtsParams`  
 A sequence of                                 **VTS_** constants that specifies the types of the parameters for the event. The first constant should be of type                                 **VTS_I4**, for the control ID. These are the same constants that are used in dispatch map entries such as                                 `DISP_FUNCTION`.  
  
### Remarks  
 The                         `vtsParams` argument is a space-separated list of values from the                         **VTS_** constants. One or more of these values separated by spaces (not commas) specifies the function's parameter list. For example:  
  
 [!CODE [NVC_MFCAutomation#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#11)]  
  
 specifies a list containing a short integer followed by a                         **BOOL**.  
  
 For a list of the                         **VTS_** constants, see                         [EVENT_CUSTOM](../Topic/EVENT_CUSTOM.md).  
  
### Example  
 The following example demonstrates an event handler, for the MouseDown event, implemented for three controls (                                `IDC_MYCTRL1` through                                 `IDC_MYCTRL3`). The event handler function,                                 `OnRangeMouseDown`, is declared in the header file of the dialog class (                                `CMyDlg`) as:  
  
 [!CODE [NVC_MFCAutomation#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#12)]  
  
 The code below is defined in the implementation file of the dialog class.  
  
 [!CODE [NVC_MFCAutomation#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#13)]  
  
##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT  
 The                 `ON_EVENT_REFLECT` macro, when used in the event sink map of an OLE control's wrapper class, receives events fired by the control before they are handled by the control's container.  
  
```  
  
ON_EVENT_REFLECT(  
theClass  
,   
dispid  
,   
pfnHandler  
,   
vtsParams  
 )  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 dispid  
 The dispatch ID of the event fired by the control.  
  
 `pfnHandler`  
 Pointer to a member function that handles the event. This function should have a                                 **BOOL** return type and parameter types that match the event's parameters (see                                 `vtsParams`). The function should return                                 **TRUE** to indicate the event was handled; otherwise                                 **FALSE**.  
  
 `vtsParams`  
 A sequence of                                 **VTS_** constants that specifies the types of the parameters for the event. These are the same constants that are used in dispatch map entries such as                                 `DISP_FUNCTION`.  
  
### Remarks  
 The                         `vtsParams` argument is a space-separated list of values from the                         **VTS_** constants.  
  
 One or more of these values separated by spaces (not commas) specifies the function's parameter list. For example:  
  
 [!CODE [NVC_MFCAutomation#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#11)]  
  
 specifies a list containing a short integer followed by a                         **BOOL**.  
  
 For a list of the                         **VTS_** constants, see                         [EVENT_CUSTOM](../Topic/EVENT_CUSTOM.md).  
  
##  <a name="on_propnotify"></a>  ON_PROPNOTIFY  
 Use the                 `ON_PROPNOTIFY` macro to define an event sink map entry for handling property notifications from an OLE control.  
  
```  
  
ON_PROPNOTIFY(  
theClass  
,   
id  
,   
dispid  
,   
pfnRequest  
,   
pfnChanged  
)  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 `id`  
 The control ID of the OLE control.  
  
 `dispid`  
 The dispatch ID of the property involved in the notification.  
  
 `pfnRequest`  
 Pointer to a member function that handles the                                 **OnRequestEdit** notification for this property. This function should have a                                 **BOOL** return type and a                                 **BOOL\*** parameter. This function should set the parameter to                                 **TRUE** to allow the property to change and                                 **FALSE** to disallow. The function should return                                 **TRUE** to indicate the notification was handled; otherwise                                 **FALSE**.  
  
 `pfnChanged`  
 Pointer to a member function that handles the                                 **OnChanged** notification for this property. The function should have a                                 **BOOL** return type and a                                 **UINT** parameter. The function should return                                 **TRUE** to indicate that notification was handled; otherwise                                 **FALSE**.  
  
### Remarks  
 The                         `vtsParams` argument is a space-separated list of values from the                         **VTS_** constants. One or more of these values separated by spaces (not commas) specifies the function's parameter list. For example:  
  
 [!CODE [NVC_MFCAutomation#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#11)]  
  
 specifies a list containing a short integer followed by a                         **BOOL**.  
  
 For a list of the                         **VTS_** constants, see                         [EVENT_CUSTOM](../Topic/EVENT_CUSTOM.md).  
  
##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE  
 Use the                 `ON_PROPNOTIFY_RANGE` macro to define an event sink map entry for handling property notifications from any OLE control having a control ID within a contiguous range of IDs.  
  
```  
  
ON_PROPNOTIFY_RANGE(  
theClass  
,   
idFirst  
,   
idLast  
,   
dispid  
,   
pfnRequest  
,   
pfnChanged  
)  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 `idFirst`  
 The control ID of the first OLE control in the range.  
  
 `idLast`  
 The control ID of the last OLE control in the range.  
  
 `dispid`  
 The dispatch ID of the property involved in the notification.  
  
 `pfnRequest`  
 Pointer to a member function that handles the                                 **OnRequestEdit** notification for this property. This function should have a                                 **BOOL** return type and                                 **UINT** and                                 **BOOL\*** parameters. The function should set the parameter to                                 **TRUE** to allow the property to change and                                 **FALSE** to disallow. The function should return                                 **TRUE** to indicate that notification was handled; otherwise                                 **FALSE**.  
  
 `pfnChanged`  
 Pointer to a member function that handles the                                 **OnChanged** notification for this property. The function should have a                                 **BOOL** return type and a                                 **UINT** parameter. The function should return                                 **TRUE** to indicate that notification was handled; otherwise                                 **FALSE**.  
  
##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT  
 The                 `ON_PROPNOTIFY_REFLECT` macro, when used in the event sink map of an OLE control's wrapper class, receives property notifications sent by the control before they are handled by the control's container.  
  
```  
  
ON_PROPNOTIFY_REFLECT(  
theClass  
,   
dispid  
,   
pfnRequest  
,   
pfnChanged  
 )  
  
```  
  
### Parameters  
 `theClass`  
 The class to which this event sink map belongs.  
  
 `dispid`  
 The dispatch ID of the property involved in the notification.  
  
 `pfnRequest`  
 Pointer to a member function that handles the                                 **OnRequestEdit** notification for this property. This function should have a                                 **BOOL** return type and a                                 **BOOL\*** parameter. This function should set the parameter to                                 **TRUE** to allow the property to change and                                 **FALSE** to disallow. The function should return                                 **TRUE** to indicate the notification was handled; otherwise                                 **FALSE**.  
  
 `pfnChanged`  
 Pointer to a member function that handles the                                 **OnChanged** notification for this property. The function should have a                                 **BOOL** return type and no parameters. The function should return                                 **TRUE** to indicate the notification was handled; otherwise                                 **FALSE**.  
  
## See Also  
 [Macros and Globals](../VS_visualcpp/MFC-Macros-and-Globals.md)