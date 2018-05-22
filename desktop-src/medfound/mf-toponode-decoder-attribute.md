﻿---
Description: 'Specifies whether a topology node's underlying object is a decoder.'
ms.assetid: 'b6d576dc-b12f-49bf-b938-db2c629df400'
title: 'MF\_TOPONODE\_DECODER attribute'
---

# MF\_TOPONODE\_DECODER attribute

Specifies whether a topology node's underlying object is a decoder.

## Data type

**UINT32**

Treat as a Boolean value.

## Remarks

This attribute applies to all node types.

If the value of this attribute is nonzero, the node's underlying object is a decoder.

The topology loader sets this attribute when it creates a decoder node. An application should set this attribute if the application manually adds a decoder to the topology.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Mfidl.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[**IMFAttributes::GetUINT32**](imfattributes-getuint32.md)
</dt> <dt>

[**IMFAttributes::SetUINT32**](imfattributes-setuint32.md)
</dt> <dt>

[**IMFTopologyNode**](imftopologynode.md)
</dt> <dt>

[Topology Node Attributes](topology-node-attributes.md)
</dt> </dl>

 

 



