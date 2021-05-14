---
external help file: SMISConfig_Cmdlets.xml
Module Name: SMISConfig
online version: https://docs.microsoft.com/powershell/module/smisconfig/register-smisprovider?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Register-SmisProvider

## SYNOPSIS
Registers an SMI-S provider and stores the configuration in the SMI-S service.

## SYNTAX

```
Register-SmisProvider [-ConnectionUri] <Uri> [-Credential] <PSCredential> [[-AdditionalUsers] <String[]>]
 [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Register-SmisProvider** cmdlet registers a Storage Management Initiative - Specification (SMI-S) provider.
The cmdlet registers a provider identified by a Uniform Resource Identifier (URI), and stores the configuration and credentials for later use.
In order to use a provider, you must register the provider with the SMI-S service.

When you register the provider, the credentials are stored for your use only.
You can also specify other users to manage the registered provider.

To search for a list of SMI-S providers on the same subnet as your server, use the **Search-SmisProvider** cmdlet.

If the provider is using the HTTPS protocol, you may be prompted to accept the certificate if it has not been previously seen by your server.

## EXAMPLES

### Example 1: Register an SMI-S provider
```
PS C:\> Register-SmisProvider -ConnectionUri https://smis.contoso.com:5989
```

This command registers an SMI-S provider by using a URI.

### Example 2: Register an SMI-S WMI provider in an automated script
```
PS C:\>$password = ConvertTo-SecureString "p@ssword" -AsPlainText -Force 


PS C:\>$cred = New-Object System.Management.Automation.PSCredential "admin", $password


PS C:\>Register-SmisProvider -ConnectionUri ContosoServer1 -Credential $cred
```

This example registers an SMI-S WMI provider.

The first command converts a string to a secure string and assigns the result to the variable $password.

The second command creates a new credential object by using the $password variable and assigns the result to the variable $cred.

The third command registers an SMI-S provider by using the variable $cred.

### Example 3: Discover the storage objects managed by a registered provider
```
PS C:\>Update-StorageProviderCache -Name smis.contoso.com -DiscoveryLevel Level3
```

This command discovers the managed objects under a registered SMI-S provider.

## PARAMETERS

### -AdditionalUsers
Specifies an array of other users who can manage the SMI-S provider.
The cmdlet stores the credentials , specified by the -Credentials parameter for users in the **AdditionalUsers** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Users

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the URI of the SMI-S provider to register.
For CIMXML-based providers, the format must include the protocol specifier (HTTPS and HTTP are supported).
The port number for such providers should also be specified, but can be omitted if the default SMI-S ports are used (5989 for HTTPS and 5988 for HTTP). 
The ConnectionUri is just the server name for SMI-S providers implemented as WMI providers.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: Uri

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials used to for authentication with the SMI-S provider.
The cmdlet stores the credentials for subsequent use.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: Creds

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Performs the action without a confirmation message.

```yaml
Type: SwitchParameter
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Search-SmisProvider](./Search-SmisProvider.md)

[Unregister-SmisProvider](./Unregister-SmisProvider.md)

[Get-StorageProvider](../storage/Get-StorageProvider.md)

[Update-StorageProviderCache](../storage/Update-StorageProviderCache.md)

