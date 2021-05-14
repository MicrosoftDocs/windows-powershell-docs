---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://docs.microsoft.com/powershell/module/printmanagement/add-printerport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-PrinterPort

## SYNOPSIS
Installs a printer port on the specified computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-PrinterPort [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-PrinterPort [-Name] <String> [-LprHostAddress] <String> [-LprQueueName] <String> [-AsJob]
 [-CimSession <CimSession>] [-ComputerName <String>] [-LprByteCounting] [-SNMP <UInt32>]
 [-SNMPCommunity <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-PrinterPort [-Name] <String> [-PrinterHostAddress] <String> [-AsJob] [-CimSession <CimSession>]
 [-ComputerName <String>] [-PortNumber <UInt32>] [-SNMP <UInt32>] [-SNMPCommunity <String>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-PrinterPort [-HostName] <String> [-PrinterName] <String> [-AsJob] [-CimSession <CimSession>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-PrinterPort** cmdlet creates a new printer port on the specified computer. 
You can create a local printer port, a printer port using TCP, and LPR printer ports by using **Add-PrinterPort** cmdlet.

You cannot use wildcard characters with **Add-PrinterPort**.
You can use **Add-PrinterPort** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Add-PrinterPort**.

## EXAMPLES

### -------------------------- Example 1: Creates a local printer port -------------------------- xample: Create a local printer port
```
PS C:\> Add-PrinterPort -Name "LocalPort:"
```

This command creates a local printer port named LocalPort on the local computer.

### -------------------------- Example 2: Creates a TCP  printer port  -------------------------- xample: Create a TCP printer port
```
PS C:\> Add-PrinterPort -Name "TCPPort:" -PrinterHostAddress "192.168.100.100"
```

This command creates a TCP printer port named TCPPort: with an IP address of 192.168.100.100 on the computer.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer to which to add the printer port.
If not specified, the printer port is added to the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the host name of the computer on which to add LPR printer port.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LprByteCounting
Enables LPR byte counting for a TCP/IP printer port in LPR mode.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LprQueueName
Specifies the LPR queue name when installing a TCP/IP printer port in LPR mode.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer port to install on the specified computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortNumber
Specifies the TCP/IP port number for the printer port added to the specified computer.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer installed on the LPR printer port.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SNMP
Enables SNMP and specifies the index for TCP/IP printer port management.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

