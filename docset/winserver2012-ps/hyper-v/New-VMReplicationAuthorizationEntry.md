---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vmreplicationauthorizationentry?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VMReplicationAuthorizationEntry

## SYNOPSIS
Creates a new authorization entry that allows one or more primary servers to replicate data to a specified Replica server.

## SYNTAX

```
New-VMReplicationAuthorizationEntry [-AllowedPrimaryServer] <String> [-ReplicaStorageLocation] <String>
 [-TrustGroup] <String> [-ComputerName <String[]>]
```

## DESCRIPTION
The **New-VMReplicationAuthorizationEntry** cmdlet creates a new authorization entry that allows one or more primary servers to replicate data.
To use this cmdlet, the value of the ReplicationAllowedFromAnyServer property of the Replica server must be false.
You can use the Get-VMReplicationServer cmdlet to check the value of this property.

## EXAMPLES

### Example 1
```
PS C:\>New-VMReplicationAuthorizationEntry server01.domain01.contoso.com D:\ReplicaVMStorage DEFAULT
```

This example creates a replication authorization entry on the local server for a primary server named server01.domain01.contoso.com and a trust group named DEFAULT.
It also specifies D:\ReplicaVMStorage as the location to create replica virtual hard disks for virtual machines replicated from server01.domain01.contoso.com.

### Example 2
```
PS C:\>New-VMReplicationAuthorizationEntry *.domain01.contoso.com D:\ReplicaVMStorage MyDomain01 -ComputerName server02.domain01.contoso.com
```

This example creates a replication authorization entry on server server02.domain01.contoso.com that allows replication from all primary servers in the domain domain01.contoso.com that also belong to the trust group MyDomain01.
It also specifies D:\ReplicaVMStorage as the location to create replica virtual hard disks for virtual machines replicated from these allowed primary servers.

## PARAMETERS

### -AllowedPrimaryServer
Specifies the server that is allowed to send replication data to the Replica server.
Only fully-qualified domain names and fully qualified international domain names are supported.
You can use a wildcard (for example, "*") in the first octect to specify a fully qualified domain name, such as *.contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the authorization entry is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaStorageLocation
Specifies the location to store the Replica virtual hard disk files sent from the allowed server when a new Replica virtual machine is created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustGroup
Identifies a group of primary servers within which a given primary virtual machine can move so replications of the primary virtual machine are accepted by the Replica server only from primary servers that belong to the trust group.
You can use any string to create a new trust group.
Ensure all primary servers within a specific trust group use the same string as the value you specify for this parameter.

Use of a trust group can help you keep virtual machines isolated by maintaining control over which primary servers are trusted to provide replication, while also allowing the virtual machines to move from one primary server to another (such as through live migration or failover from a cluster node).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VMReplicationAuthorizationEntry

## NOTES

## RELATED LINKS



