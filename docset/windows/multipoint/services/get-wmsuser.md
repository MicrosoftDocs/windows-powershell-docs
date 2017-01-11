---
author: brianlic-msft
description: 
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WmsUser
ms.assetid: EA8744D5-B53A-4C3E-AE80-5D4A9252E6FB
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
PS C:\>Get-WmsUser -All
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
None.

## OUTPUTS

###  
This cmdlet returns a **WmsUser** collection as **PSObject** collection.

## NOTES

## RELATED LINKS

[New-WmsUser]()

[Remove-WmsUser]()

[Set-WmsUser](./Set-WmsUser.md)

