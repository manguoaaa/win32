---
Description: The GetRestorePosition method retrieves the position to which the window will be restored when it is not maximized or minimized.
ms.assetid: 5f129be3-c4d8-4583-bbc8-870e0bcafd80
title: CBaseControlWindow.GetRestorePosition method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CBaseControlWindow.GetRestorePosition method

The `GetRestorePosition` method retrieves the position to which the window will be restored when it is not maximized or minimized.

## Syntax


```C++
HRESULT GetRestorePosition(
   long *pLeft,
   long *pTop,
   long *pWidth,
   long *pHeight
);
```



## Parameters

<dl> <dt>

*pLeft* 
</dt> <dd>

Pointer to the value for leftmost coordinate.

</dd> <dt>

*pTop* 
</dt> <dd>

Pointer to the value for top of the window.

</dd> <dt>

*pWidth* 
</dt> <dd>

Pointer to the value for width of the window.

</dd> <dt>

*pHeight* 
</dt> <dd>

Pointer to the value for height of window.

</dd> </dl>

## Return value

Returns an **HRESULT** value.

## Remarks

This is the same as the values returned by the [**CBaseControlWindow::GetWindowPosition**](cbasecontrolwindow-getwindowposition.md) function when the window is neither maximized nor minimized.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseControlWindow Class**](cbasecontrolwindow.md)
</dt> </dl>

 

 



