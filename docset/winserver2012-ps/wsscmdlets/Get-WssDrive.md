---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssdrive?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

