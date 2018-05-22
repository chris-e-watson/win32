﻿---
Description: 'The IOCTL\_USBPRINT\_SOFT\_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.'
ms.assetid: '84e9197a-a096-42ff-af0d-3f4dab9fe0c6'
title: 'IOCTL\_USBPRINT\_SOFT\_RESET control code'
---

# IOCTL\_USBPRINT\_SOFT\_RESET control code

The **IOCTL\_USBPRINT\_SOFT\_RESET** request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer.

## Input Buffer

Not used with this operation; set this parameter to **NULL**.

## Input Buffer Length

Not used with this operation; set this parameter to 0.

## Output Buffer

Not used with this operation; set this parameter to **NULL**.

## Output Buffer Length

Not used with this operation; set this parameter to 0.

## Status block

**Irp-&gt;IoStatus.Status** is set to **STATUS\_SUCCESS** if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](kernel.ntstatus_values) code.

## Requirements



|                   |                                                                                       |
|-------------------|---------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Usbprint.h</dt> </dl> |



## See also

<dl> <dt>

[Creating IOCTL Requests in Drivers](kernel.creating_ioctl_requests_in_drivers)
</dt> <dt>

[**WdfIoTargetSendInternalIoctlOthersSynchronously**](wdf.wdfiotargetsendinternalioctlotherssynchronously)
</dt> <dt>

[**WdfIoTargetSendInternalIoctlSynchronously**](wdf.wdfiotargetsendinternalioctlsynchronously)
</dt> <dt>

[**WdfIoTargetSendIoctlSynchronously**](wdf.wdfiotargetsendioctlsynchronously)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20IOCTL_USBPRINT_SOFT_RESET%20control%20code%20%20RELEASE:%20%285/12/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/en-us/default.aspx. "Send comments about this topic to Microsoft")




