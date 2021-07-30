---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssdriveinuse?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssDriveInUse
---

# Get-WssDriveInUse

## SYNOPSIS
Checks whether a drive is in use.

## SYNTAX

```
Get-WssDriveInUse [-Drive] <Drive> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDriveInUse** cmdlet checks whether a drive is in use.
To obtain a **Drive** object to check, use the Get-WssDrive cmdlet.

## EXAMPLES

### Example 1: Check whether a drive is in use
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13
PS C:\> Get-WssDriveInUse -Drive $Drive
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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.DriveInUseRequest
This cmdlet generates a drive in use indicator.

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

