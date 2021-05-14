---
external help file: GPv2_Cmdlets.xml
Module Name: GroupPolicy
online version: https://docs.microsoft.com/powershell/module/grouppolicy/remove-gpprefregistryvalue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-GPPrefRegistryValue

## SYNOPSIS
Removes one or more Registry preference items from either Computer Configuration or User Configuration in a GPO.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-GPPrefRegistryValue [[-Server] <String>] [-Domain <String>] [-Order <Int32>] [-ValueName <String>]
 -Context <GpoConfiguration> -Guid <Guid> -Key <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-GPPrefRegistryValue [-Name] <String> [[-Server] <String>] [-Domain <String>] [-Order <Int32>]
 [-ValueName <String>] -Context <GpoConfiguration> -Key <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Remove-GPPrefRegistryValue cmdlet removes one or more Registry preference items from either Computer Configuration or User Configuration in a GPO.
You must specify the Context parameter (User or Computer) to indicate whether to remove the Registry preference item from Computer Configuration or User Configuration.
. You can specify the GPO by its display name or by its GUID.

You can specify either a key or a value:

- If you specify a key, all Registry preference items that configure that registry key or any of its (first-level) values are removed from the specified configuration in the GPO.
Registry preference items that configure subkeys of that key (or their values) are not affected.
For a key, specify the Key parameter without the ValueName parameter.

- If you specify a value, all Registry preference items that configure that registry value are removed from the specified configuration in the GPO.
For a value, specify the Key parameter without the ValueName parameter.

This cmdlet can take input from the pipeline:

- You can pipe GPO objects to this cmdlet to remove a specified Registry preference item from one or more GPOs.

- You can pipe PreferencRegistrySetting objects to this cmdlet to remove one or more Registry preference items from a specified GPO.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-GPPrefRegistryValue -Name TestGPO -Context User -Key "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey" -ValueName ValueOne 

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

Description

-----------

This command removes all Registry preference items that configure the registry value "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne" from User Configuration in the "TestGPO" GPO.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-GPPrefRegistryValue -Name TestGPO -Context Computer -Key "HKLM\SOFTWARE\Microsoft\ExampleKey" 

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

Description

-----------

This command removes Registry preference items that configure any (first-level) values under the registry key "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey" or the key itself from Computer Configuration in the "TestGPO" GPO.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-GPO -All | Remove-GPPrefRegistryValue -Context User -Key "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey" -ValueName ValueOne -ErrorAction SilentlyContinue 

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

Description

-----------

This command removes any Registry preference items that configure the registry value "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne" from User Configuration for all GPOs in the domain.
It returns each GPO from which at least one Registry preference item is removed.

Note: The Remove-GPPrefRegistryValue returns a non-terminating error for each GPO that does not have a Registry preference item associated with the specified registry value.
In this command, these error messages are suppressed by setting the ErrorAction parameter to SilentlyContinue (-ErrorAction SilentlyContinue).
For more information about the ErrorAction parameter, see about_CommonParameters.

## PARAMETERS

### -Context
Specifies whether the Registry preference item (or items) are removed from Computer Configuration or User Configuration in the specified GPO.
You must specify either User or Computer.

The following values are permitted for this object type.

```yaml
Type: GpoConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Remove-GPPrefRegistryValue cmdlet, the GPO from which to remove the Registry preference item (or items) must exist in this domain.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Domain parameter by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies the GPO from which to remove the Registry preference item by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key
Specifies a registry key for which to remove one or more Registry preference items; for example, "HKCU\Control Panel\Colors".

You can specify any of the following registry hives: HKEY_CLASSES_ROOT (HKCR), HKEY_CURRENT_USER (HKCU), HKEY_LOCAL_MACHINE (HKLM), HKEY_USERS (HKU), and HKEY_CURRENT_CONFIG (HKCC).
Any of these hives can be specified for Registry preference items in both Computer Configuration and User Configuration.

The Key parameter can be specified with or without the ValueName parameter:

- If the ValueName parameter is specified, all Registry preference items that configure the registry value are removed.

- If the ValueName parameter is not specified, all Registry preference items that configure the registry key and any of its (first-level) values are removed.

You can also refer to the Key parameter by its built-in alias, "FullKeyPath".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the GPO from which to remove the Registry preference item by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order
Specifies the order in which a Registry preference item is processed relative to other Registry preference items in the GPO when the GPO is applied on a client computer.

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
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName
Specifies the name of a registry value for which to remove all Registry preference items.
If you specify the ValueName parameter, you must also specify the Key parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.Gpo, Microsoft.GroupPolicy.PreferenceRegistrySetting
This cmdlet takes a GPO or a PreferenceRegistrySetting object as input.
You can pipe in one or more PreferenceRegistrySetting objects (for example, from Get-GPPrefRegistryValue) to remove one or more Registry preference items from a specified GPO.
You can pipe in one or more GPO objects (for example, from Get-GPO) to remove a specified Registry preference item from each GPO.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
Remove-GPPrefRegistryValue returns the GPO from which the Registry preference item (or items) has been removed.

## NOTES
* You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPPrefRegistryValue](./Get-GPPrefRegistryValue.md)

[Set-GPPrefRegistryValue](./Set-GPPrefRegistryValue.md)

