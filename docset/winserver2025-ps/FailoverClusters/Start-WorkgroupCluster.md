---
description: Starts a workgroup cluster, bringing the specified nodes online and making them available for use.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
ms.date: 04/24/2025
---

# Start-WorkgroupCluster

## SYNOPSIS
Starts a workgroup cluster.

## SYNTAX

```
Start-WorkgroupCluster [[-Node] <String[]>] [[-Credentials] <PSCredential[]>] [-IgnorePersistentState]
 [-AuthenticationMethod] <WorkgroupClusterAuthenticationMethod> [<CommonParameters>]
```

## DESCRIPTION
The Start-WorkgroupCluster function starts a workgroup cluster. This cmdlet brings the specified workgroup cluster online, using the provided credentials and authentication method. You can optionally ignore the persistent state of the cluster when starting it.

## EXAMPLES

### EXAMPLE 1
```
Start-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example starts the cluster.

## PARAMETERS

### -AuthenticationMethod
Specifies the authentication method to use when starting the workgroup cluster. Acceptable values are:
- `Certificates`: Uses certificate-based authentication for secure communication between nodes.
- `NoCertificates`: Uses local user accounts and passwords for authentication without certificates.

```yaml
Type: WorkgroupClusterAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: Certificates, NoCertificates

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials
An array of credentials for the nodes.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnorePersistentState
Indicates that the cmdlet should start the cluster without restoring the previous persistent state. This can be useful if you want to start the cluster in a clean state, ignoring any saved cluster state from previous operations.

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

### -Node
An array of nodes that form the current cluster.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: @()
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
You can pipe an array of node names to this cmdlet.

### System.Management.Automation.PSCredential[]
You can pipe an array of credentials to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output. It performs the operation of starting a workgroup cluster.

## NOTES

## RELATED LINKS
