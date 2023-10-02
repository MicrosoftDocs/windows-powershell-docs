---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/disable-securitypolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-SecurityPolicy

## SYNOPSIS
Disables predefined security group policies.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-SecurityPolicy [-AllPolicy]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-SecurityPolicy -Policy <String[]>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Enable-SecurityPolicy](./Enable-SecurityPolicy.md)

