---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wsscomputeraccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssComputerAccess
---

# Remove-WssComputerAccess

## SYNOPSIS
Removes a relationship between a user and a computer for Remote Web Access.

## SYNTAX

```
Remove-WssComputerAccess -ComputerName <String> [-UserName <String>] [-GroupName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssComputerAccess** cmdlet removes a relationship between a user account and a computer used for Remote Web Access.
After you remove the relationship, a user cannot access a computer by means of Remote Web Access.
You can use the Add-WssComputerAccess cmdlet to create a relationship for use with Remote Web Access.

## EXAMPLES

### Example 1: Remove computer access for a user
```
PS C:\> Remove-WssComputerAccess -ComputerName "Workstation033" -UserName "SarahJones"
```

This command deletes a relationship between the user SarahJones and the computer named Workstation033.
The user can no longer use Remote Web Access to connect to this computer.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies the name of a group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user name of an account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssComputerAccess](./Add-WssComputerAccess.md)

