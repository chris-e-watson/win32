---
title: Editing Streams
description: Editing Streams
ms.assetid: '1653ff90-e96a-43fc-b509-6d8ad4ddcd2c'
keywords: ["CreateEditableStream function", "EditStreamCut function", "EditStreamCopy function", "EditStreamPaste function", "EditStreamClone function", "EditStreamSetInfo function"]
---

# Editing Streams

You can create a stream that you can edit by using the [**CreateEditableStream**](createeditablestream.md) function. This function initializes the environment for editing a stream. This includes creating an interface to the new stream, and internal edit tables that track changes made to the stream. **CreateEditableStream** returns a stream pointer to an editable stream that is required by other stream-editing functions. The editable stream pointer can also be used by other AVIFile functions that accept stream pointers.

You can cut one or more samples from an editable stream by using the [**EditStreamCut**](editstreamcut.md) function. To remove samples from the editable stream, this function adds an entry to the edit table. The function then places a copy of the cut samples in a new temporary stream whose interface pointer is returned in a variable.

You can copy one or more samples from an editable stream into a temporary stream by using the [**EditStreamCopy**](editstreamcopy.md) function. **EditStreamCopy** places copies of the samples in a new temporary stream whose interface pointer is returned in a variable.

You can copy one or more samples from a stream and paste them into an editable stream by using the [**EditStreamPaste**](editstreampaste.md) function. To insert the samples at the specified position, this function adds an entry in the edit table of the target editable stream.

You can duplicate an editable stream by using the [**EditStreamClone**](editstreamclone.md) function. This function returns a pointer to the stream interface of the new stream. You can copy these streams to the clipboard or use them to maintain a trail of edits made to a stream.

You can change several of the characteristics of an editable stream by using the [**EditStreamSetInfo**](editstreamsetinfo.md) function. This function updates the priority setting, language, scale and rate, starting time, quality setting, destination rectangle dimensions and coordinates, and the textual description of the stream. These items are stored in the [**AVISTREAMINFO**](avistreaminfo-struct.md) structure associated with the editable stream.

You can also change the textual description of an editable stream by using the [**EditStreamSetName**](editstreamsetname.md) function. This function updates the **szName** member of the **AVISTREAMINFO** structure associated with the editable stream.

The editing functions work on streams. You need to cut and paste each stream individually, and then use the [**AVIMakeFileFromStreams**](avimakefilefromstreams.md) function to create a new file pointer.

> [!Note]  
> The edit tables in an editable stream maintain all the changes for a stream. The source stream is never changed.

 

 

 



