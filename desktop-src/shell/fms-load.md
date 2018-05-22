﻿---
Description: 'Contains information that File Manager uses to add a custom menu provided by a File Manager extension DLL. The structure also provides a delta value that the extension DLL can use to manipulate the custom menu after File Manager has loaded the menu.'
title: 'FMS\_LOAD structure'
---

# FMS\_LOAD structure

Contains information that File Manager uses to add a custom menu provided by a File Manager extension DLL. The structure also provides a delta value that the extension DLL can use to manipulate the custom menu after File Manager has loaded the menu.

## Syntax


```C++
typedef struct _FMS_LOAD {
  DWORD dwSize;
  TCHAR szMenuName[MENU_TEXT_LEN];
  HMENU hMenu;
  UINT  wMenuDelta;
} FMS_LOAD;
```



## Members

<dl> <dt>

**dwSize**
</dt> <dd>

Type: **DWORD**

</dd> <dd>

The length, in bytes, of the structure.

</dd> <dt>

**szMenuName**
</dt> <dd>

Type: **TCHAR\[MENU\_TEXT\_LEN\]**

</dd> <dd>

A null-terminated name for a menu item that appears on the menu bar in File Manager.

</dd> <dt>

**hMenu**
</dt> <dd>

Type: **HMENU**

</dd> <dd>

The identifier of the pop-up menu added to the menu bar in File Manager.

</dd> <dt>

**wMenuDelta**
</dt> <dd>

Type: **UINT**

</dd> <dd>

The menu item delta value. To avoid conflicts with its own menu items, File Manager renumbers the menu item identifiers in the pop-up menu identified by the **hMenu** member by adding this delta value to each identifier. An extension DLL that must modify a menu item must identify the item by adding the delta value to the menu item's identifier. The value of this member can vary from session to session.

</dd> </dl>

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                         |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Wfext.h</dt> </dl> |



## See also

<dl> <dt>

[**FMExtensionProc**](fmextensionproc.md)
</dt> </dl>

 

 



