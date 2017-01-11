---
author: brianlic
description: 
external help file: HgsServer-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Clear-HgsServer
ms.assetid: AAE0C591-6B5E-42B3-B547-1AEC29E96C86
---

# Clear-HgsServer

## SYNOPSIS
Resets the Host Guardian Service on the local node to the uninitialized state.

## SYNTAX

```
Clear-HgsServer [[-ClusterName] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-HgsServer** cmdlet removes a local node from the Host Guardian Service (HGS).

This cmdlet makes the following infrastructure component changes on the additional HGS node: 

- Unregisters the Attestation service web application with the IIS service.
- Unregisters the Key Protection service web application with the IIS service.
- Disables Just Enough Administration on the local node.
- Removes the local node from the existing failover cluster.

This cmdlet makes the following infrastructure components changes on the last HGS node: 

- Unregisters the Attestation service web application with the IIS service.
- Unregisters the Key Protection service web application with the IIS service.
- Removes the Distributed Network Name resource corresponding to the Host Guardian Service name.
- Disables Just Enough Administration on the local node.
- Destroys the cluster on the local node.

For more information about the scenario terms, see Security and Assurancehttp://go.microsoft.com/fwlink/?LinkId=699209 (http://go.microsoft.com/fwlink/?LinkId=699209).

## EXAMPLES

### Example 1: Clear all cluster initialization settings from the local node
```
PS C:\>Clear-HgsServer
```

This command returns the HGS Server on the local node to a clean state to prepare it for the **Initialize-HgsServer** command.

### Example 2: Clear all cluster initialization settings from the local node without confirmation
```
PS C:\>Clear-HgsServer -Force -Confirm:$False
```

This command returns the HGS Server on the local node to a clean state to prepare it for the **Initialize-HgsServer** command and does not prompt for confirmation.

## PARAMETERS

### -ClusterName
{{Fill ClusterName Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[HGS Server Cmdlets](./index.md)

[Initialize-HgsServer](./Initialize-HgsServer.md)

