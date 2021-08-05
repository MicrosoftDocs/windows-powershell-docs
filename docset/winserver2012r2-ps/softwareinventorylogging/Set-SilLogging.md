---
external help file: MsftSil_ManagementTasks-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/set-sillogging?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SilLogging
---

# Set-SilLogging

## SYNOPSIS
Applies configuration settings for Software Inventory Logging.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

## SYNTAX

### TimeOfDay (Default)
```
Set-SilLogging -TimeOfDay <DateTime> [-CimSession <CimSession[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TargetUri
```
Set-SilLogging [-TimeOfDay <DateTime>] [-TargetUri <String>] [-CertificateThumbprint <String>]
 [-CimSession <CimSession[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SilLogging** cmdlet applies configuration settings for Software Inventory Logging.
If logging is started, Software Inventory Logging collects data hourly from Software Inventory Logging data sources, and then forwards this data over the network to an aggregation server.
This cmdlet sets the uniform resource identifier (URI) of the aggregation server, the certificate thumbprint needed for secure authentication, and optionally the date and time that the hourly collection is scheduled to start.

## EXAMPLES

### Example 1: Specify an aggregation server
```
PS C:\> Set-SilLogging -TargetUri "https://log03.hosts.contoso.com"
```

This command specifies an aggregation server for Software Inventory Logging for the current computer.

### Example 2: Specify a date and time for logging to start
```
PS C:\> Set-SilLogging -TimeOfDay "01/01/2013 5:00:00AM"
```

This command specifies the date and time that the computer starts forwarding Software Inventory Logging data.
Note that when you specify a date in the future, Software Inventory Logging does not start logging until that date and time.
If you specify a date in the past, only the time specified is relevant to the configuration setting.

## PARAMETERS

### -CertificateThumbprint
Specifies a certificate thumbprint as a string.
Software Inventory Logging encrypts logging data sent to the aggregation server by using this thumbprint.
If you do not specify a value for this parameter, Software Inventory Logging does not forward data.

```yaml
Type: String
Parameter Sets: TargetUri
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -TargetUri
Specifies the URI, as an HTTPS address, of an aggregation server.
If you do not specify a value for this parameter, Software Inventory Logging does not forward data.

```yaml
Type: String
Parameter Sets: TargetUri
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeOfDay
Specifies the time of day, as a **DateTime** object, to schedule Software Inventory Logging to forward data.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`. 
If you do not change the default value, Software Inventory Logging starts at the next 3:00:00 AM local system time.

```yaml
Type: DateTime
Parameter Sets: TimeOfDay
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: DateTime
Parameter Sets: TargetUri
Aliases: 

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

### None.

## NOTES

## RELATED LINKS

[Get-SilLogging](./Get-SilLogging.md)

[Start-SilLogging](./Start-SilLogging.md)

[Stop-SilLogging](./Stop-SilLogging.md)

[Publish-SilData](./Publish-SilData.md)

