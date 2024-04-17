---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gpprefregistryvalue?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GPPrefRegistryValue
---

# Set-GPPrefRegistryValue

## SYNOPSIS

Configures a Registry preference item under either Computer Configuration or User Configuration in a
GPO.

## SYNTAX

### ByGUID (Default)

```
Set-GPPrefRegistryValue -Guid <Guid> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Value <PSObject>] [-Type <RegistryValueKind>] -Action <PreferenceAction>
 [-Order <Int32>] [-Domain <String>] [-Server <String>] [-Disable] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByName

```
Set-GPPrefRegistryValue [-Name] <String> -Context <GpoConfiguration> -Key <String>
 [-ValueName <String>] [-Value <PSObject>] [-Type <RegistryValueKind>] -Action <PreferenceAction>
 [-Order <Int32>] [-Domain <String>] [-Server <String>] [-Disable] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Configures a Registry preference item under either Computer Configuration or User Configuration in a
Group Policy Object (GPO).

You can configure the Registry preference item for either a registry key or a registry value:

- For a registry key, specify the **Key** parameter, but do not specify the **ValueName**, **Type**,
  or **Value** parameters.

- For a registry value, specify the **Key** parameter together with the **ValueName**, **Type**, and
  **Value** parameters.

You must specify the **Context** parameter (User or Computer) to indicate whether to configure the
Registry preference item in Computer Configuration or User Configuration. You must also specify the
**Action** parameter to set the action that should be applied on the client. You can specify the GPO
by its display name or GUID. You can specify the **Disable** parameter to create a Registry
preference item that is disabled.

This cmdlet configures new Registry preference items. It does not modify existing Registry
preference items.

This cmdlet can take input from the pipeline:

- You can pipe GPO objects to this cmdlet to set a specified Registry preference item on one or more
  GPOs.

- You can pipe **PreferenceRegistrySetting** objects to this cmdlet to set one or more Registry
  preference items on a specified GPO.

## EXAMPLES

### Example 1: Configure a Registry preference item for a registry value for a GPO

```powershell
$params = @{
    Name      = 'TestGPO'
    Context   = 'User'
    Key       = 'HKCU\Software\Policies\Microsoft\Windows\Control Panel'
    ValueName = 'ScreenSaveIsSecure'
    Value     = '1'
    Type      = 'String'
    Action    = 'Update'
}
Set-GPPrefRegistryValue @params
```

```Output
DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 35c12ab3-956c-45d5-973b-46b17d225f47 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/24/2009 4:41:03 PM 
ModificationTime : 2/25/2009 12:16:28 PM 
UserVersion      : AD Version: 1, SysVol Version: 1 
ComputerVersion  : AD Version: 34, SysVol Version: 34 
WmiFilter        :
```

This command configures a Registry preference item for the registry value
`HKCU\Software\Policies\Microsoft\Windows\Control Panel\ ScreenSaveIsSecure` in `User` Configuration
for the GPO named `TestGPO`. When the GPO is applied on a client, the registry value is updated with
a data type of `String` (REG_SZ) and value data `1`.

### Example 2: Configure a Registry preference item for a registry value for a GPO

```powershell
$params = @{
    Name      = 'TestGPO'
    Context   = 'User'
    Action    = 'Create'
    Key       = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey'
    ValueName = 'ValueOne'
    Value     = 'NewData'
    Type      = 'String'
}
Set-GPPrefRegistryValue @params
```

This command configures a Registry preference item for the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne` in `User` Configuration for the GPO
named `TestGPO`. When the GPO is applied on a client, the registry value is created with a data type
of `String` (REG_SZ) and value data `NewData`.

### Example 3: Configure a Registry preference item for a registry value for a GPO specified by GUID

```powershell
$params = @{
    Guid    = '35c12ab3-956c-45d5-973b-46b17d225f47'
    Context = 'Computer'
    Action  = 'Create'
    Key     = 'HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey\ExampleKey2'
}
Set-GPPrefRegistryValue @params
```

This command configures a Registry preference item for the registry key
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey\ExampleKey2` in `Computer` Configuration in the
GPO that has ID `35c12ab3-956c-45d5-973b-46b17d225f47`. When the GPO is applied on a client, the
registry key is created.

### Example 4: Create a disabled Registry preference item for a registry value for a GPO

```powershell
$removeGPPrefParams = @{
    Name      = 'TestGPO'
    Context   = 'User'
    Key       = 'HKLM\SOFTWARE\Microsoft\ExampleKey'
    ValueName = 'ValueOne'
}
$setGPPrefParams = @{
    Context   = 'User'
    Action    = 'Create'
    Disable   = $true
    Key       = 'HKLM\SOFTWARE\Microsoft\ExampleKey'
    ValueName = 'ValueOne'
    Value     = 'SomeData'
    Type      = 'String'
}
Remove-GPPrefRegistryValue @removeGPPrefParams | 
    Set-GPPrefRegistryValue @setGPPrefParams
```

