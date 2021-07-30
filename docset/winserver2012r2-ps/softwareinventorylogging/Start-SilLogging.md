---
external help file: MsftSil_ManagementTasks-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/start-sillogging?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-SilLogging
---

# Start-SilLogging

## SYNOPSIS
Starts Software Inventory Logging hourly logging.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

## SYNTAX

```
Start-SilLogging [[-CimSession] <CimSession[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SilLogging** cmdlet starts Software Inventory Logging hourly logging.
Once logging is started, Software Inventory Logging collects data hourly from Software Inventory Logging data sources, and then forwards this data over the network to an aggregation server.
Specify an aggregation server and certificate thumbprint by using the Set-SilLogging cmdlet.

## EXAMPLES

### Example 1: Start logging
```
PS C:\> Start-SilLogging
```

This command starts Software Inventory Logging for the current computer.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SilLogging](./Get-SilLogging.md)

[Set-SilLogging](./Set-SilLogging.md)

[Stop-SilLogging](./Stop-SilLogging.md)

[Publish-SilData](./Publish-SilData.md)

