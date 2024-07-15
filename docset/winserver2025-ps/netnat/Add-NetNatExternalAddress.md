---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNatExternalAddress.cdxml-help.xml
Module Name: NetNat
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netnat/add-netnatexternaladdress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetNatExternalAddress
---

# Add-NetNatExternalAddress

## SYNOPSIS
Adds an external address to a NAT instance.

## SYNTAX

```
Add-NetNatExternalAddress [-NatName] <String> -IPAddress <String> [-PortStart <UInt16>] [-PortEnd <UInt16>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetNatExternalAddress** cmdlet adds an external address to a network address translation (NAT) instance.

## EXAMPLES

### Example 1: Add an external address
```
PS C:\> Add-NetNatExternalAddress -IPAddress "a.b.c.0/24"
```

This command adds the external address 10.20.30.120 to a NAT.
This example uses the placeholder a.b.c.0/24 to represent a public Internet address prefix.

### Example 2: Add an external address and a port range
```
PS C:\> Add-NetNatExternalAddress -IPAddress "a.b.c.0/24" -PortEnd 19999 -PortStart 10000
```

This command adds an external address to a specified NAT, and specifies a range of ports to use for outbound connections.
This example uses the placeholder a.b.c.0/24 to represent a public Internet address prefix.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -IPAddress
Specifies an external IP address for a NAT, as a string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NatName
Specifies the name for the NAT instance, as a string.

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

### -PortEnd
Specifies the high end of a dynamic port range from which to pick a port for a NAT session.
Choose a port number that is greater than the *PortStart* parameter from the available ports.
NAT associates a port number with an external address to identify the mapping between an internal network and an external network.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortStart
Specifies the low end of a dynamic port range from which to pick a port for a NAT session.
Choose a port number that is less than the *PortEnd* parameter from the available ports.
NAT associates a port number with an external address to identify the mapping between an internal network and an external network.

```yaml
Type: UInt16
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNatExternalAddress

## NOTES

## RELATED LINKS

[Get-NetNatExternalAddress](./Get-NetNatExternalAddress.md)

[Remove-NetNatExternalAddress](./Remove-NetNatExternalAddress.md)

