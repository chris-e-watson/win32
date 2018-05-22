---
Description: 'The GetActualDataLength method retrieves the length of the valid data in the buffer. This method implements the IMediaSample::GetActualDataLength method.'
ms.assetid: 'bdb8c2b9-7be4-494b-bb96-34a9936d4a2f'
title: 'CMediaSample.GetActualDataLength method'
---

# CMediaSample.GetActualDataLength method

The `GetActualDataLength` method retrieves the length of the valid data in the buffer. This method implements the [**IMediaSample::GetActualDataLength**](imediasample-getactualdatalength.md) method.

## Syntax


```C++
LONG GetActualDataLength();
```



## Parameters

This method has no parameters.

## Return value

Returns the length of the valid data, in bytes.

## Remarks

The [**CMediaSample::m\_lActual**](cmediasample-m-lactual.md) member variable specifies this property.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CMediaSample Class**](cmediasample.md)
</dt> </dl>

�

�



