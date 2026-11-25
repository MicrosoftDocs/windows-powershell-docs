---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/stop-sbecinstance?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-SbecInstance
---

# Stop-SbecInstance

## SYNOPSIS
Stops the Setup and Boot Event Collector.

## SYNTAX

### Service
```
Stop-SbecInstance [-Service] [-Force] [<CommonParameters>]
```

### Direct
```
Stop-SbecInstance [-Direct] [-ComputerName <String[]>] [-CimSession <CimSession[]>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SbecInstance** cmdlet stops an instance of the Setup and Boot Event Collector.

You must have the Builtin Administrator privilege to run this cmdlet.

## EXAMPLES

### Example 1: Stop the Boot Event Collector service
```
PS C:\> Stop-SbecInstance -Service
```

This command stops the Boot Event Collector service.

### Example 2: Stop a Boot Event Collector instance
```
PS C:\> Stop-SbecInstance -Direct
```

This command stops an instance of Boot Event Collector that was started from the command line.

### Example 3: Immediately stop a Boot Event Collector instance
```
PS C:\> Stop-SbecInstance -Direct -Force
```

This command stops an instance of Boot Event Collector that was started from the command line, and discards any buffered but not-yet processed data.

## PARAMETERS

### -CimSession
Runs the cmdlet on the remote computers through a remote session.
Enter a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet or an array of these objects.
The default is to run the cmdlet on the local computer.
For more information, see About_CimSession.

```yaml
Type: CimSession[]
Parameter Sets: Direct
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computers on which you want to perform the operation.
You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.
For more information see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on MSDN.

```yaml
Type: String[]
Parameter Sets: Direct
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direct
Stops the Setup and Boot Event Collector instance directly through the WMI/CIM interface.
Specify this parameter to stop an instance of the Setup and Boot Event Collector that was started from a command prompt.

If multiple instances are running (including the service), specifying this parameter stops a random instance, because WMI connects to a random instance.
Do not use this parameter with the service, because the service controller interprets it as a service failure and restarts it.

```yaml
Type: SwitchParameter
Parameter Sets: Direct
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
With the *Service* parameter, this parameter acts as a pass-through parameter for **Stop-Service**, allowing the cmdlet to stop a service even if that service has dependent services.
With *Direct*, requests the fast stopping, discarding the buffered but not yet fully processed data.

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

### -Service
Stops the Setup and Boot Event Collector service on the current computer.

```yaml
Type: SwitchParameter
Parameter Sets: Service
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SbecActiveConfig](./Get-SbecActiveConfig.md)

[Save-SbecInstance](./Save-SbecInstance.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Start-SbecInstance](./Start-SbecInstance.md)

[Test-SbecActiveConfig](./Test-SbecActiveConfig.md)

