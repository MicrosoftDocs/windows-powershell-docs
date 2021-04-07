---
author: Kateyanne
description: 
external help file: ClusterAwareUpdating.dll-Help.xml
manager: jasgro
Module Name: ClusterAwareUpdating
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/get-caurun?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauRun
---

# Get-CauRun

## SYNOPSIS
Retrieves status information about an Updating Run currently in progress.

## SYNTAX

### DefaultParamSet (Default)
```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ShowClusterNodeState
```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-ShowClusterNodeState] [<CommonParameters>]
```

### WaitForCompletion
```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-WaitForCompletion] [<CommonParameters>]
```

### WaitForStart
```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-WaitForStart] [<CommonParameters>]
```

## DESCRIPTION
The **Get-CauRun** cmdlet retrieves status information about an Updating Run currently in progress.
Use this cmdlet to monitor current Updating Runs.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-CauRun -ClusterName CONTOSO-FC1
RunId                   : 834dd11e-584b-41f2-8d22-4c9c0471dbad 
RunStartTime            : 10/13/2011 1:35:39 PM 
CurrentOrchestrator     : NODE1 
NodeStatusNotifications : { 
Node      : NODE1 
Status    : Waiting 
Timestamp : 10/13/2011 1:35:49 PM 
} 
NodeResults             : { 
Node                     : NODE2 
Status                   : Succeeded 
ErrorRecordData          : 
NumberOfSucceededUpdates : 0 
NumberOfFailedUpdates    : 0 
InstallResults           : Microsoft.ClusterAwareUpdating.UpdateInstallResult[] 
}
```

This example gets status information about the Updating Run currently in progress on the cluster called CONTOSO-FC1.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster for which to get the Updating Run status.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

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

### -Credential
Specifies the administrative credentials for the target cluster.

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

### -ShowClusterNodeState
If this parameter is specified, the cmdlet retrieves the status of the WMI object that is created on each cluster node.
This can be used to debug the status of leftover objects.

```yaml
Type: SwitchParameter
Parameter Sets: ShowClusterNodeState
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Returns after the Updating Run has finished, and writes the updated CAU run objects to the output stream as progress is recorded by the current CAU Update Coordinator.

```yaml
Type: SwitchParameter
Parameter Sets: WaitForCompletion
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForStart
Returns only if there is an Updating Run in progress on the specified cluster, otherwise waits for an Updating Run to begin.

```yaml
Type: SwitchParameter
Parameter Sets: WaitForStart
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauRun

### Microsoft.ClusterAwareUpdating.RunState

## NOTES

## RELATED LINKS

[Invoke-CauRun](./Invoke-CauRun.md)

[Stop-CauRun](./Stop-CauRun.md)

