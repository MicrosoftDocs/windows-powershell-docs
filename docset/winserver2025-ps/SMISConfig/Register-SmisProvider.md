---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.StorageManagementService.Configuration.Cmdlets.dll-Help.xml
Module Name: SMISConfig
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/smisconfig/register-smisprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-SmisProvider
---

# Register-SmisProvider

## SYNOPSIS
Registers an SMI-S provider and stores the configuration in the SMI-S service.

## SYNTAX

```
Register-SmisProvider [-ConnectionUri] <Uri> [-Credential] <PSCredential> [[-AdditionalUsers] <String[]>]
 [[-CimSession] <CimSession>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SmisProvider** cmdlet registers a Storage Management Initiative - Specification (SMI-S) provider.
The cmdlet registers a provider identified by a Uniform Resource Identifier (URI), and stores the configuration and credentials for later use.
In order to use a provider, you must register the provider with the SMI-S service.

When you register the provider, the credentials are stored for your use only.
You can also specify other users to manage the registered provider.

To search for a list of SMI-S providers on the same subnet as your server, use the Search-SmisProvider cmdlet.

If the provider is using the HTTPS protocol, you may be prompted to accept the certificate if it has not been previously seen by your server.

## EXAMPLES

### Example 1: Register an SMI-S provider
```
PS C:\> Register-SmisProvider -ConnectionUri https://smis.contoso.com:5989
```

This command registers an SMI-S provider by using a URI.

### Example 2: Register an SMI-S WMI provider in an automated script
```
PS C:\> $Password = ConvertTo-SecureString "password" -AsPlainText -Force
PS C:\> $Credential = New-Object System.Management.Automation.PSCredential "admin", $Password
PS C:\> Register-SmisProvider -ConnectionUri ContosoServer17 -Credential $Credential
```

This example registers an SMI-S WMI provider.

The first command converts a string to a secure string and assigns the result to the variable $Password.
For more information, type `Get-Help ConvertTo-SecureString`.

The second command creates a new credential object by using the $Password variable and assigns the result to the variable $Credential.

The third command registers an SMI-S provider by using the variable $Credential.

### Example 3: Discover the storage objects managed by a registered provider
```
PS C:\> Update-StorageProviderCache -Name "smis.contoso.com" -DiscoveryLevel Level3
```

This command discovers the managed objects under a registered SMI-S provider.

## PARAMETERS

### -AdditionalUsers
Specifies an array of other users who can manage the SMI-S provider.
The cmdlet stores the credentials, specified by the *Credentials* parameter, for the users that you specify.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Users

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the URI of the SMI-S provider to register.
For CIMXML-based providers, the format must include the protocol specifier.
The parameter supports HTTPS and HTTP.
The port number for such providers should also be specified.
You can omit default SMI-S ports, which are 5989 for HTTPS and 5988 for HTTP.
The *ConnectionUri* is the server name for SMI-S providers implemented as WMI providers.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: Uri

Required: True
Position: 0
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Uri

### System.Management.Automation.PSCredential

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)

[Search-SmisProvider](./Search-SmisProvider.md)

[Unregister-SmisProvider](./Unregister-SmisProvider.md)

