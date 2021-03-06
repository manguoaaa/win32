---
Description: Prevents more than one thread from completing acquiring a lock.
ms.assetid: 9cdcc6d5-b2f1-4c88-b859-1c15a80e70a9
title: CShareLockNH::PartialLock method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CShareLockNH.PartialLock
api_type: 
- COM
api_location: 
- Rwnh.dll
---

# CShareLockNH::PartialLock method

Prevents more than one thread from completing acquiring a lock.

## Syntax


```C++
void PartialLock();
```



## Parameters

This method has no parameters.

## Return value

This method does not return a value.

## Remarks

While **PartialLock** is in effect, other threads calling [**ShareLock**](csharelocknh--sharelock.md) can enter the lock.

This function has no associated import library or header file; you must call it using the [**LoadLibrary**](https://msdn.microsoft.com/library/ms684175(v=VS.85).aspx) and [**GetProcAddress**](https://msdn.microsoft.com/library/ms683212(v=VS.85).aspx) functions.

## Requirements



|                |                                                                                     |
|----------------|-------------------------------------------------------------------------------------|
| DLL<br/> | <dl> <dt>Rwnh.dll</dt> </dl> |



 

 




