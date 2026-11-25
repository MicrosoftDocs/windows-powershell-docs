---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/set-ruleoption?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RuleOption
---

# Set-RuleOption

## SYNOPSIS
Modifies rule options in a Code Integrity policy.

## SYNTAX

### Action
```
Set-RuleOption [-Delete] [-FilePath] <String> [-Option] <Int32> [<CommonParameters>]
```

### Help
```
Set-RuleOption [-Help] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RuleOption** cmdlet modifies rule options in a Code Integrity policy.
Rule options appear under the **Rules** property in the .xml policy file.
To see the available rule options and their indexes, specify the **Help** parameter.
This cmdlet adds the option that you specify by index.
To remove a rule option, specify the **Delete** parameter.

## EXAMPLES

### Example 1: Remove a rule option
```
The first command displays the contents of the policy. This example shows only the first few lines of the policy, which include the **Rules** property. One of the options displayed is Enabled:Audit Mode.
PS C:\> Get-Content -Path '.Policy.xml'
<?xml version="1.0" encoding="utf-8"?>
<SiPolicy xmlns="urn:schemas-microsoft-com:sipolicy">
  <VersionEx>10.0.0.0</VersionEx>
  <PolicyTypeID>{A244370E-44C9-4C06-B551-F6016E563076}</PolicyTypeID>
  <PlatformID>{2E07F7E4-194C-4D20-B7C9-6F44A6C5A234}</PlatformID>
  <Rules>
    <Rule>
      <Option>Enabled:Unsigned System Integrity Policy</Option>
    </Rule>
    <Rule>
      <Option>Enabled:Audit Mode</Option>
    </Rule>
    <Rule>
      <Option>Enabled:Advanced Boot Options Menu</Option>
    </Rule>
    <Rule>
      <Option>Enabled:UMCI</Option>
    </Rule>
  </Rules>

The second command removes the Enabled:Audit Mode from Policy.xml.The final command displays the contents of the policy again. Enabled:Audit Mode is no longer part of the policy.
PS C:\> Set-RuleOption -FilePath '.\Policy.xml' -Option 3 -Delete
PS C:\> Get-Content -Path '.Policy.xml'
<?xml version="1.0" encoding="utf-8"?>
<SiPolicy xmlns="urn:schemas-microsoft-com:sipolicy">
  <VersionEx>10.0.0.0</VersionEx>
  <PolicyTypeID>{A244370E-44C9-4C06-B551-F6016E563076}</PolicyTypeID>
  <PlatformID>{2E07F7E4-194C-4D20-B7C9-6F44A6C5A234}</PlatformID>
  <Rules>
    <Rule>
      <Option>Enabled:Unsigned System Integrity Policy</Option>
    </Rule>
    <Rule>
      <Option>Enabled:Advanced Boot Options Menu</Option>
    </Rule>
    <Rule>
      <Option>Enabled:UMCI</Option>
    </Rule>
  </Rules>
```

This example removes Enabled:Audit Mode from a policy.

## PARAMETERS

### -Delete
Indicates that this cmdlet removes the rule option that the **Option** parameter specifies.

```yaml
Type: SwitchParameter
Parameter Sets: Action
Aliases: d

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
Parameter Sets: Action
Aliases: f

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Help
Indicates that this cmdlet displays the list of available options and their indexes.

```yaml
Type: SwitchParameter
Parameter Sets: Help
Aliases: h

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Option
Specifies the index of the rule option that this cmdlet modifies.
Specify the **Help** parameter for option information. Refer to [WDAC Policy Rule Options](/windows/security/threat-protection/windows-defender-application-control/select-types-of-rules-to-create#windows-defender-application-control-policy-rules) for more detailed descriptions of each option.

```yaml
Type: Int32
Parameter Sets: Action
Aliases: o

Required: True
Position: 1
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

[Set-HVCIOptions](./Set-HVCIOptions.md)
