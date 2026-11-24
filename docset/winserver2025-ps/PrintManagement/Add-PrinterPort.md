---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterPortTasks_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/add-printerport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PrinterPort
---

# Add-PrinterPort

## SYNOPSIS
Installs a printer port on the specified computer.

## SYNTAX

### local (Default)
```
Add-PrinterPort [-Name] <String> [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### tcplpr
```
Add-PrinterPort [-Name] <String> [-ComputerName <String>] [-SNMP <UInt32>] [-SNMPCommunity <String>]
 [-LprHostAddress] <String> [-LprQueueName] <String> [-LprByteCounting] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### tcp
```
Add-PrinterPort [-Name] <String> [-ComputerName <String>] [-PrinterHostAddress] <String> [-PortNumber <UInt32>]
 [-SNMP <UInt32>] [-SNMPCommunity <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### lpr
```
Add-PrinterPort [-ComputerName <String>] [-HostName] <String> [-PrinterName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-PrinterPort** cmdlet creates a printer port on the specified computer.
You can create a local printer port, a printer port using TCP, and LPR printer ports by using **Add-PrinterPort**.

You cannot use wildcard characters with **Add-PrinterPort**.
You can use **Add-PrinterPort** in a Windows PowerShell remoting session.

You do not need administrator credentials to run **Add-PrinterPort**.

## EXAMPLES

### Example 1: Create a local printer port
```
Add-PrinterPort -Name "LocalPort:"
```

This command creates a local printer port named LocalPort on the local computer.

### Example 2: Create a TCP printer port
```
Add-PrinterPort -Name "TCPPort:" -PrinterHostAddress "192.168.100.100"
```

This command creates a TCP printer port named TCPPort: with an IP address of 192.168.100.100 on the computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer to which to add the printer port.
If you do not specify a value, the printer port is added to the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the host name of the computer on which to add LPR printer port.

```yaml
Type: String
Parameter Sets: lpr
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LprByteCounting
Indicates that this cmdlet enables LPR byte counting for a TCP/IP printer port in LPR mode.

```yaml
Type: SwitchParameter
Parameter Sets: tcplpr
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LprHostAddress
Specifies the LPR host address when installing a TCP/IP printer port in LPR mode.

```yaml
Type: String
Parameter Sets: tcplpr
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LprQueueName
Specifies the LPR queue name when installing a TCP/IP printer port in LPR mode.

```yaml
Type: String
Parameter Sets: tcplpr
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer port to install on the specified computer.

```yaml
Type: String
Parameter Sets: local, tcplpr, tcp
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortNumber
Specifies the TCP/IP port number for the printer port added to the specified computer.

```yaml
Type: UInt32
Parameter Sets: tcp
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterHostAddress
Specifies the host address of the TCP/IP printer port added to the specified computer.

```yaml
Type: String
Parameter Sets: tcp
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer installed on the LPR printer port.

```yaml
Type: String
Parameter Sets: lpr
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SNMP
Enables SNMP and specifies the index for TCP/IP printer port management.

```yaml
Type: UInt32
Parameter Sets: tcplpr, tcp
Aliases: SNMPIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SNMPCommunity
Specifies the SNMP community name for TCP/IP printer port management.

```yaml
Type: String
Parameter Sets: tcplpr, tcp
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterPort
This cmdlet returns an object that contains the new printer port.

## NOTES

## RELATED LINKS

[Get-PrinterPort](./Get-PrinterPort.md)

[Remove-PrinterPort](./Remove-PrinterPort.md)

