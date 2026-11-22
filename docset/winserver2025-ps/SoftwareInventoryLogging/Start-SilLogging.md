---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftSil_ManagementTasks.psm1-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 01/24/2017
online version: https://learn.microsoft.com/powershell/module/softwareinventorylogging/start-sillogging?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-SilLogging
---

# Start-SilLogging

## SYNOPSIS
Starts Software Inventory Logging daily logging.

## SYNTAX

```
Start-SilLogging [[-CimSession] <CimSession[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SilLogging** cmdlet starts Software Inventory Logging daily logging.
If logging is started, Software Inventory Logging collects data daily from all Software Inventory Logging data sources, and then forwards this data over the network to an aggregation server.
Specify an aggregation server by using the Set-SilLogging cmdlet.
If you do not specify an aggregation server and the server is a virtual machine that runs on a Hyper-V host, then the daily collection forwards the Software Inventory Logging data to a location that its Windows Server host can access.

## EXAMPLES

### Example 1: Start Software Inventory Logging for the current computer
```
PS C:\> Start-SilLogging
```

This command starts Software Inventory Logging for the current computer.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-SilLogging](./Get-SilLogging.md)

[Set-SilLogging](./Set-SilLogging.md)

[Stop-SilLogging](./Stop-SilLogging.md)

[Publish-SilData](./Publish-SilData.md)

