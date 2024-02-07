---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmsuser?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsUser
---

# Get-WmsUser

## SYNOPSIS
Gets local user account information.

## SYNTAX

### GetUser
```
Get-WmsUser -Name <String> [-Server <String>] [<CommonParameters>]
```

### GetAllUsers
```
Get-WmsUser [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsUser** cmdlet gets local user account information for a specified user or all users.

## EXAMPLES

### Example 1: Get all local user account information
```
PS C:\> Get-WmsUser -All
Name         : Administrator
Password     :
FullName     :
Description  : Built-in account for administering the computer/domain
UserType     : Administrator
ComputerName : Test1
Name         : Guest
Password     :
FullName     :
Description  : Built-in account for guest access to the computer/domain
UserType     : Standard
ComputerName : Test1
```

This command gets all local user account information.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: GetAllUsers
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the user to get.

```yaml
Type: String
Parameter Sets: GetUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsUser

## NOTES

## RELATED LINKS

[New-WmsUser]()

[Remove-WmsUser]()

[Set-WmsUser](./Set-WmsUser.md)

