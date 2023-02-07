---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/enable-securitypolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-SecurityPolicy

## SYNOPSIS
Enables predefined security group policies.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-SecurityPolicy [-AllPolicy]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-SecurityPolicy -Policy <String[]>
```

## DESCRIPTION
The **Enable-SecurityPolicy** cmdlet enables pre-defined group policies for security features.
The cmdlet enables group policies for Windows Defender, Windows Update, and Windows Firewall.

## EXAMPLES

### Example 1: Enable predefined security group policies
```
PS C:\> Enable-SecurityPolicy -Policy "WindowsUpdate"
```

This command enables the security group policy for Windows Update.

## PARAMETERS

### -AllPolicy
Indicates that the cmdlet enables all pre-defined group policies for Windows Update, Windows Firewall, and Windows Defender.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies an array of group policies to enable.
The acceptable values for this parameter are:

- WindowsUpdate
- Firewall
- WindowsDefender

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-SecurityPolicy](./Disable-SecurityPolicy.md)

