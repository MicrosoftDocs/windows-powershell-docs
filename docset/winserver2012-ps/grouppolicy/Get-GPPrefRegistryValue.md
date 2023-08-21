---
external help file: GPv2_Cmdlets.xml
Module Name: GroupPolicy
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gpprefregistryvalue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-GPPrefRegistryValue

## SYNOPSIS
Retrieves one or more Registry preference items under either Computer Configuration or User Configuration in a GPO.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-GPPrefRegistryValue [-Domain <String>] [-Order <Int32>] [-Server <String>] [-ValueName <String>]
 -Context <GpoConfiguration> -Guid <Guid> -Key <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-GPPrefRegistryValue [-Name] <String> [-Domain <String>] [-Order <Int32>] [-Server <String>]
 [-ValueName <String>] -Context <GpoConfiguration> -Key <String>
```

## DESCRIPTION
The Get-GPPrefRegistryValue cmdlet retrieves one or more Registry preference items under either Computer Configuration or User Configuration in a GPO.
You must specify the Context parameter (User or Computer) to indicate whether to retrieve the Registry preference item from Computer Configuration or User Configuration.
. You can specify the GPO by its display name or by its GUID.

You can retrieve Registry preference items for a specific registry value, or for a key and any of its first-level registry values:

- To retrieve any Registry preference items that configure a specific registry value, specify both the Key and the ValueName parameters.

- To retrieve all the Registry preference items that configure a registry key and any (first-level) registry values directly under the key, specify the Key parameter without the ValueName parameter.

If you specify only a key, the cmdlet also returns its first-level subkeys for which there are Registry preference items that configure the subkey, its values, or any of its subkeys (at any level) or their values.
You can use this information to browse for Registry preference items.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>get-gpprefregistryvalue -name testgpo -context user -key hklm\software\microsoft\examplekey -valuename valueone 

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
```

Description

-----------

This command retrieves the Registry preference item that is configured for the registry value "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey ValueOne" from User Configuration in the "TestGPO" GPO.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>get-gpprefregistryvalue -name testgpo -context user -key hklm\software\microsoft\examplekey 

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

Description

-----------

This command retrieves all the Registry preference items that are configured for the registry key "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExampleKey" and any of its first-level values from User Configuration in the "TestGPO" GPO.

In this example, Registry preference items that configure the following two first-level values of the registry key are returned: ValueOne and ValueTwo.
Two subkeys of the key are also returned.
This is because there are Registry preference items in User Configuration associated with each subkey.

## PARAMETERS

### -Context
Specifies whether the Registry preference item is retrieved from User Configuration or Computer Configuration in the GPO.
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

For the Get-GPPrefRegistryValue cmdlet, the GPO for which to retrieve the Registry preference item must exist in this domain.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Domain parameter by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: domainname

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies the GPO from which to retrieve the Registry preference item by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key
Specifies the registry key for the Registry preference item to retrieve; for example: HKEY_CURRENT_USER\Control Panel\Colors.

You can specify any of the following registry hives: HKEY_CLASSES_ROOT (HKCR), HKEY_CURRENT_USER (HKCU), HKEY_LOCAL_MACHINE (HKLM), HKEY_USERS (HKU), and HKEY_CURRENT_CONFIG (HKCC).
Any of these hives can be specified for Registry preference items in both Computer Configuration and User Configuration.

The Key parameter can be specified with or without the ValueName parameter:

- If the ValueName parameter is specified, all Registry preference items that configure the registry value are retrieved.

- If the ValueName parameter is not specified, all Registry preference items that configure the registry key and any of its (first-level) values are retrieved.

You can also refer to the Key parameter by its built-in alias, "FullKeyPath".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullKeyPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the GPO from which to retrieve the Registry preference item by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: displayname

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order
Specifies the order in which the Registry preference item is applied, relative to the other Registry preference items in the GPO, on a client.

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
Aliases: dc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName
Specifies the name of a registry value for which to retrieve all Registry preference items.
For example, the registry key "HKEY_CURRENT_USER\Control Panel\Colors" can have a value with the following name: ActiveTitle.
For the default value of a registry key, specify either "(default)" or an empty string ("").

When you want to retrieve Registry preference items for a registry key and all its first-level values, do not specify this parameter.
When you want to retrieve Registry preference items only for a specific registry value, specify this parameter together with the Key parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.Gpo
This cmdlet takes a GPO as input.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.PreferenceRegistrySetting
This cmdlet returns PreferenceRegistrySetting objects.
You can pipe these objects to the following cmdlets:

Set-GPPrefRegistryValue

Remove-GPPrefRegistryValue

## NOTES
* If a Registry preference item for the specified registry key or value is not found, a non-terminating error occurs.

  You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell® or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Remove-GPPrefRegistryValue](./Remove-GPPrefRegistryValue.md)

[Set-GPPrefRegistryValue](./Set-GPPrefRegistryValue.md)

