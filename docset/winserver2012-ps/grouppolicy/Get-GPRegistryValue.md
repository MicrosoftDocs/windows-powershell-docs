---
external help file: GPv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 6F526B5E-8887-4612-9CF4-C45DF9DBC546
manager: dansimp
---

# Get-GPRegistryValue

## SYNOPSIS
Retrieves one or more registry-based policy settings under either Computer Configuration or User Configuration in a GPO.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-GPRegistryValue [-Domain <String>] [-Server <String>] [-ValueName <String>] -Guid <Guid> -Key <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-GPRegistryValue [-Name] <String> [-Domain <String>] [-Server <String>] [-ValueName <String>] -Key <String>
```

## DESCRIPTION
The Get-GPRegistryValue cmdlet retrieves one or more registry-based policy settings under either Computer Configuration or User Configuration in a GPO.

You can retrieve registry-based policy settings for a specific registry value, or for all the registry values under a key:

- To retrieve the registry-based policy setting that configures a specific registry value, specify both the Key and the ValueName parameters.

- To retrieve all the registry-based policy settings that configure values directly under a registry key, specify the Key parameter without the ValueName parameter.

If you specify only a key, in addition to the policy settings that configure values under the key, the following first-level subkeys of the key are returned:

- first-level subkeys that have a policy setting that configures a value.

- first-level subkeys that have a subkey (at any level) with a policy setting that configures a value.

You can use this information to browse for registry-based policy settings.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-GPRegistryValue -Name TestGPO -Key HKCU\Software\Policies\Microsoft\ExampleKey -ValueName ValueOne 

KeyPath     : Software\Policies\Microsoft\ExampleKey 
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey 
Hive        : CurrentUser 
PolicyState : Set 
Value       : DataString 1 
Type        : String 
ValueName   : ValueOne 
HasValue    : True
```

Description

-----------

This command retrieves the registry-based policy setting that configures the registry value "HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey ValueOne" from User Configuration in the "TestGPO" GPO.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-GPRegistryValue -Name TestGPO -Key HKCU\Software\Policies\Microsoft\ExampleKey 

KeyPath     : Software\Policies\Microsoft\ExampleKey 
FullKeyPath : HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey 
Hive        : CurrentUser 
PolicyState : Set 
Value       : DataString 1 
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

Description

-----------

This command retrieves all the registry-based policy settings that configure registry values under the key "HKEY_CURRENT_USER\Software\Policies\Microsoft\ExampleKey" from User Configuration in the "TestGPO" GPO.
Subkeys (of this key) that have registry-based policy settings, are also returned.
The second registry-based policy setting (ValueTwo) is disabled (its PolicyState property is set to Delete).

## PARAMETERS

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Get-GPRegistryValue cmdlet, the GPO for which to retrieve registry-based policy settings must exist in this domain.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to Domain by its built-in alias, "domainname".
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
Specifies the GPO from which to retrieve the registry-based policy setting by its globally unique identifier (GUID).
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
Specifies the registry key for which to retrieve the registry-based policy setting (or settings).
For example: "HKLM\Software\Policies\Microsoft\Windows NT\DNSClient".

The key must be in one of the two following registry hives:

- HKEY_LOCAL_MACHINE (HKLM) for a registry-based policy setting in Computer Configuration.

- HKEY_CURRENT_USER (HKCU) for a registry-based policy setting in User Configuration.

You can specify:

- The Key parameter without the ValueName parameter to retrieve all the registry-based policy settings that configure values directly under that key.

- The Key parameter together with the ValueName parameter to retrieve the registry-based policy setting that configures a specific registry value.

You can also refer to the Key parameter by its built-in alias "FullKeyPath".
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
Specifies the GPO from which to retrieve the registry-based policy setting by its display name.

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

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.SalesDomain.Contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

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

### -ValueName
Specifies the name of a registry value for which to retrieve the registry-based policy setting.
For example, the registry key "HKLM\Software\Policies\Microsoft\Windows NT\DNSClient" can have a value with the following name: UseDomainNameDevolution.
For the default value of a registry key, specify "(default)" or an empty string ("").

You must also specify the Key parameter with this parameter.

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
A GPO for which to retrieve registry-based policy settings.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.PolicyRegistrySetting
Get-GPRegistryValue returns PolicyRegistrySetting objects that represent registry-based policy settings.
These objects can be piped into the following cmdlets:

Set-GPRegistryValue

Remove-GPRegistryValue

## NOTES
* The hive of the registry key that you specify (HKLM or HKCU) indicates whether the registry-based policy setting is retrieved from Computer Configuration or User Configuration.

  If the specified registry key cannot be located in policy (the registry key is not configured), a corresponding error message is displayed.

  You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell® or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Remove-GPRegistryValue](./Remove-GPRegistryValue.md)

[Set-GPRegistryValue](./Set-GPRegistryValue.md)

