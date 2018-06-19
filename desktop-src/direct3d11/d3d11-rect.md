---
title: D3D11\_RECT
description: D3D11\_RECT is declared as follows
ms.assetid: 737B47A3-E609-48E4-A0B6-017206E500B1
keywords:
- D3D11_RECT Direct3D 11
topic_type:
- apiref
api_name:
- D3D11_RECT
api_location:
- D3D11.lib
- D3D11.dll
api_type:
- LibDef
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# D3D11\_RECT

D3D11\_RECT is declared as follows:

``` syntax
typedef RECT D3D11_RECT;
```

For more information about this GDI rectangle structure, see [**RECT**](https://msdn.microsoft.com/library/windows/desktop/dd162897).

## Remarks

This structure is used for scissor rectangles by [**ID3D11DeviceContext::RSGetScissorRects**](/windows/desktop/api/D3D11/nf-d3d11-id3d11devicecontext-rsgetscissorrects) and [**ID3D11DeviceContext::RSSetScissorRects**](/windows/desktop/api/D3D11/nf-d3d11-id3d11devicecontext-rssetscissorrects).

## Requirements



|                    |                                                                                      |
|--------------------|--------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3D11.h</dt> </dl>   |
| Library<br/> | <dl> <dt>D3D11.lib</dt> </dl> |



## See also

<dl> <dt>

[Core Structures](d3d11-graphics-reference-d3d11-core-structures.md)
</dt> </dl>

 

 




