---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 9C4607C0-4DFD-408D-AA76-E40F914CC7B5
manager: dansimp
---

# Get-WssDriveInUse

## SYNOPSIS
Checks whether a drive is in use.

## SYNTAX

```
Get-WssDriveInUse [-Drive] <Drive>
```

## DESCRIPTION
The **Get-WssDriveInUse** cmdlet checks whether a drive is in use.
To obtain a **Drive** object to check, use the Get-WssDrive cmdlet.

## EXAMPLES

### Example 1: Check whether a drive is in use
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13 PS C:\> Get-WssDriveInUse -Drive $Drive
```

This example checks whether a specified drive is in use.
The first command uses the Get-WssDrive cmdlet to get a **Drive** object that has the specified GUID, and stores it in the **$Drive** variable.

The second command checks whether the **Drive** object stored in the **$Drive** variable is in use.

## PARAMETERS

### -Drive
Specifies a **Drive** object.
To obtain a **Drive** object, use the Get-WssDrive cmdlet.

```yaml
Type: Drive
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### DriveInUseRequest

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

