---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clustergenericscriptrole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterGenericScriptRole
---

# Add-ClusterGenericScriptRole

## SYNOPSIS
Configures an application controlled by a script that runs in Windows Script Host, within a failover
cluster.

## SYNTAX

```
Add-ClusterGenericScriptRole -ScriptFilePath <String> [-Storage <StringCollection>]
 [-StaticAddress <StringCollection>] [-IgnoreNetwork <StringCollection>] [[-Name] <String>]
 [-Wait <Int32>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterGenericScriptRole` cmdlet configures an application controlled by a script that
runs in Windows Script Host, within a failover cluster.

The script provides the cluster software with information about the current state of the
application. As needed, the cluster software will restart or fail over the script. Through the
script, the application will be restarted or failed over.

> [!NOTE]
> This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
> authentication on the server computer.

## EXAMPLES

### Example 1: Configure a script to run on a failover cluster

```powershell
Add-ClusterGenericScriptRole -ScriptFilePath "script1.vbs"
```

This example configures the script named `script1.vbs` to run within a failover cluster, using
defaults for the name and IP address, and doesn't assign a disk.

### Example 2: Configure a script on a failover cluster and assign a clustered script name

```powershell
Add-ClusterGenericScriptRole -ScriptFilePath "script1.vbs" -Storage "Cluster Disk 4" -Name "script1"
```

This example configures the script named `script1.vbs` to run within a failover cluster and use
`Cluster Disk 4`. The cmdlet assigns the clustered script the name script1.

### Example 3: Configure a script to run on a fail over cluster without waiting for resources

```powershell
Add-ClusterGenericScriptRole -ScriptFilePath "script1.vbs" -Wait 0
```

This example configures the script called `script1.vbs` to run within a failover cluster, using
defaults for the name and IP address, and doesn't assign a disk. The cmdlet completes without
waiting for all resources to come online.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -IgnoreNetwork

Specifies one or more networks to ignore when running the cmdlet. Networks with DHCP enabled are
always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the cluster on which to create the highly available script.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the highly available script to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptFilePath

Specifies the path of the script file to use for the highly available script.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticAddress

Specifies one or more static addresses to use when running the cmdlet. Networks with DHCP enabled
are always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage

Specifies the cluster disk resource to be added to the created highly available script.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If the value `0` is specified, then the call is initiated and
the cmdlet returns without waiting.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterGenericApplicationRole](./Add-ClusterGenericApplicationRole.md)

[Add-ClusterGenericServiceRole](./Add-ClusterGenericServiceRole.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)
