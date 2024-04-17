---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/new-sbecunattendfragment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SbecUnattendFragment
---

# New-SbecUnattendFragment

## SYNOPSIS
Creates a fragment for Unattend.xml with post-install commands.

## SYNTAX

```
New-SbecUnattendFragment [-CollectorIp] <String> [-CollectorPort] <UInt32> [-Key] <String>
 [[-BusParameters] <String>] [[-Logger] <String[]>] [[-PermLogger] <String[]>] [-NoDefaultLoggers]
 [[-LogDbgMask] <UInt32>] [[-FirstOrder] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SbecUnattendFragment** cmdlet creates a fragment for Unattend.xml with post-install commands.
You use these commands to configure Setup and Boot Event monitoring on the image that you are preparing.

The fragment generated represents the text of the `<RunSynchronous>` element.
That element is normally inserted into the Unattend.xml in `<Component name="Microsoft-Windows-Setup">`, after `<DiskConfiguration>`.

The generated fragment relies on the winpeshl.ini file created in the WinPE boot image by Enable-SbecBootImage and will not work without it.

The hash table that this cmdlet returns contains the following elements:

- `<UnattendText>`.
Text of the XML fragment for insertion into Unattend.xml, as an array of strings.
- `<NextOrder>`.
The next uint32 value for `<Order>` in case if you want to add more commands to the fragment.
See the description of the *FirstOrder* parameter for more information.

## EXAMPLES


## PARAMETERS

### -BusParameters
Specifies the bus parameters to use to select the NIC of the target computer for communication.
This value overrides the default choice of the first supported adapter.
This value applies to all the computers that use this image; it can be used only if the hardware of these computers is sufficiently homogeneous.

To find the value of bus parameters for a specific NIC on a machine, open Device Manager, and in Network Adapters select the desired device.
Right-click the device, select Properties, select the Details tab, and then select Location information.
It displays a string of the form PCI bus X, device Y, function Z.
The bus parameter to specify in this example is "X,Y,Z".

```yaml
Type: String
Parameter Sets: (All)
Aliases: BusParams

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorIp
Specifies the IPv4 address of the host on which the Boot Event Collector is located.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorPort
Specifies the port number (common for the target and collector).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FirstOrder
Specifies the value with which to start the numbering of the auto-generated commands.

The commands in the Unattend.xml must be sequentially ordered by the value in the `<Order>` element.
Normally the order starts with 1 by default, but if you prepend your own commands, the auto-generated commands must begin with a greater value.

If you specify this parameter, even with the value 1, the text of the XML fragment is generated without the surrounding `<RunSynchronous>` element, because you would presumably want to assemble that element from multiple parts.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key
Specifies the encryption key for the communication.
This value must match the key specified in the collector configuration for this target.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogDbgMask
Specifies the value for the Debug Print Filter bit mask that enables the messages from **DbgPrint**().
The 0x1 bit must be set to allow the messages with the Bugcheck system crash information.
If the mask is set to 0, the command for setting this Registry value is not created.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logger
Specifies the AutoLogger sessions for which to enable forwarding.
The forwarding on these sessions auto-disables after the operating system starts.
Specifying a session explicitly in *Logger* or *PermLogger* overrides the defaults for it.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDefaultLoggers
Indicates that this operation does not automatically add the default set of logger sessions.

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

### -PermLogger
Specifies the AutoLogger sessions for which to enable forwarding.
The forwarding on these sessions remains enabled after the operating system starts.
Specifying a session explicitly in *Logger* or *PermLogger* overrides the defaults for it.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### hash table
This cmdlet returns a hash table that contains the following elements:

- `<UnattendText>`.
Text of the XML fragment to insert into Unattend.xml as an array of strings.
- `<NextOrder>`.
The next uint32 value for `<Order>` if you want to add more commands to the fragment.
For more information, see the *FirstOrder* parameter.

## NOTES

## RELATED LINKS

[Enable-SbecAutologger](./Enable-SbecAutologger.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

[Enable-SbecWdsBcd](./Enable-SbecWdsBcd.md)

