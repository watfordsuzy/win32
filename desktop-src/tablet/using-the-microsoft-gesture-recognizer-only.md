---
Description: You can use an ink collector (InkCollector, InkOverlay, or InkPicture) to access the default Microsoft gesture recognizer directly.To use an ink collector to access the gesture recognizerSet the CollectionMode property of the ink collector to either InkAndGesture mode or GestureOnly mode.inkOverlay.CollectionMode = CollectionMode.GestureOnly;Choose the gesture that you want to support.inkOverlay.SetGestureStatus(ApplicationGesture.AllGestures, true);Implement an event handler that receives gesture notifications. In the event handler, you need to implement the action corresponding to each event received.Note  Mixed mode supports only single-stroke gestures. Gesture mode supports multiple stroke gestures. inkOverlay.Gesture += new InkCollectorGestureEventHandler(inkOverlay\_Gesture);In InkAndGesture mode, each individual stroke is sent to the Microsoft gesture recognizer. If it is recognized as a gesture that you have enabled, an event notification is sent. If the application accepts the event notification, the stroke is erased. If the application does not accept the notification or if the stroke is not recognized to be a gesture, the stroke is stored in the Ink object.In GestureOnly mode, the strokes are delimited by timeouts before and after the strokes. The strokes collected within the timeout are sent to the recognizer. If the strokes are recognized as a gesture that you have enabled, an event notification is sent. The application may accept or reject the event, effecting the corresponding action or not. In gesture-only mode, the strokes are never saved in the Ink object.
ms.assetid: 3f5f00a3-1f2c-4fa2-9738-bc5fb56e2208
title: Using the Microsoft Gesture Recognizer Only
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Using the Microsoft Gesture Recognizer Only

You can use an ink collector ([**InkCollector**](/windows/win32/msinkaut/?branch=master), [**InkOverlay**](/windows/win32/msinkaut/?branch=master), or [InkPicture](inkpicture-control-reference.md)) to access the default Microsoft gesture recognizer directly.

To use an ink collector to access the gesture recognizer:

-   Set the [**CollectionMode**](/windows/win32/msinkaut/ne-msinkaut-inkcollectionmode?branch=master) property of the ink collector to either **InkAndGesture** mode or **GestureOnly** mode.

`inkOverlay.CollectionMode = CollectionMode.GestureOnly;`

-   Choose the gesture that you want to support.

`inkOverlay.SetGestureStatus(ApplicationGesture.AllGestures, true);`

-   Implement an event handler that receives gesture notifications. In the event handler, you need to implement the action corresponding to each event received.
    > [!Note]  
    > Mixed mode supports only single-stroke gestures. Gesture mode supports multiple stroke gestures.

     

`inkOverlay.Gesture += new InkCollectorGestureEventHandler(inkOverlay_Gesture);`

In **InkAndGesture** mode, each individual stroke is sent to the Microsoft gesture recognizer. If it is recognized as a gesture that you have enabled, an event notification is sent. If the application accepts the event notification, the stroke is erased. If the application does not accept the notification or if the stroke is not recognized to be a gesture, the stroke is stored in the [**Ink**](/windows/win32/msinkaut/?branch=master) object.

In **GestureOnly** mode, the strokes are delimited by timeouts before and after the strokes. The strokes collected within the timeout are sent to the recognizer. If the strokes are recognized as a gesture that you have enabled, an event notification is sent. The application may accept or reject the event, effecting the corresponding action or not. In gesture-only mode, the strokes are never saved in the [**Ink**](/windows/win32/msinkaut/?branch=master) object.

## Related topics

<dl> <dt>

[Microsoft.Ink.InkCollector.CollectionMode](frlrfMicrosoftInkInkCollectorClassCollectionModeTopic)
</dt> <dt>

[Microsoft.Ink.InkOverlay.CollectionMode](frlrfMicrosoftInkInkOverlayClassCollectionModeTopic)
</dt> <dt>

[Microsoft.Ink.InkPicture.CollectionMode](frlrfMicrosoftInkInkPictureClassCollectionModeTopic)
</dt> </dl>

 

 


