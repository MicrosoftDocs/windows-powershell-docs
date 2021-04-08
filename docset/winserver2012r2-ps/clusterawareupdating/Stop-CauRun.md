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
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/stop-caurun?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-CauRun
---

# Stop-CauRun

## SYNOPSIS
Stops an Updating Run that is in progress on a cluster.

## SYNTAX

```
Stop-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-Wait] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-CauRun** cmdlet stops an Updating Run that is in progress on a failover cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Stop-CauRun -ClusterName CONTOSO-FC1 -Wait -Force
```

This example stops the Updating Run that is being performed by the CAU Update Coordinator that is configured on the cluster named CONTOSO-FC1.
The cmdlet waits to return until the canceled Updating Run has completely finished.
The cmdlet runs without displaying confirmation prompts.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster on which to stop an Updating Run that is in progress.
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

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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

### -Wait
Returns after the canceled Updating Run has completely finished.
Otherwise, returns as soon as the stop request has been acknowledged by the current CAU Update Coordinator.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-CauRun](./Get-CauRun.md)

[Invoke-CauRun](./Invoke-CauRun.md)

