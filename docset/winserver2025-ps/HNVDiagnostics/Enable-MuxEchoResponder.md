---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MuxEchoResponder.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/enable-muxechoresponder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-MuxEchoResponder
---

# Enable-MuxEchoResponder

## SYNOPSIS
Enables an ICMP echo responder. This cmdlet has been deprecated.

## SYNTAX

```
Enable-MuxEchoResponder [-TargetVIP] <String> [[-SequenceNumber] <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MuxEchoResponder** cmdlet enables an ICMP echo responder in a multiplexer (MUX).

You should run this cmdlet on a MUX virtual machine, either locally or through remote PowerShell.

## EXAMPLES

### Example 1: Enable an echo responder
```
PS C:\> Enable-MuxEchoResponder -TargetVIP "10.123.176.108" -SequenceNumber 27
```

This command enables the specified echo responder.

## PARAMETERS

### -SequenceNumber
Specifies the ICMP sequence number of the echo responder to disable.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVIP
Specifies the target virtual IP address of the echo responder to enable.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-MuxEchoResponder](./Disable-MuxEchoResponder.md)

