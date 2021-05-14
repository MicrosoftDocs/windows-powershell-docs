---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/disable-securitypolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-SecurityPolicy
---

# Disable-SecurityPolicy

## SYNOPSIS
Disables predefined security group policies.

## SYNTAX

### All
```
Disable-SecurityPolicy [-AllPolicy] [<CommonParameters>]
```

### Specific
```
Disable-SecurityPolicy -Policy <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SecurityPolicy** cmdlet disables pre-defined group policies for security features.
The cmdlet disables group policies for Windows Defender, Windows Update, and Windows Firewall.

## EXAMPLES

### Example 1: Disable predefined security group policies
```
PS C:\> Disable-SecurityPolicy -Policy "WindowsUpdate"
```

This command disables the security group policy for Windows Update.

## PARAMETERS

### -AllPolicy
Indicates that the cmdlet disables all pre-defined group policies for Windows Update, Windows Firewall, and Windows Defender.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies an array of group policies to disable.
The acceptable values for this parameter are:

- WindowsUpdate
- Firewall
- WindowsDefender

```yaml
Type: String[]
Parameter Sets: Specific
Aliases: 
Accepted values: WindowsUpdate, Firewall, WindowsDefender

Required: True
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

[Enable-SecurityPolicy](./Enable-SecurityPolicy.md)

