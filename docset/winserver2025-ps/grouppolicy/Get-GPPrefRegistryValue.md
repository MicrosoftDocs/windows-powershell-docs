---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gpprefregistryvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPPrefRegistryValue
---

# Get-GPPrefRegistryValue

## SYNOPSIS

Gets one or more Registry preference items under either Computer Configuration or User Configuration
in a GPO.

## SYNTAX

### GetByGUID (Default)

```
Get-GPPrefRegistryValue -Guid <Guid> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Order <Int32>] [-Domain <String>] [-Server <String>] [<CommonParameters>]
```

### GetByName

```
Get-GPPrefRegistryValue [-Name] <String> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Order <Int32>] [-Domain <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPPrefRegistryValue` cmdlet gets one or more Registry preference items under either
Computer Configuration or User Configuration in a Group Policy Object (GPO). You must specify the
*Context* parameter, for the user or computer, to indicate whether to get the Registry preference
item from Computer Configuration or User Configuration. You can specify the GPO by its display name
or by its GUID.

You can get Registry preference items for a specific registry value, or for a key and any of its
first-level registry values:

- To get any Registry preference items that configure a specific registry value, specify both the
  **Key** and the *ValueName* parameters.

- To get all the Registry preference items that configure a registry key and any first-level
  registry values directly under the key, specify the **Key** parameter without the *ValueName*
  parameter.

If you specify only a key, the cmdlet also returns its first-level subkeys for which there are
Registry preference items that configure the subkey, its values, or any of its subkeys or their
values. You can use this information to browse for Registry preference items.

## EXAMPLES

### Example 1: Get the Registry preference item value

```powershell
$params = @{
    ValueName = 'ValueOne'
    Context   = 'User'
    Key       = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey'
    Name      = 'TestGPO'
}
Get-GPPrefRegistryValue @params
```

```Output
KeyPath            : SOFTWARE\Microsoft\ExampleKey
FullKeyPath        : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey
Hive               : LocalMachine
Action             : Create
Order              : 1
DisabledDirectly   : False
DisabledByAncestor : False
Value              : TestGPO
Type               : String
ValueName          : ValueOne
HasValue           : True
```

This command gets the Registry preference item that is configured for the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey` with value name ValueOne from User Configuration
in the GPO named `TestGPO`.

### Example 2: Get all Registry preference items

```powershell
$params = @{
    Context = 'User'
    Key     = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey'
    Name    = 'TestGPO'
}
Get-GPPrefRegistryValue @params
```

```Output
KeyPath            : SOFTWARE\Microsoft\ExampleKey
FullKeyPath        : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey
Hive               : LocalMachine
Action             : Create
Order              : 1
DisabledDirectly   : False
DisabledByAncestor : False
Value              : NewData1
Type               : String
ValueName          : ValueOne
HasValue           : True

KeyPath            : SOFTWARE\Microsoft\ExampleKey
FullKeyPath        : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey
Hive               : LocalMachine
Action             : Create
Order              : 2
DisabledDirectly   : False
DisabledByAncestor : False
Value              : NewData2
Type               : String
ValueName          : Valuetwo
HasValue           : True



KeyPath     : SOFTWARE\Microsoft\ExampleKey\Subkey1
FullKeyPath : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey\Subkey1
Hive        : LocalMachine

KeyPath     : SOFTWARE\Microsoft\ExampleKey\SubKey2
FullKeyPath : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey\SubKey2
Hive        : LocalMachine
```

This command gets all the Registry preference items that are configured for the registry key
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey and any of its first-level values from User
Configuration in the GPO named TestGPO.

In this example, Registry preference items that configure the following two first-level values of
the registry key are returned: ValueOne and ValueTwo. Two subkeys of the key are also returned. This
is because there are Registry preference items in User Configuration associated with each subkey.

## PARAMETERS

### -Context

Specifies whether the cmdlet gets the Registry preference item from User Configuration or Computer
Configuration in the GPO.

The acceptable values for this parameter are: User or Computer.

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

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Get-GPPrefRegistryValue` cmdlet, the GPO for which to get the Registry preference item
must exist in this domain.

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

Specifies the GPO from which this cmdlet gets the Registry preference item by its globally unique
identifier (GUID). The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

Specifies the registry key for the Registry preference item that this cmdlet gets; for instance:
`HKEY_CURRENT_USER\Control Panel\Colors`.

The acceptable values for this parameter are:

- HKEY_CLASSES_ROOT (HKCR)
- HKEY_CURRENT_USER (HKCU)
- HKEY_LOCAL_MACHINE (HKLM)
- HKEY_USERS (HKU)
- HKEY_CURRENT_CONFIG (HKCC)

Any of these hives can be specified for Registry preference items in both Computer Configuration and
User Configuration.

The **Key** parameter can be specified with or without the *ValueName* parameter:

- If the **ValueName** parameter is specified, all Registry preference items that configure the
  registry value are retrieved.

- If the **ValueName** parameter is not specified, all Registry preference items that configure the
  registry key and any of its first-level values are retrieved.

You can also refer to the Key parameter by its built-in alias, FullKeyPath. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullKeyPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the GPO from which this cmdlet gets the Registry preference item by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

Specifies the order in which the Registry preference item is applied, relative to the other Registry
preference items in the GPO, on a client.

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

If you do not specify the name through the **Server** parameter, the primary domain controller (PDC)
emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

### -ValueName

Specifies the name of a registry value for which this cmdlet gets all Registry preference items. For
instance, the registry key `HKEY_CURRENT_USER\Control Panel\Colors` can have a value with the
following name: ActiveTitle. For the default value of a registry key, specify either "(default)" or
an empty string ("").

When you want to gets Registry preference items for a registry key and all its first-level values,
do not specify this parameter. When you want to get Registry preference items only for a specific
registry value, specify this parameter together with the **Key** parameter.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet takes a GPO as input. Collections that contain GPOs from different domains are not
supported.

## OUTPUTS

### Microsoft.GroupPolicy.PreferenceRegistrySetting

This cmdlet returns **PreferenceRegistrySetting** objects. You can pipe these objects to the
following cmdlets:

- `Set-GPPrefRegistryValue`

- `Remove-GPPrefRegistryValue`

## NOTES

* If a Registry preference item for the specified registry key or value is not found, a
  non-terminating error occurs.

  You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For instance, the domain of the user who started the session by opening Windows
  PowerShell or the domain of a user that is specified in a runas command. However, computer startup
  and shutdown scripts run under the context of the LocalSystem account. The LocalSystem account is
  a built-in local account, and it accesses network resources under the context of the computer
  account. Therefore, when this cmdlet is run from a startup or shutdown script, the default domain
  is the domain to which the computer is joined.

## RELATED LINKS

[Remove-GPPrefRegistryValue](./Remove-GPPrefRegistryValue.md)

[Set-GPPrefRegistryValue](./Set-GPPrefRegistryValue.md)

