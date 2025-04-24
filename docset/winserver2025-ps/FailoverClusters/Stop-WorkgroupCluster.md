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
The Stop-WorkgroupCluster function stops a workgroup cluster.

## EXAMPLES

### EXAMPLE 1
```
Stop-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example stops the cluster.

## PARAMETERS

### -AuthenticationMethod
{{ Fill AuthenticationMethod Description }}

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

## OUTPUTS

## NOTES

## RELATED LINKS