This command creates a disabled Registry preference item for the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne` in `User` Configuration in the GPO named
`TestGPO`. The `Remove-GPPrefRegistryValue` command removes any Registry preference items that
configure the value from User Configuration. Then, the GPO named `TestGPO` returned by the
`Remove-GPPrefRegistryValue` is piped into `Set-GPPrefRegistryValue` to configure the `disabled`
Registry preference item. After this command completes, the `disabled` Registry preference item is
the only Registry preference item associated with the registry value in User Configuration.

If `TestGPO` does not initially have a Registry preference item configured for the specified
registry value, a non-terminating error occurs. You can suppress the error message by supplying the
**ErrorAction** parameter to `Remove-GPPrefRegistryValue` and setting its value to
SilentlyContinue. For more information about the **ErrorAction** parameter, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

### Example 5: Configure a Registry preference item for a registry value for all GPOs

```powershell
$removeGPPrefParams = @{
    Context     = 'User'
    Key         = 'HKLM\SOFTWARE\Microsoft\ExampleKey'
    ValueName   = 'ValueOne'
    ErrorAction = 'SilentlyContinue'
}
$setGPPrefParams = @{
    Context   = 'User'
    Action    = 'Update'
    Key       = 'HKLM\SOFTWARE\Microsoft\ExampleKey'
    ValueName = 'ValueOne'
    Value     = 'SomeData'
    Type      = 'String'
}
Get-GPO -All | Remove-GPPrefRegistryValue @removeGPPrefParams | 
    Set-GPPrefRegistryValue @setGPPrefParams
```

This command configures a Registry preference item to update the registry value
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne` for every GPO in the domain that
previously had a Registry preference item configured for that value in User Configuration.

The command is invoked with the **All** parameter to get all the GPOs in the domain. These GPOs are
piped into the `Remove-GPPrefRegistryValue` cmdlet. If the GPO contains any Registry preference
items configured for the specified key, they are removed. `Remove-GPPrefRegistryValue` only
outputs a GPO to the pipeline if it removes a Registry preference item from a GPO. Finally, these
GPOs are piped to the `Set-GPPrefRegistryValue` to configure the Registry preference item to
update the registry value.

If a GPO passed to `Remove-GPPrefRegistryValue` does not have a Registry preference item
configured for the specified value, a non-terminating error occurs. The **ErrorAction** parameter is
set to `SilentlyContinue` to suppress the error message.

### Example 6: Copy all Registry preference items for a registry value for a GPO

```powershell
$getGPPrefParams = @{
    Name    = 'TestGPO'
    Context = 'User'
    Key     = 'HKLM\Software\Microsoft\ExampleKey'
}
$setGPPrefParams = @{
    Name        = 'TestGPO-1'
    Context     = 'Computer'
    Order       = 1
    ErrorAction = 'SilentlyContinue'
}
Get-GPPrefRegistryValue @getGPPrefParams | Set-GPPrefRegistryValue @setGPPrefParams
```

```Output
DisplayName      : TestGPO-1 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : ef4d0f7e-1a1a-4fd1-b735-0bc6620e7f51 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/1/2009 11:14:06 AM 
ModificationTime : 3/1/2009 11:15:16 AM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 1, SysVol Version: 1 
WmiFilter        : 


DisplayName      : TestGPO-1 
DomainName       : contoso.microsoft.com 
Owner            : CONTOSO\Domain Admins 
Id               : ef4d0f7e-1a1a-4fd1-b735-0bc6620e7f51 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/1/2009 11:14:06 AM 
ModificationTime : 3/1/2009 11:15:16 AM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 2, SysVol Version: 2 
WmiFilter        :
```

This command copies all Registry preference items that configure first-level values under the
registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey` from `User` Configuration in a
source GPO named `TestGPO` to Computer Configuration in destination GPO named `TestGPO-1`. A copy of
the destination GPO `TestGPO-1` is returned for each Registration preference item set.

The `Get-GPPrefRegistryValue` command gets all the Registry preference items that configure values
under User Configuration in the source GPO. This command also returns all first level subkeys that
have values configured (though not the Registry preference items for the values themselves). These
Registry preference items and the subkeys are then piped into the `Set-GPPrefRegistryValue`
cmdlet.

The `Set-GPPrefRegistryValue` command configures the Registry preference items for the registry
values in the destination GPO.

- The subkeys returned by `Get-GPPrefRegistryValue` do not have an **Action** property, and so a
  non-terminating error occurs for each subkey. The **ErrorAction** parameter is specified to
  suppress these error messages.

- It is a good practice to specify an order of one `-Order 1` in `Set-GPPrefRegistryValue` when it
  accepts input from the pipeline. This is because Registry preference items passed on the pipeline
  have an **Order** property. If the **Order** property of a Registry preference item passed on the
  pipeline is greater than the number of Registry preference items currently configured in the
  destination GPO, an out of range error occurs and the Registry preference item is not configured
  in the destination GPO. By specifying the order as one in the `Set-GPPrefRegistryValue` command,
  you override the **Order** property of the source Registry preference item, and prevent such
  errors from occurring.

## PARAMETERS

### -Action

Specifies the action for the Registry preference item.

The acceptable values for this parameter are:

- Create
- Update
- Replace
- Delete

The action specifies how the Registry preference item is applied to the registry key or registry
value on the client when Group Policy is processed.

```yaml
Type: PreferenceAction
Parameter Sets: (All)
Aliases: 
Accepted values: Create, Replace, Update, Delete

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Context

