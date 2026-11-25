---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsldapserverconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsLdapServerConnection
---

# New-AdfsLdapServerConnection

## SYNOPSIS
Creates a connection object.

## SYNTAX

```
New-AdfsLdapServerConnection [-HostName] <String> [-Port <Int32>] [-SslMode <LdapSslMode>]
 [-AuthenticationMethod <LdapAuthenticationMethod>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsLdapServerConnection** cmdlet creates a connection object that represents the Lightweight Directory Access Protocol (LDAP) folder that serves as a claims provider trust.
A connection object includes host name, port, and authentication credentials.

## EXAMPLES

### Example 1: Create an LDAP connection
```
PS C:\> $Credential = Get-Credential
PS C:\ > $LdapConn = New-AdfsLdapServerConnection -HostName "DomainContoller03.contoso.com" -Port 389 -SslMode None -AuthenticationMethod Basic -Credential $Credential
```

The first command prompts you for a user name and password by using the **Get-Credential** cmdlet.
The command stores the results in the $Credential variable.

The second command creates an LDAP connection.
DomainContoller03.contoso.com is the fully qualified domain name of a domain controller in the other forest.
The command stores the result in the $LdapConn variable.

To see this cmdlet as part of creating an LDAP local claims provider trust, see the **Add-AdfsLocalClaimsProviderTrust** cmdlet.

## PARAMETERS

### -AuthenticationMethod
Specifies the authentication method the local claims provider trust uses.
In Windows Server 2016, the only supported method is Basic (username/password).

```yaml
Type: LdapAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use for the connection to the LDAP host.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the fully qualified domain name of the server that hosts the LDAP folder to which Active Directory Federation Services (AD FS) connects for authentication requests.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the port that AD FS uses to connect to the LDAP host.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslMode
Specifies SSL setting of the connection.
The acceptable values for this parameter are:

- None
- Ssl
- Tls

```yaml
Type: LdapSslMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Ssl, Tls

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsLocalClaimsProviderTrust](./Add-AdfsLocalClaimsProviderTrust.md)

