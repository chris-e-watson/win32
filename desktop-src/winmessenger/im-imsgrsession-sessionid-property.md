---
title: IMsgrSession SessionID property
description: Retrieves a value that indicates the session ID.
ms.assetid: 'a86529e7-b039-4d2b-956f-3e78af7584bb'
keywords: ["SessionID property Windows Messenger", "SessionID property Windows Messenger , IMsgrSession interface", "IMsgrSession interface Windows Messenger , SessionID property"]
topic_type:
- apiref
api_name:
- IMsgrSession.SessionID
- IMsgrSession.get_SessionID
api_location:
- Msgsc.dll
api_type:
- COM
---

# IMsgrSession::SessionID property

\[**SessionID** is no longer available for use as of Windows�Vista. See [Windows Messenger](im-messenger-entry.md) for more information.\]

Retrieves a value that indicates the session ID.

This property is read-only.

## Syntax


```C++
HRESULT get_SessionID(
  [out, retval]�BSTR *pbstrSessionID
);
```



## Property value

Pointer to a **BSTR** that indicates the session ID.

## Remarks

The following table lists the error codes returned by this property.



| Error Code     | Meaning                                           |
|----------------|---------------------------------------------------|
| E\_INVALIDARG  | The value passed into the property was not valid. |
| E\_OUTOFMEMORY | The session identifier is too long.               |



�



| Error Code | Meaning                                  |
|------------|------------------------------------------|
| 0x8007000E | The session identifier is too long.      |
| 0x80070057 | One of the possible values is not valid. |



�

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                    |
| End of client support<br/>    | Windows�XP<br/>                                                                   |
| End of server support<br/>    | Windows Server�2003<br/>                                                          |
| Product<br/>                  | Messenger 4.0<br/>                                                                |
| Header<br/>                   | <dl> <dt>Msgrpriv.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>Msgrpriv.idl</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Msgsc.dll</dt> </dl>    |



## See also

<dl> <dt>

[**IMsgrSession**](im-imsgrsession.md)
</dt> <dt>

[Messenger Session Invite and Messenger Private APIs](im-session-invite-ovw.md)
</dt> <dt>

[Messenger Lock and Key API](im-lock-and-key-ovw.md)
</dt> </dl>

�

�




