---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmreplicationserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMReplicationServer
---

# Set-VMReplicationServer

## SYNOPSIS
Configures a host as a Replica server.

## SYNTAX

### AuthenticationPort (Default)
```
Set-VMReplicationServer [[-ReplicationEnabled] <Boolean>]
 [[-AllowedAuthenticationType] <RecoveryAuthenticationType>] [[-ReplicationAllowedFromAnyServer] <Boolean>]
 [-CertificateThumbprint <String>] [-DefaultStorageLocation <String>] [-KerberosAuthenticationPort <Int32>]
 [-CertificateAuthenticationPort <Int32>] [-MonitoringInterval <TimeSpan>] [-MonitoringStartTime <TimeSpan>]
 [-Force] [-Passthru] [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AuthenticationPortMapping
```
Set-VMReplicationServer [[-ReplicationEnabled] <Boolean>]
 [[-AllowedAuthenticationType] <RecoveryAuthenticationType>] [[-ReplicationAllowedFromAnyServer] <Boolean>]
 [-CertificateThumbprint <String>] [-DefaultStorageLocation <String>]
 [-KerberosAuthenticationPortMapping <Hashtable>] [-CertificateAuthenticationPortMapping <Hashtable>]
 [-MonitoringInterval <TimeSpan>] [-MonitoringStartTime <TimeSpan>] [-Force] [-Passthru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMReplicationServer** cmdlet configures a host as a Replica server and enables you to specify the types of authentication and ports to use for incoming replication traffic.

To restrict the replication traffic that the Replica server will accept by allowing it only from specific servers, use the **New-VMReplicationAuthorizationEntry** cmdlet.

## EXAMPLES

### Example 1
```powershell
PS C:\>  Set-VMReplicationServer $true -AllowedAuthenticationType Kerberos
```

This example configures the local host as a Replica server and specifies Kerberos for authentication.

### Example 2
```powershell
PS C:\>  Set-VMReplicationServer -ReplicationEnabled $true -AllowedAuthenticationType Kerberos -ReplicationAllowedFromAnyServer $true -DefaultStorageLocation d:\DefaultReplicaStorage
```

This example configures a Replica server that accepts replication from all authenticated servers and uses a default storage location of d:\DefaultReplicaStorage.

### Example 3
```powershell
PS C:\>  Set-VMReplicationServer -MonitoringInterval "12:00:00" -MonitoringStartTime "17:00:00"
```

This example configures the Replica server with a monitoring interval of 12 hours starting at 17:00 hours.

### Example 4
```powershell
PS C:\> $portmapping = @{"Server1.contoso.com" = 82; "Server2.contoso.com" = 81; "Broker.contoso.com" = 80}
PS C:\> Set-VMReplicationServer -KerberosAuthenticationPortMapping $portmapping
```

This example configures the nodes of the cluster to receive replication on different ports.
The first command declares a variable named portmapping and uses it to store the server names of the nodes and the port to use on each node.
The second command configures each node of the cluster to use port mapping for Kerberos authentication using the values stored in the portmapping variable.

## PARAMETERS

### -AllowedAuthenticationType
Specifies which authentication types the Replica server will use.
Allowed values are Kerberos, Certificate, or CertificateAndKerberos.

```yaml
Type: RecoveryAuthenticationType
Parameter Sets: (All)
Aliases: AuthType
Accepted values: Kerberos, Certificate, CertificateAndKerberos

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateAuthenticationPort
Specifies the port on which the Replica server will receive replication data using certificate-based authentication.
This parameter can be set only when the value of the AllowedAuthType parameter is Certificate or CertificateAndKerberos.

```yaml
Type: Int32
Parameter Sets: AuthenticationPort
Aliases: CertAuthPort

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateAuthenticationPortMapping
When using Hyper-V Replica with failover clustering and certificate-based authorization, you can use this parameter to specify a different port for each node of the cluster to receive replication.
We recommend that you specify a unique port for each node of the cluster, and one unique port for the Hyper-V Replica Broker.
This parameter can be set only when the Replica server is configured with an authentication type of Certificate or CertificateAndKerberos.

```yaml
Type: Hashtable
Parameter Sets: AuthenticationPortMapping
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the certificate to use for mutual authentication of the replication data.
This parameter is required only when Certificate is specified as the type of authentication.
Specify the thumbprint of a valid computer certificate from the Personal store.

The certificate must have all of the following properties to be valid:

- It must not be expired.
- It must include both client and server authentication extensions for extended key usage (EKU), and an associated private key.
- It must terminate at a valid root certificate.
- It must meet the requirements for the subject common name (CN):
  - For servers that are not clustered, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) should contain, the FQDN of the host.
  - For servers that are clustered, each node must have two certificates - one in which the subject common name (CN) or subject alternative name (DNS Name) is the name of the node, and the other in which subject common name (CN) or subject alternative name (DNS Name) is FQDN of the Hyper-V Replica Broker.

To display a list of certificates in the computer's My store and the thumbprint of each certificate, run the following commands:

`PS C:\\\> cd cert:\LocalMachine\My`

`PS C:\\\> dir | format-list`

For more information about certificate stores, see [Certificate stores](/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Thumbprint

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Configures Replica server settings for one or more Hyper-V hosts.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
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

### -DefaultStorageLocation
Specifies the default location to store the virtual hard disk files when a Replica virtual machine is created.
You must specify this parameter when ReplicationAllowedFromAnyServer is True.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageLoc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies whether the command runs without requiring confirmation.

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

### -KerberosAuthenticationPort
Specifies the port that the HTTP listener uses on the Replica server host.

```yaml
Type: Int32
Parameter Sets: AuthenticationPort
Aliases: KerbAuthPort

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KerberosAuthenticationPortMapping
When using Hyper-V Replica with failover clustering and Kerberos authorization, you can use this parameter to specify a different port for each node of the cluster to receive replication.
We recommend that you specify a unique port for each node of the cluster, and one unique port for the Hyper-V Replica Broker.
This parameter can be set only when the Replica server is configured with an authentication type of either Kerberos or CertificateAndKerberos.

```yaml
Type: Hashtable
Parameter Sets: AuthenticationPortMapping
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringInterval
Specifies how often (the monitoring interval) replication statistics are computed.
Valid values are: 1 hour, 2 hours, 3 hours, 4 hours, 6 hours, 8 hours, 12 hours, 24 hours, 2 days, 3 days, 4 days, 5 days, 6 days, 7 days.
Specify in the format days:hours:minutes:seconds, such as 01:00:00 for 1 hour, or 1.00:00:00 for 1 day.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringStartTime
Specifies when the monitoring interval starts.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMReplicationServer** object is to be passed through to the pipeline representing the replication settings of the Replica server.

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

### -ReplicationAllowedFromAnyServer
Specifies whether to accept replication requests from any server.
When specified as **true**, DefaultStorageLocation must also be specified.
The default storage location and DEFAULT trust group tag are used for virtual machine replicas.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AllowAnyServer

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationEnabled
Specifies whether the host is enabled as a Replica server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: RepEnabled

Required: False
Position: 0
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

## OUTPUTS

### None
Default

### VMRecoveryServer
If **-PassThru** is specified.

## NOTES

## RELATED LINKS
