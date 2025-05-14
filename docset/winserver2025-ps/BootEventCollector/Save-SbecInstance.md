---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/save-sbecinstance?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-SbecInstance
---

# Save-SbecInstance

## SYNOPSIS
Writes in-memory buffers to disk.

## SYNTAX

```
Save-SbecInstance [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Save-SbecInstance** cmdlet writes the in-memory buffers of the running Setup and Boot Event Collector to disk.

When the command returns, the buffers of the forwarders in the Setup and Boot Event Collector are saved to disk, and thus all the data up to the point when the write request was received is saved to disk.

You must have the Builtin Administrator privilege to run this cmdlet.

The alias for this cmdlet is **Flush-SbecInstance**.

## EXAMPLES


## PARAMETERS

### -CimSession
Runs the cmdlet on the remote computers through a remote session.
Enter a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet, or an array of these objects.
The default is to run the cmdlet on the local computer.
For more information, see About_CimSession.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the names of the computers on which you want to perform the operation.
You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address for each computer.
For more information see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on MSDN.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Stop-SbecInstance](./Stop-SbecInstance.md)

[Test-SbecActiveConfig](./Test-SbecActiveConfig.md)

[Test-SbecConfig](./Test-SbecConfig.md)

