---
author: Kateyanne
description: 
external help file: MsftSil_ManagementTasks-help.xml
manager: jasgro
Module Name: SoftwareInventoryLogging
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/stop-sillogging?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-SilLogging
---

# Stop-SilLogging

## SYNOPSIS
Stops Software Inventory Logging hourly logging.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see http://support.microsoft.com/kb/3000850.

## SYNTAX

```
Stop-SilLogging [[-CimSession] <CimSession[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SilLogging** cmdlet stops Software Inventory Logging hourly logging.
If logging is started, Software Inventory Logging collects data hourly from Software Inventory Logging data sources, and then forwards this data over the network to an aggregation server.
Specify an aggregation server and certificate thumbprint by using the Set-SilLogging cmdlet.

## EXAMPLES

### Example 1: Stop logging
```
PS C:\> Stop-SilLogging
```

This command stops Software Inventory Logging for the current computer.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SilLogging](./Get-SilLogging.md)

[Set-SilLogging](./Set-SilLogging.md)

[Start-SilLogging](./Start-SilLogging.md)

[Publish-SilData](./Publish-SilData.md)

