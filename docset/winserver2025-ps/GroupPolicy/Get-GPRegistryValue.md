---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gpregistryvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPRegistryValue
---

# Get-GPRegistryValue

## SYNOPSIS

Gets one or more registry-based policy settings under either Computer Configuration or User
Configuration in a GPO.

## SYNTAX

### GetByGUID (Default)

```
Get-GPRegistryValue -Guid <Guid> -Key <String> [-ValueName <String>] [-Domain <String>]
 [-Server <String>] [<CommonParameters>]
```

### GetByName

```
Get-GPRegistryValue [-Name] <String> -Key <String> [-ValueName <String>] [-Domain <String>]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPRegistryValue` cmdlet retrieves one or more registry-based policy settings under either
Computer Configuration or User Configuration in a Group Policy Object (GPO).

You can get registry-based policy settings for a specific registry value, or for all the registry
values under a key:

- To get the registry-based policy setting that configures a specific registry value, specify both
  the **Key** and the **ValueName** parameters.

- To get all the registry-based policy settings that configure values directly under a registry key,
  specify the **Key** parameter without the **ValueName** parameter.

If you specify only a key, in addition to the policy settings that configure values under the key,
the following first-level subkeys of the key are returned:

- first-level subkeys that have a policy setting that configures a value.

- first-level subkeys that have a subkey, at any level, with a policy setting that configures a
  value.

You can use this information to browse for registry-based policy settings.

## EXAMPLES

### Example 1: Get the group policy registry value from the specified key

```powershell
$params = @{
    ValueName = 'ValueOne'
    Key       = 'HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey'
    Name      = 'TestGPO'
}
Get-GPRegistryValue @params
```

```Output
KeyPath     : Software\Policies\Microsoft\ExampleKey
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey
Hive        : CurrentUser
PolicyState : Set
Value       : TestGPO
Type        : String
ValueName   : ValueOne
HasValue    : True
```

This command gets the registry-based policy setting that configures the registry value
`HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey:ValueOne` from User Configuration in the
GPO named TestGPO.

### Example 2: Get all group policy registry values from the specified key

```powershell
Get-GPRegistryValue -Name "TestGPO" -Key "HKCU\Software\Policies\Microsoft\ExampleKey"
```

```Output
KeyPath     : Software\Policies\Microsoft\ExampleKey
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey
Hive        : CurrentUser
PolicyState : Set
Value       : TestGPO
Type        : String
ValueName   : ValueOne
HasValue    : True

KeyPath     : Software\Policies\Microsoft\ExampleKey
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey
Hive        : CurrentUser
PolicyState : Delete
Value       :
Type        : String
ValueName   : ValueTwo
HasValue    : True


KeyPath     : Software\Policies\Microsoft\ExampleKey\Subkey1
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey\Subkey1
Hive        : CurrentUser

KeyPath     : Software\Policies\Microsoft\ExampleKey\SubKey2
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey\SubKey2
Hive        : CurrentUser
```

This command gets all the registry-based policy settings that configure registry values under the
key `HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey` from User Configuration in the GPO
named `TestGPO`. Subkeys of this key that have registry-based policy settings, are also returned.
The second registry-based policy setting (ValueTwo) is disabled (its **PolicyState** property is set
to Delete).

## PARAMETERS

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain (for instance: sales.contoso.com).

For the `Get-GPRegistryValue` cmdlet, the GPO for which to get registry-based policy settings must
exist in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to Domain by its built-in alias, **DomainName**. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

Specifies the GPO from which to retrieve the registry-based policy setting by its globally unique
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

Specifies the registry key for which this cmdlet gets the registry-based policy setting. For
instance: `HKLM\Software\Policies\Microsoft\Windows NT\DNSClient`.

The key must be in one of the two following registry hives:

- HKEY_LOCAL_MACHINE (HKLM) for a registry-based policy setting in Computer Configuration.

- HKEY_CURRENT_USER (HKCU) for a registry-based policy setting in User Configuration.

You can specify:

- The **Key** parameter without the **ValueName** parameter to get all the registry-based policy
  settings that configure values directly under that key.

- The Key parameter together with the **ValueName** parameter to get the registry-based policy
  setting that configures a specific registry value.

You can also refer to the **Key** parameter by its built-in alias FullKeyPath. For more information,
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

Specifies the GPO from which this cmdlet gets the registry-based policy setting by its display name.

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

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

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

Specifies the name of a registry value for which this cmdlet gets the registry-based policy setting.
For instance, the registry key `HKLM\Software\Policies\Microsoft\Windows NT\DNSClient` can have a
value with the following name: UseDomainNameDevolution. For the default value of a registry key,
specify "(default)" or an empty string ("").

You must also specify the **Key** parameter with this parameter.

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

You can pipe a GPO for which this cmdlet gets registry-based policy settings. Collections that
contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.PolicyRegistrySetting

This cmdlet returns **PolicyRegistrySetting** objects that represent registry-based policy settings.
These objects can be piped into the following cmdlets:

- `Set-GPRegistryValue`

- `Remove-GPRegistryValue`

## NOTES

* The hive of the registry key that you specify (HKLM or HKCU) indicates whether the registry-based
  policy setting is retrieved from Computer Configuration or User Configuration.

  If the specified registry key cannot be located in policy (the registry key is not configured), a
  corresponding error message is displayed.

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

[Remove-GPRegistryValue](./Remove-GPRegistryValue.md)

[Set-GPRegistryValue](./Set-GPRegistryValue.md)

