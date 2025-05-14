---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/remove-gpprefregistryvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-GPPrefRegistryValue
---

# Remove-GPPrefRegistryValue

## SYNOPSIS

Removes one or more Registry preference items from either Computer Configuration or User
Configuration in a GPO.

## SYNTAX

### GetByGUID (Default)

```
Remove-GPPrefRegistryValue -Guid <Guid> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Order <Int32>] [-Domain <String>] [[-Server] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### GetByName

```
Remove-GPPrefRegistryValue [-Name] <String> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Order <Int32>] [-Domain <String>] [[-Server] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Remove-GPPrefRegistryValue` cmdlet removes one or more Registry preference items from either
Computer Configuration or User Configuration in a GPO. You must specify the **Context** parameter
for the User or Computer to indicate whether to remove the Registry preference item from Computer
Configuration or User Configuration. You can specify the GPO by its display name or by its GUID.

You can specify either a key or a value:

- If you specify a key, all Registry preference items that configure that registry key or any of its
  first-level values are removed from the specified configuration in the GPO. Registry preference
  items that configure subkeys of that key or their values are not affected. For a key, specify the
  **Key** parameter without the *ValueName* parameter.

- If you specify a value, all Registry preference items that configure that registry value are
  removed from the specified configuration in the GPO. For a value, specify the **Key** parameter
  without the **ValueName** parameter.

This cmdlet can take input from the pipeline:

- You can pipe GPO objects to this cmdlet to remove a specified Registry preference item from one or
  more GPOs.

- You can pipe **PreferencRegistrySetting** objects to this cmdlet to remove one or more Registry
  preference items from a specified GPO.

## EXAMPLES

### Example 1: Remove all registry preference item under the specified registry

```powershell
$params = @{
    Name      = 'TestGPO'
    Context   = 'User'
    Key       = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey'
    ValueName = 'ValueOne'
}
Remove-GPPrefRegistryValue @params
```

```Output
DisplayName      : TestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 92f79f6c-61ce-47d9-8dc6-f78c5cea93ac
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/28/2009 5:15:04 PM
ModificationTime : 2/28/2009 5:15:32 PM
UserVersion      : AD Version: 5, SysVol Version: 5
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

This command removes all Registry preference items that configure the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne` from User Configuration in the GPO named
`TestGPO`.

### Example 2: Remove registry preference items that configure first-level values

```powershell
$params = @{
    Name    = "TestGPO"
    Context = "Computer"
    Key     = "HKLM\SOFTWARE\Microsoft\ExampleKey"

}
Remove-GPPrefRegistryValue @params
```

```Output
DisplayName      : TestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 92f79f6c-61ce-47d9-8dc6-f78c5cea93ac
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/28/2009 5:15:04 PM
ModificationTime : 2/28/2009 5:15:32 PM
UserVersion      : AD Version: 5, SysVol Version: 5
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

This command removes Registry preference items that configure any first-level values under the
registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey` or the key itself from `Computer`
Configuration in the GPO named `TestGPO`.

### Example 3: Remove any registry preference items for all GPOs

```powershell
$params = @{
    Context     = 'User'
    Key         = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey'
    ValueName   = 'ValueOne'
    ErrorAction = 'SilentlyContinue'
}
Get-GPO -All | Remove-GPPrefRegistryValue @params
```

```Output
DisplayName      : TestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : a83ad1da-9fd4-4005-96b1-7e98042d04de
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/28/2009 5:21:05 PM
ModificationTime : 2/28/2009 5:21:17 PM
UserVersion      : AD Version: 5, SysVol Version: 5
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :


DisplayName      : TestGPO-1
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 277eafe8-5dbf-4e3f-86dc-557eee14d0a4
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/28/2009 2:35:24 PM
ModificationTime : 2/28/2009 5:21:17 PM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

This command removes any Registry preference items that configure the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne` from `User` Configuration for all GPOs
in the domain. It returns each GPO from which at least one Registry preference item is removed.

This cmdlet returns a non-terminating error for each GPO that does not have a Registry preference
item associated with the specified registry value. In this command, these error messages are
suppressed by setting the **ErrorAction** parameter to `SilentlyContinue`. For more information
about the **ErrorAction** parameter, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

### -Context

Specifies whether the Registry preference item (or items) are removed from Computer Configuration or
User Configuration in the specified GPO. You must specify either User or Computer.

```yaml
Type: GpoConfiguration
Parameter Sets: (All)
Aliases:
Accepted values: User, Computer

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for which this cmdlet runs the operation. You must specify the fully qualified
domain name (FQDN) of the domain.

For the `Remove-GPPrefRegistryValue` cmdlet, the GPO from which to remove the Registry preference
item or items must exist in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. (If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session, a trust must exist between that domain and the domain of the user or the computer.

You can also refer to the Domain parameter by its built-in alias, **DomainName**. For more
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

Specifies the GPO from which to remove the Registry preference item by its globally unique
identifier (GUID). The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: GetByGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key
Specifies a registry key for which to remove one or more Registry preference items; for instance,
HKCU\Control Panel\Colors.

You can specify any of the following registry hives: `HKEY_CLASSES_ROOT` (HKCR), `HKEY_CURRENT_USER`
(HKCU), `HKEY_LOCAL_MACHINE` (HKLM), `HKEY_USERS` (HKU), and `HKEY_CURRENT_CONFIG` (HKCC). Any of
these hives can be specified for Registry preference items in both Computer Configuration and User
Configuration.

The **Key** parameter can be specified with or without the **ValueName** parameter:

- If the **ValueName** parameter is specified, all Registry preference items that configure the
  registry value are removed.

- If the **ValueName** parameter is not specified, all Registry preference items that configure the
  registry key and any of its first-level values are removed.

You can also refer to the **Key** parameter by its built-in alias, FullKeyPath.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullKeyPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO from which to remove the Registry preference item by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the Guid parameter to uniquely identify a
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

### -Order

Specifies the order in which a Registry preference item is processed relative to other Registry
preference items in the GPO when the GPO is applied on a client computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName

Specifies the name of a registry value for which to remove all Registry preference items. If you
specify the **ValueName** parameter, you must also specify the **Key** parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Microsoft.GroupPolicy.Gpo, Microsoft.GroupPolicy.PreferenceRegistrySetting

This cmdlet takes a GPO or a **PreferenceRegistrySetting** object as input. You can pipe in one or
more **PreferenceRegistrySetting** objects to remove one or more Registry preference items from a
specified GPO. You can pipe in one or more GPO objects, such as `Get-GPO`, to remove a specified
Registry preference item from each GPO. Collections that contain GPOs from different domains are not
supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO from which the Registry preference item or items that have been removed.

## NOTES

* You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

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

[Get-GPO](./Get-GPO.md)

[Get-GPPrefRegistryValue](./Get-GPPrefRegistryValue.md)

[Set-GPPrefRegistryValue](./Set-GPPrefRegistryValue.md)

