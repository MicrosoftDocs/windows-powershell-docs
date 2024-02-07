---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gpregistryvalue?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GPRegistryValue
---

# Set-GPRegistryValue

## SYNOPSIS

Configures one or more registry-based policy settings under either Computer Configuration or User Configuration in a GPO.

## SYNTAX

### ByGUID (Default)

```
Set-GPRegistryValue -Guid <Guid> -Key <String> [-ValueName <String[]>] [-Value <PSObject>]
 [-Type <RegistryValueKind>] [-Domain <String>] [-Server <String>] [-Additive] [-Disable]
 [-ValuePrefix <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName

```
Set-GPRegistryValue [-Name] <String> -Key <String> [-ValueName <String[]>] [-Value <PSObject>]
 [-Type <RegistryValueKind>] [-Domain <String>] [-Server <String>] [-Additive] [-Disable]
 [-ValuePrefix <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-GPRegistryValue` cmdlet configures a registry-based policy setting under either Computer
Configuration or User Configuration in a Group Policy Object (GPO). The policy setting configures
keys or values in the registry on the client computer when the GPO is applied.

You can specify the GPO by name or by its GUID, or you can pipe a GPO object to the cmdlet. You can
also pipe a PolicyRegistrySetting object to the cmdlet.

You can configure registry-based policy settings for:

- One or more registry values by passing the **Key**, **ValueName**, **Value**, and **Type**
  parameters. For multiple registry values, pass a comma-separated list for both the **ValueName**
  and **Value** parameters. When you specify multiple registry values, only the `String` and
  `ExpandString` data types are supported.

- A list of one or more registry values that share the same name prefix by passing the **Key** and
  **Type** parameters, and a single value or a comma-separated list for the **Value** parameter. You
  can optionally specify the value name prefix by using the **ValuePrefix** parameter. Only the
  `String` and `ExpandString` data types are supported for lists.

You can use the **Additive** parameter to ensure that existing registry values for the key are not
overwritten by the new policy setting when the GPO is applied.

You can also delete registry values on a client when the GPO is applied by disabling a policy
setting with the **Disable** parameter. You can disable:

- All the registry values under a specified registry key by passing the **Key** parameter. No
  subkeys, or their values, are deleted on the client.

- A single registry value by passing the **Key** parameter and the **ValueName** parameter.

- Multiple registry values by passing the **Key** parameter and a comma-separated list for the
  **ValueName** parameter.

## EXAMPLES

### Example 1: Configure a registry-based policy setting for a registry value

```powershell
$params = @{
    Name      = 'TestGPO'
    Key       = 'HKCU\Software\Policies\Microsoft\Windows\Control Panel\Desktop'
    ValueName = 'ScreenSaveTimeOut'
    Value     = 900
    Type      = 'DWORD'
}
Set-GPRegistryValue @params
```

```Output
DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 35c12ab3-956c-45d5-973b-46b17d225f47 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/24/2009 4:41:03 PM 
ModificationTime : 2/25/2009 12:42:00 PM 
UserVersion      : AD Version: 3, SysVol Version: 3 
ComputerVersion  : AD Version: 34, SysVol Version: 34 
WmiFilter        :
```

This command configures a registry-based policy setting for the registry value
`HKCU\Software\Policies\Microsoft\Windows\Control ScreenSaverTimeOut` with a value of `900` and a
data type of `DWord`. This policy setting sets the Screen Saver timeout to 900 seconds (15 minutes)
when Group Policy is applied on the client.

### Example 1: Configure a registry-based policy settings for multiple registry values

```powershell
$params = @{
    Name      = 'TestGPO'
    Key       = 'HKCU\Software\Policies\Microsoft\ExampleKey'
    ValueName = 'ValueOne', 'ValueTwo', 'ValueThree'
    Value     = 'String 1', 'String 2', 'String 3'
    Type      = 'String'
}
Set-GPRegistryValue @params
```

This command configures registry-based policy settings to set three registry values. The policy
settings are configured in the `User` Configuration section of the GPO. When the GPO is applied on
the client, the following registry values are set:

`HKCU\Software\Policies\Microsoft\ExampleKey ValueOne` `String 1`

`HKCU\Software\Policies\Microsoft\ExampleKey ValueTwo` `String 2`

`HKCU\Software\Policies\Microsoft\ExampleKey ValueThree` `String 3`

### Example 3: Configure a registry-based policy setting to set a list of registry values

```powershell
$params = @{
    Name        = 'TestGPO'
    Key         = 'HKCU\Software\Policies\Microsoft\ExampleKey'
    ValuePrefix = 'MyValue'
    Type        = 'String'
    Value       = 'String 1', 'String 2', 'String 3'
}
Set-GPRegistryValue @params
```

This command configures a registry-based policy setting to set a list of three registry values. The
policy settings are configured in the `User` Configuration section of the GPO. Because the
**Additive** parameter is not specified, when the GPO is applied on the client any list values under
the key are deleted -- then, the following registry values are set:

`HKCU\Software\Policies\Microsoft\ExampleKey MyValue1` `String 1`

`HKCU\Software\Policies\Microsoft\ExampleKey MyValue2` `String 2`

`HKCU\Software\Policies\Microsoft\ExampleKey MyValue3` `String 3`

If you specify the **Additive** parameter, the list values are added to the existing list values on
the client when the GPO is applied. The actual value names assigned to the list values depends on
the number of existing list values on the client.

### Example 4: Disable registry-based policy settings for specific registry values

```powershell
$params = @{
    Disable   = $true
    Name      = 'TestGPO'
    Key       = 'HKCU\Software\Policies\Microsoft\ExampleKey'
    ValueName = 'ValueOne', 'ValueTwo', 'ValueThree'
}
Set-GPRegistryValue @params
```

This command `disables` the registry-based policy settings, in the `User` Configuration section, for
the specified registry values. When the GPO is applied on the client, the registry values are
deleted from the registry on the client.

### Example 5: Disable registry-based policy settings for a specific registry key

```powershell
Set-GPRegistryValue -Disable -Name 'TestGPO' -Key 'HKCU\Software\Policies\Microsoft\ExampleKey'
```

This command `disables` the registry-based policy setting, in the `User` Configuration section, for
the specified registry key. When the GPO is applied on the client, all first level values will be
deleted from the registry key. Subkeys and their values are not modified.

## PARAMETERS

### -Additive

Indicates that registry values should be appended to existing values under the key when the GPO is
applied on a client.

By default, when Group Policy is processed on a client, existing values under a registry key are
deleted before any new values are written to the registry. By using the **Additive** parameter for a
registry-based policy setting, you can specify that the new value should be added to the registry
key without deleting the existing values.

You cannot specify the **Disable** parameter with this parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable

Indicates that the cmdlet disables the registry-based policy setting.

You can disable a policy setting for a registry key or value:

- For a registry key, specify the **Key** parameter without the **ValueName** parameter. When the GPO
  is applied on the client, all of the values directly under the key are removed from the registry.
  The key itself is not removed from the registry, nor are any of its subkeys, or their values,
  removed.

- For a registry value, specify the **Key** parameter together with the **ValueName** parameter.
  When the GPO is applied on the client, only the specified value is removed from the registry.

To remove a policy setting from a GPO without affecting existing registry keys or values on a client
when Group Policy is processed, use the `Remove-GPRegistryValue` cmdlet.

You cannot specify the **Additive**, **Type**, **Value**, or **ValuePrefix** parameters with the
**Disable** parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Set-GPRegistryValue` cmdlet, the GPO in which to configure the registry-based policy
setting must exist in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to the **Domain** parameter by its built-in alias, **DomainName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO in which to configure the registry-based policy setting by its globally unique
identifier (GUID). The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key

Specifies the registry key for the registry-based policy setting; for instance,
`HKLM\Software\Policies\Microsoft\Windows NT\DNSClient`.

The key must be in one of the two following registry hives:

- `HKEY_LOCAL_MACHINE` (HKLM) for a registry-based policy setting in Computer Configuration.

- `HKEY_CURRENT_USER` (HKCU) for a registry-based policy setting in User Configuration.

You can also refer to the Key parameter by its built-in alias, FullKeyPath.

```yaml
Type: System.String.String
Parameter Sets: (All)
Aliases: FullKeyPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO in which to configure the registry-based policy setting by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Specifies the data type for the registry-based policy setting.

The acceptable values for this parameter are:

- String
- ExpandString
- Binary
- DWord
- MultiString
- QWord

For more information about these data types, see
[Microsoft.Win32.RegistryValueKind Enumeration](https://go.microsoft.com/fwlink/?LinkID=143266) in
the MSDN library.

Only the following data types are supported for list values: `String` and `ExpandString`.

You must specify this parameter when you configure a policy setting to set a registry value.
You cannot specify this parameter with the **Disable** parameter.

The following values are permitted for this object type.

```yaml
Type: RegistryValueKind
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, String, ExpandString, Binary, DWord, MultiString, QWord, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Specifies the value data for the registry-based policy setting. You can specify a single value or an
array of values. Use a comma-separated list to specify more than one value. Only the `String` and
`ExpandString` data types are supported for an array of values.

At a minimum, you must specify this parameter together with the *Type* and **Key** parameters to
configure a policy setting to set a registry value. You cannot specify this parameter with the
**Disable** parameter.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValueName

Specifies a value name or an array of value names for the registry-based policy setting. For
instance, the registry key `HKLM\Software\Policies\Microsoft\Windows NT\DNSClient` can have a
registry value with the following value name: `UseDomainNameDevolution`. Use a comma-separated list
to specify more than one value name. Only the `String` and `ExpandString` data types are supported
for an array of values.

You cannot specify this parameter with the **ValuePrefix** parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValuePrefix

Specifies a value name prefix for a registry-based policy setting for a list of registry values.

Configures a policy setting that creates the following registry values when Group Policy is applied
on the client:

`HKLM\SOFTWARE\Policies\ExampleKey ExValue1` `100`

`HKLM\SOFTWARE\Policies\ExampleKey ExValue2` `200`

`HKLM\SOFTWARE\Policies\ExampleKey ExValue3` `300`

Only the `String` and `ExpandString` data types are supported with the **ValuePrefix** parameter.

You cannot specify this parameter with the **ValueName** parameter or the **Disable** parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo or Microsoft.GroupPolicy.PolicyRegistrySetting

You can pipe a GPO (in which to configure a registry-based policy setting), or a
**PolicyRegistrySetting** object that represents a registry-based policy setting (to configure in a
specified GPO) to this cmdlet. Collections that contain GPOs from different domains are not
supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO in which the registry-based policy setting has been configured.

## NOTES

* The hive of the registry key that you specify, `HKEY_LOCAL_MACHINE` (HKLM) or `HKEY_CURRENT_USER`
  (HKCU), determines whether the registry-based policy setting is in Computer Configuration or User
  Configuration.

  You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For instance, the domain of the user who started the session by opening Windows
  PowerShell from the Program Files menu, or the domain of a user that is specified in a runas
  command. However, computer startup and shutdown scripts run under the context of the LocalSystem
  account. The LocalSystem account is a built-in local account, and it accesses network resources
  under the context of the computer account. Therefore, when this cmdlet is run from a startup or
  shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPRegistryValue](./Get-GPRegistryValue.md)

[Remove-GPRegistryValue](./Remove-GPRegistryValue.md)

