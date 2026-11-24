---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/test-vmreplicationconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VMReplicationConnection
---

# Test-VMReplicationConnection

## SYNOPSIS
Tests the connection between a primary server and a Replica server.

## SYNTAX

```
Test-VMReplicationConnection [-ReplicaServerName] <String> [-ReplicaServerPort] <Int32>
 [-AuthenticationType] <ReplicationAuthenticationType> [[-CertificateThumbprint] <String>]
 [-BypassProxyServer <Boolean>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-VMReplicationConnection** cmdlet tests the connection between a primary server and a Replica server to determine whether replication can be enabled for virtual machines on the primary server to the specified Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Test-VMReplicationConnection server01.domain01.contoso.com 80 Kerberos
```

This example tests the connection between the local host and a Replica server named server01.domain01.contoso.com, using port 80 and Kerberos authentication.

## PARAMETERS

### -AuthenticationType
Specifies the authentication type to use to test the connection, either "Kerberos" or "Certificate".
The specified Replica server must support the chosen authentication type.
Run the **Get-VMReplicationServer** cmdlet to verify the authentication configured for the specified Replica server, or contact the administrator of the specified Replica server.

```yaml
Type: ReplicationAuthenticationType
Parameter Sets: (All)
Aliases: AuthType
Accepted values: Kerberos, Certificate

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassProxyServer
Specifies whether to bypass a proxy server when testing the connectivity.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the certificate to use for mutual authentication of the replication data.
This parameter is required only when "Certificate" is the specified as the type of authentication.
Specify the thumbprint of a valid computer certificate from the Personal store.

The certificate must have all of the following properties to be valid:

It must not be expired.

It must include both client and server authentication extensions for extended key usage (EKU), and an associated private key.

It must terminate at a valid root certificate.

The requirement for the subject common name (CN) differs depending on whether the virtual machine belongs to a cluster.
For virtual machines that do not belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) should contain, the FQDN of the host.
For virtual machines that belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) must contain, the FQDN of the Hyper-V Replica Broker.

To display a list certificates in the computer's My store and the thumbprint of each certificate, type the following:

`PS C:\\\> cd cert:\LocalMachine\My`

`PS C:\\\> dir | format-list`

For more information about certificate stores, see [http://technet.microsoft.com//library/cc757138.aspx](https://technet.microsoft.com//library/cc757138.aspx).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Thumbprint

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that have the virtual machines for which you want to test the connection for replication.
NetBIOS names, IP addresses, and fully qualified domain names (FQDN) are allowed.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerName
Specifies the name of the Replica server to test for connectivity with the virtual machine to be replicated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReplicaServer

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerPort
Specifies the port on the Replica server to use to test connectivity.
Make sure you specify a port that is configured on the Replica server to support the same authentication type you specify using the AuthenticationType parameter in this cmdlet.
Run the **Get-VMReplicationServer** cmdlet on the Replica server to check the configuration of the port, or contact the administrator of the specified Replica server.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ReplicaPort

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

