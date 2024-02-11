---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/new-wmsuser?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WmsUser
---

# New-WmsUser

## SYNOPSIS
Modifies a Windows MultiPoint Server user account.

## SYNTAX

```
New-WmsUser [-Credential] <PSCredential> [-UserType] <UserTypePS> [[-FullName] <String>]
 [[-Description] <String>] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsUser** cmdlet updates a local user on the current Windows MultiPoint Server system.

## EXAMPLES

### Example 1: Modify a user account
```
PS C:\> Set-WmsUser -Name "Student01" -Description "New Student" -FullName "Patti Fuller"
```

This command updates a user account with the description New Student, the name as Student01, and the full name as Patti Fuller.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object.
Use the **Get-Credential** cmdlet to get a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullName
Specifies the full name of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### -UserType
Specifies the user type.
The acceptable values for this parameter are:

- Administrator
- Standard
- DashboardUser

```yaml
Type: UserTypePS
Parameter Sets: (All)
Aliases:
Accepted values: Administrator, Standard, DashboardUser

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-WmsUser]()

[Remove-WmsUser]()