Specifies whether the Registry preference item is configured under User Configuration or Computer
Configuration in the GPO. The acceptable values for this parameter are: `User` or `Computer`.

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

### -Disable

Indicates that the cmdlet configures the Registry preference item as disabled. A disabled Registry
preference item is not applied when Group Policy is processed on the client, and, therefore, does
not modify any existing registry keys or values on the client.

This parameter does not disable an existing Registry preference item in the GPO, rather, it creates
a new Registry preference item that is disabled. Any existing Registry preference items that
configure the same key or value will still be applied when the GPO is processed on a client. This
behavior is different than disabling an existing Registry preference item using the GPMC.

You can use the `Remove-GPPrefRegistryValue` cmdlet to remove any existing Registry preference
items associated with the specified key or value from the appropriate configuration (User or
Computer) in the GPO before you create the new disabled Registry preference item. This ensures that
after you create the disabled Registry preference item, it will be the only Registry preference item
associated with the key or value in the specified configuration in the GPO.

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

For the `Set-GPPrefRegistryValue` cmdlet, the GPO for which to configure the Registry preference
item must exist in this domain.

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

Specifies the GPO in which to configure the Registry preference item by its globally unique
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

Specifies the registry key for the Registry preference item; for instance:
`HKEY_CURRENT_USER\Control Panel\Colors`.

You can specify any of the following registry hives: `HKEY_CLASSES_ROOT` (HKCR), `HKEY_CURRENT_USER`
(HKCU), `HKEY_LOCAL_MACHINE` (HKLM), `HKEY_USERS` (HKU), and `HKEY_CURRENT_CONFIG` (HKCC). Any of
these hives can be specified for Registry preference items in both Computer Configuration and User
Configuration.

You can configure a preference registry setting for a registry key or a registry value.

- To configure a setting for a registry key, specify the **Key** parameter without the *ValueName*,
  **Value**, or **Type** parameters.

- To configure a setting for a registry value, specify the **Key** parameter together with the
  **ValueName**, **Value**, and **Type** parameters.

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

Specifies the GPO in which to configure the Registry preference item by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String.String.String
Parameter Sets: ByName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order

Specifies the order in which the Registry preference item is processed relative to other Registry
preference items in the GPO when the GPO is applied on a client computer. If two Registry preference
items in the GPO change the same registry value, the one that has the highest order is the last to
modify the value on the client.

By default, if the **Order** parameter is not specified, the order is set to one plus the current
number of Registry preference items in the GPO. You can specify any value greater than zero. If you
specify a value larger than the default value, the order is set to the default.

The order of a setting can change as Registry preference items are added or removed from the GPO.
For instance, if the GPO has five Registry preference items, and you add another one and specify an
order of `4`, the Registry preference items that previously were at order `4` and `5`, are at order
`5` and `6` after the change.

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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Specifies the data type of the registry value for the Registry preference item.

The acceptable values for this parameter are:

- String
- ExpandString
- Binary
- DWord
- MultiString
- ExpandString
- Qword

For more information about these data types, see
[Microsoft.Win32.RegistryValueKind Enumeration](https://go.microsoft.com/fwlink/?LinkID=143266) in
the MSDN library.

When you configure a Registry preference item for a registry key, do not specify this parameter.
When you configure a Registry preference item for a registry value, specify this parameter together
with the **Key**, **ValueName**, and **Value** parameters.

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

Specifies the value data of the registry value for the Registry preference item. For instance, the
registry value `HKEY_CURRENT_USER\Control Panel\Colors ActiveTitle` can have the following (value)
`data: 10 36 106`.

When you configure a Registry preference item for a registry key, do not specify this parameter.
When you configure a Registry preference item for a registry value, specify this parameter together
with the **Key**, **ValueName**, and **Type** parameters.

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

Specifies the value name of the registry value for the Registry preference item. For instance, the
registry key `HKEY_CURRENT_USER\Control Panel\Colors` can have a value with the following name:
`ActiveTitle`. For the default value of a registry key, specify either `(default)` or an empty string
`""`.

When you configure a Registry preference item for a registry key, do not specify this parameter.
When you configure a Registry preference item for a registry value, specify this parameter together
with the **Key**, **Value**, and **Type** parameters.

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

You can pipe a GPO object (in which to configure a specified preference registry setting) to this
cmdlet, or a **PreferenceRegistrySetting** object (to configure in a specified GPO). Collections
that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO in which the Registry preference item was configured.

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

[Get-GPPrefRegistryValue](./Get-GPPrefRegistryValue.md)

[Remove-GPPrefRegistryValue](./Remove-GPPrefRegistryValue.md)

