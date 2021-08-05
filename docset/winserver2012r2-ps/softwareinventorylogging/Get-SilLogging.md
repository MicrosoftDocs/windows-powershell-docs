---
external help file: MsftSil_ManagementTasks-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/get-sillogging?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SilLogging
---

# Get-SilLogging

## SYNOPSIS
Displays configuration settings for Software Inventory Logging.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

## SYNTAX

```
Get-SilLogging [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilLogging** cmdlet displays configuration settings for Software Inventory Logging.
If logging is started, Software Inventory Logging collects data hourly from Software Inventory Logging data sources, and then forwards this data over the network to an aggregation server.
Specify an aggregation server by using the Set-SilLogging cmdlet.
The cmdlet gets the state, either started or stopped, of the hourly collection, the date and time that the hourly collection is scheduled to start, the uniform resource identifier (URI) of the aggregation server, and the certificate thumbprint to use for secure authentication.

## EXAMPLES

### Example 1: Get settings for the current computer
```
PS C:\> Get-SilLogging
State                 : Running
TimeOfDay             : 1/1/2000 3:00:00 AM
Target URI            : https://log03.hosts.contoso.com
CertificateThumbprint : ‎39 21 c1 15 c1 5d 0e ca 5c cb 5b c4 f0 7d 21 d8 05 0b 56 6a
PSComputerName        :
```

This command displays the configuration settings for Software Inventory Logging.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSCustomObject

## NOTES

## RELATED LINKS

[Set-SilLogging](./Set-SilLogging.md)

[Start-SilLogging](./Start-SilLogging.md)

[Stop-SilLogging](./Stop-SilLogging.md)

[Publish-SilData](./Publish-SilData.md)

