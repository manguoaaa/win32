---
title: Grayscale effect
description: Converts an image to monochromatic gray.
ms.assetid: 4e0b26ed-ba71-5f8f-db1e-f1b4e28fbd11
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Grayscale effect

Converts an image to monochromatic gray.

Grayscale uses the color matrix effect to convert to grayscale, using the following matrix:

![conversion matrix](images/grayscale-effect-matrix.png)

The CLSID for this effect is CLSID\_D2D1Grayscale.

-   [Example Image](#example-image)
-   [Effect Properties](#effect-properties)
-   [Requirements](#requirements)
-   [Related topics](#related-topics)

## Example Image

![example of effect output](images/grayscale-effect.png)

## Effect Properties

This effect has no properties.

## Requirements



|                          |                                                   |
|--------------------------|---------------------------------------------------|
| Minimum supported client | Windows 10 \[desktop apps \| Windows Store apps\] |
| Minimum supported server | Windows 10 \[desktop apps \| Windows Store apps\] |
| Header                   | d2d1effects\_2.h                                  |
| Library                  | d2d1.lib, dxguid.lib                              |



 

## Related topics

<dl> <dt>

[**ID2D1Effect**](https://msdn.microsoft.com/en-us/library/Hh404566(v=VS.85).aspx)
</dt> </dl>

 

 



