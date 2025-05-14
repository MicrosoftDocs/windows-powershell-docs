---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/set-hvcioptions?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HVCIOptions
---

# Set-HVCIOptions

## SYNOPSIS
Modifies hypervisor Code Integrity options for a policy.

## SYNTAX

### Options
```
Set-HVCIOptions [-Enabled] [-Strict] [-DebugMode] [-DisableAllowed] [-FilePath] <String> [<CommonParameters>]
```

### None
```
Set-HVCIOptions [-None] [-FilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-HVCIOptions** cmdlet modifies hypervisor Code Integrity options for a policy.
The policy stores these options in the **HvciOptions** property of the policy.
You can specify any combination of the following values:

- Enabled
- DebugMode
- Strict

## EXAMPLES

### Example 1: Assign the Strict option
```
PS C:\> Set-HVCIOptions -Strict -FilePath '.\Policy.xml'
PS C:\> Get-Content -Path '.Policy.xml'
    <CiSigner SignerId="ID_SIGNER_S_21" />
  </CiSigners>
  <HvciOptions>2</HvciOptions>
</SiPolicy>
```

The first command assigns the Strict option in Policy.xml.

The second command displays the contents of the policy.
This example shows the last few lines of the policy, which include the **HvciOptions** property.
It now has a value of 2.

## PARAMETERS

### -DebugMode
Indicates that this cmdlet turns on DebugMode in the policy.

```yaml
Type: SwitchParameter
Parameter Sets: Options
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAllowed
Indicates that this cmdlet allows for HVCI to be disabled by the user outside of the Code Integrity policy enablement method.

```yaml
Type: SwitchParameter
Parameter Sets: Options
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates that this cmdlet turns on Enabled in the policy.

```yaml
Type: SwitchParameter
Parameter Sets: Options
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the path of the policy .xml file that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -None
Indicates that this cmdlet removes all hypervisor Code Integrity options from the policy.
In the policy itself, **HvciOptions** takes a value of zero (0).

```yaml
Type: SwitchParameter
Parameter Sets: None
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strict
Indicates that this cmdlet turns on Strict in the policy.

```yaml
Type: SwitchParameter
Parameter Sets: Options
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-RuleOption](./Set-RuleOption.md)

