---
description: The Set-CIPolicySetting cmdlet modifies the SecureSettings within the Code Integrity policy.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 10/20/2021
online version: https://learn.microsoft.com/powershell/module/configci/set-cipolicysetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CIPolicySetting
---

# Set-CIPolicySetting

## SYNOPSIS
Modifies the SecureSettings within the Code Integrity policy.

## SYNTAX

### Set
```
Set-CIPolicySetting [-FilePath] <String> -Provider <String> -Key <String> -ValueName <String>
 -ValueType <String> -Value <String> [<CommonParameters>]
```

### Delete
```
Set-CIPolicySetting [-FilePath] <String> -Provider <String> -Key <String> -ValueName <String> [-Delete]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-CIPolicySetting** cmdlet modifies the Secure Settings within a Code Integrity policy.
Specify the .xml file of the policy to modify.
Secure Settings are queried by Windows APIs to set security behaviors.

## EXAMPLES

### Example 1: Set the Code Integrity policy
```powershell
Set-CIPolicySetting -FilePath C:\Policies\WDAC_policy.xml -Key "{12345678-9abc-def0-1234-56789abcdef0}" -Provider WSH -Value $True -ValueName EnterpriseDefinedClsId -ValueType Boolean
```

This command sets the Code Integrity policy to allow for the specified **Provider**, **Key** and **ValueName**.

## PARAMETERS

### -Delete
Indicates that this cmdlet removes a Secure Setting from the Code Integrity policy identified by **Provider**, **Key** and **ValueName**.

```yaml
Type: SwitchParameter
Parameter Sets: Delete
Aliases: d

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the full path of the policy .xml file.

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

### -Key
Specifies the Secure Setting key.
The key is the GUID of the program to run in this format:

{33333333-4444-4444-1616-161616161616}

```yaml
Type: String
Parameter Sets: (All)
Aliases: k

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Provider
Specifies the Secure Setting provider.
The provider is the platform on which the code runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: p

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Specifies the Secure Setting value.
Specify `$True` to allow or `$False` to deny.

Specify $False, or deny, only for base policies, not supplemental policies.

```yaml
Type: String
Parameter Sets: Set
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName
Specifies the value name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: vn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueType
Specifies the value type. Valid values are:

- Boolean
- DWord
- Binary
- String

```yaml
Type: String
Parameter Sets: Set
Aliases: vt
Accepted values: Boolean, DWord, Binary, String

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-CIPolicy](New-CIPolicy.md)

[New-CIPolicyRule](New-CIPolicyRule.md)
