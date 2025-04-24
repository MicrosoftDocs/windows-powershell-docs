---
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
---

# Stop-WorkgroupCluster

## SYNOPSIS
Stop a workgroup cluster.

## SYNTAX

```
Stop-WorkgroupCluster [[-Node] <String[]>] [[-Credentials] <PSCredential[]>] [-Confirm]
 [-AuthenticationMethod] <WorkgroupClusterAuthenticationMethod> [<CommonParameters>]
```

## DESCRIPTION
The Stop-WorkgroupCluster function stops a workgroup cluster. This cmdlet takes the specified workgroup cluster offline, using the provided credentials and authentication method. You can optionally prompt for confirmation before stopping the cluster.

## EXAMPLES

### EXAMPLE 1
```
Stop-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example stops the cluster.

## PARAMETERS

### -AuthenticationMethod
Specifies the authentication method to use when stopping the workgroup cluster. Acceptable values are:
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
You can pipe an array of node names to this cmdlet.

### System.Management.Automation.PSCredential[]
You can pipe an array of credentials to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output. It performs the operation of stopping a workgroup cluster.

## NOTES

## RELATED LINKS
