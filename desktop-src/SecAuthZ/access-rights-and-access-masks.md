---
Description: 'An access right is a bit flag that corresponds to a particular set of operations that a thread can perform on a securable object.'
ms.assetid: 'da67c486-d2e7-4632-ac7a-c18aabc3f21d'
title: Access Rights and Access Masks
---

# Access Rights and Access Masks

An *access right* is a bit flag that corresponds to a particular set of operations that a thread can perform on a securable object. For example, a registry key has the KEY\_SET\_VALUE access right, which corresponds to the ability of a thread to set a value under the key. If a thread tries to perform an operation on an object, but does not have the necessary access right to the object, the system does not carry out the operation.

An [*access mask*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-mask-gly) is a 32-bit value whose bits correspond to the access rights supported by an object. All Windows securable objects use an [access mask format](access-mask-format.md) that includes bits for the following types of access rights:

-   [Generic access rights](generic-access-rights.md)
-   [Standard access rights](standard-access-rights.md)
-   [SACL access right](sacl-access-right.md)
-   [Directory services access rights](directory-services-access-rights.md)

When a thread tries to open a handle to an object, the thread typically specifies an access mask to [request a set of access rights](requesting-access-rights-to-an-object.md). For example, an application that needs to set and query the values of a registry key can open the key by using an access mask to request the KEY\_SET\_VALUE and KEY\_QUERY\_VALUE access rights.

The following table shows the functions that manipulate the security information for each type of securable object.



| Object type                                                                                                                                           | Security descriptor functions                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Files or directories](https://msdn.microsoft.com/library/windows/desktop/aa364399) on an NTFS file system                                                                     | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| [Named pipes](https://msdn.microsoft.com/library/windows/desktop/aa365600)[Anonymous pipes](https://msdn.microsoft.com/library/windows/desktop/aa365142)<br/>                 | [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md)                                                                                                             |
| Console screen buffers                                                                                                                                | Not supported.                                                                                                                                                                                     |
| [Processes](https://msdn.microsoft.com/library/windows/desktop/ms684880)[Threads](https://msdn.microsoft.com/library/windows/desktop/ms686769)<br/>                                      | [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md)                                                                                                             |
| [File-mapping objects](https://msdn.microsoft.com/library/windows/desktop/aa366559)                                                                                  | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| [Access tokens](access-rights-for-access-token-objects.md)                                                                                           | [**SetKernelObjectSecurity**](setkernelobjectsecurity.md), [**GetKernelObjectSecurity**](getkernelobjectsecurity.md)                                                                             |
| Window-management objects ([window stations](https://msdn.microsoft.com/library/windows/desktop/ms687391) and [desktops](https://msdn.microsoft.com/library/windows/desktop/ms682575)) | [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md)                                                                                                             |
| [Registry keys](https://msdn.microsoft.com/library/windows/desktop/ms724878)                                                                                         | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| [Windows services](https://msdn.microsoft.com/library/windows/desktop/ms685981)                                                                                           | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| Local or remote printers                                                                                                                              | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| Network shares                                                                                                                                        | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| [Interprocess synchronization objects](https://msdn.microsoft.com/library/windows/desktop/ms686670) (events, mutexes, semaphores, and waitable timers)     | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |
| [Job objects](https://msdn.microsoft.com/library/windows/desktop/ms684164)                                                                                             | [**GetNamedSecurityInfo**](getnamedsecurityinfo.md), [**SetNamedSecurityInfo**](setnamedsecurityinfo.md), [**GetSecurityInfo**](getsecurityinfo.md), [**SetSecurityInfo**](setsecurityinfo.md) |



�

�

�



