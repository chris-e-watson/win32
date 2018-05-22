---
title: Error.webHelp method
description: The webHelp method launches the Windows Media Player Web Help page to display further information about the first error in the error queue (index zero).
ms.assetid: '79797b41-1d47-4347-aa47-c104f7f7fbaf'
keywords: ["webHelp method Windows Media Player", "webHelp method Windows Media Player , Error class", "Error class Windows Media Player , webHelp method"]
topic_type:
- apiref
api_name:
- Error.webHelp
api_location:
- wmp.dll
api_type:
- COM
---

# Error.webHelp method

The **webHelp** method launches the Windows Media Player Web Help page to display further information about the first error in the error queue (index zero).

## Syntax


```JScript
Error.webHelp()
```



## Parameters

This method has no parameters.

## Return value

This method does not return a value.

## Remarks

The Web Help pages always contain the latest and most detailed information about Windows Media Player errors. This method automatically transfers the other information needed by Web Help, such as the operating system version being used.

To access the Web Help pages directly, use the following error code and support center links.

-   [Windows Media Player Error Code Information](http://support.microsoft.com/kb/886273)
-   [Windows Media Player Solution Center](http://go.microsoft.com/fwlink/p/?linkid=10187)

**Windows Media Player 10 Mobile:** This method always succeeds, but does not perform the intended operation.

## Examples

The following example creates an HTML BUTTON element that launches the Microsoft Windows Media Player Web Help page. The **Player** object was created with ID = "Player".


```JScript
<INPUT TYPE = "BUTTON"  
       NAME = "WHBUTTON"  
       VALUE = "More Info"

OnClick = "Player.error.webHelp();

">

```



## Requirements



|                    |                                                                                    |
|--------------------|------------------------------------------------------------------------------------|
| Version<br/> | Windows Media Player version 7.0 or later.<br/>                              |
| DLL<br/>     | <dl> <dt>Wmp.dll</dt> </dl> |



## See also

<dl> <dt>

[**Error Object**](error-object.md)
</dt> </dl>

�

�




