---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 9161E619-5D1F-4880-9F4C-7F78F411491C
manager: dansimp
---

# New-OBPagingContext

## SYNOPSIS
Creates a new OBPagingContext object that is used in the Get-OBRecoverableItem cmdlet during searching and browsing through paginated recoverable items.

## SYNTAX

```
New-OBPagingContext
```

## DESCRIPTION
The **New-OBPagingContext** cmdlet creates a new OBPagingContext object that is used in the Get-OBRecoverableItem cmdlet for to enable searching and browsing of paginated recoverable items.
Providing the OBPagingContext object will intelligently retrieve paginated files and folders within the destination folder.

This cmdlet only needs to be called once during a session and the OBPagingContext object will be automatically refreshed when browsing or searching under different folders. 
In the Get-OBRecoverableItem cmdlet if the OBPagingContext object is not supplied the cmdlet would page as necessary for the cmdlet to retrieve and return all items listed recursively in the folder.

While searching and browsing as part of the Get-OBRecoverableItem cmdlet; if the OBPagingContext object is supplied, then re-running the same cmdlet would then fetch the 2nd page, and 3rd page, and so on until the last page is retrieved.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-OBPagingContext
```

This example creates a new paging context.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPagingContext

## NOTES

## RELATED LINKS

[Get-OBRecoverableItem](./Get-OBRecoverableItem.md)

