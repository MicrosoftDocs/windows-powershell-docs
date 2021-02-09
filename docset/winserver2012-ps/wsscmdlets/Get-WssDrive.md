---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 485624A7-B40A-47DF-AF78-B12EC35B90DA
manager: dansimp
---

# Get-WssDrive

## SYNOPSIS
Gets an object that represents a drive.

## SYNTAX

```
Get-WssDrive [-ID <Guid>]
```

## DESCRIPTION
The **Get-WssDrive** cmdlet gets an object that represents a drive.
Specify a GUID for a specific drive.
If you do not specify a GUID, the cmdlet gets **Drive** objects for all the drives for the current server.

## EXAMPLES

### Example 1: Get all drives
```
PS C:\> Get-WssDrive
```

This command gets **Drive** objects for all the drives for the current server.

## PARAMETERS

### -ID
Specifies the GUID for a drive.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Drive

## NOTES

## RELATED LINKS

[Set-WssDrive](./Set-WssDrive.md)

[Test-WssDrive](./Test-WssDrive.md)

