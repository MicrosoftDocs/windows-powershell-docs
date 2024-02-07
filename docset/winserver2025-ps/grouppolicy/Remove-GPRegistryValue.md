---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/remove-gpregistryvalue?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-GPRegistryValue
---

# Remove-GPRegistryValue

## SYNOPSIS

Removes one or more registry-based policy settings from either Computer Configuration or User Configuration in a GPO.

## SYNTAX

### GetByGUID (Default)

```
Remove-GPRegistryValue [-Guid] <Guid> [-Key] <String> [[-ValueName] <String>] [[-Domain] <String>]
 [[-Server] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetByName

```
Remove-GPRegistryValue [-Name] <String> [-Key] <String> [[-ValueName] <String>] [[-Domain] <String>]
 [[-Server] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-GPRegistryValue` cmdlet removes one or more registry-based policy settings from either
Computer Configuration or User Configuration in a Group Policy Object (GPO). You can specify the GPO
by its display name or by its GUID.

You can specify either a key or a value:

- If you specify a key, registry-based policy settings that configure any of its first-level values
  are removed. However, if there are registry-based policy settings that configure any subkeys or
  their values, an error occurs and no policy settings are removed, including those for first-level
  values of the key. For a key, specify the **Key** parameter without the *ValueName* parameter.

- If you specify a value, the registry-based policy setting that configures that registry value is
  removed. For a value, specify the **Key** parameter without the *ValueName* parameter.

This cmdlet can take input from the pipeline:

- You can pipe GPO objects to this cmdlet to remove a specified registry-based policy setting from
  one or more GPOs.

- You can pipe **PolicyRegistrySetting** objects to this cmdlet to remove one or more registry-based
  policy settings from a specified GPO.

## EXAMPLES

### Example 1: Remove a registry-based policy setting under the specified registry key

```powershell
$params = @{
    Name      = 'TestGPO'
    Key       = 'HKCU\Software\Policies\Microsoft\Windows\Control Panel\Desktop'
    ValueName = 'ScreenSaveTimeOut'
}
Remove-GPRegistryValue @params
```

```Output
DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 35c12ab3-956c-45d5-973b-46b17d225f47 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/24/2009 4:41:03 PM 
ModificationTime : 2/25/2009 12:45:52 PM 
UserVersion      : AD Version: 4, SysVol Version: 4 
ComputerVersion  : AD Version: 34, SysVol Version: 34 
WmiFilter        :
```

This command removes the registry-based policy setting for the registry value
`HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Control Panel\Desktop ScreenSaveTimeout` from
the GPO named `TestGPO`. The registry value is no longer modified when the GPO is applied on a
client. Removing a policy setting does not delete the registry value on a client. To delete the
registry value when the GPO is applied on a client, you must disable the policy setting by using the
`Set-GPRegistryValue` cmdlet.

### Example 2: Remove all the registry-based policy settings under the specified registry key

```powershell
Remove-GPRegistryValue -Name "TestGPO" -Key "HKCU\Software\Policies\Microsoft\ExampleKey"
```

This command removes all the registry-based policy settings that configure first-level registry
values under the key `HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey` from `User`
Configuration in the GPO named `TestGPO`. If there are registry-based policy settings in `User`
Configuration that configure registry values for any subkeys of this key, an error occurs and no
first-level policy settings are removed.

## PARAMETERS

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

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Remove-GPRegistryValue` cmdlet, the GPO from which to remove the registry-based policy setting must exist in this domain.

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
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO from which to remove the registry-based policy setting by its globally unique
identifier (GUID). The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: GetByGUID
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key

Specifies a registry key for which to remove one or more registry-based policy settings (for
instance: `HKLM\Software\Policies\Microsoft\WindowsNT\DNSClient\UseDomainNameDevolution`).

The key must be in one of the two following registry hives:

- `HKEY_LOCAL_MACHINE` (HKLM) for a registry-based policy setting in Computer Configuration.

- `HKEY_CURRENT_USER` (HKCU) for a registry-based policy setting in User Configuration.

The Key parameter can be specified with or without the ValueName parameter:

- If the **ValueName** parameter is specified, the registry-based policy setting that configures
  that registry value is removed.

- If the **ValueName** parameter is not specified, all registry-based policy settings that configure
  any of the first-level values of the registry key are removed. If there are registry-based policy
  settings that configure any subkeys or their values, an error occurs.

You can also refer to the Key parameter by its built-in alias, FullKeyPath.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullKeyPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO from which to remove the registry-based policy setting by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: GetByName
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName

Specifies the name of the registry value for which to remove the registry-based policy setting. If
you specify the **ValueName** parameter, you must also specify the **Key** parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.GroupPolicy.Gpo, Microsoft.GroupPolicy.PolicyRegistrySetting

You can pipe a GPO from which to remove a registry-based policy setting, or a
**PolicyRegistrySetting** object that represents a registry-based policy setting. Collections that
contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO from which the registry-based policy setting (or settings) has been
removed.

## NOTES

* The hive of the registry key that you specify -- `HKEY_LOCAL_MACHINE` (HKLM) or
  `HKEY_CURRENT_USER` (HKCU) indicates whether the registry-based policy setting is removed from
  Computer Configuration or User Configuration.

  If a value for the registry key cannot be located (the registry key is not configured) or if
  subkeys are present, an error occurs and a corresponding error message is displayed.

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

[Set-GPRegistryValue](./Set-GPRegistryValue.md)

