---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationNextHopLookup.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Select-NetVirtualizationNextHop
ms.reviewer:
ms.assetid: 508CB567-F354-4AB9-805C-DCB62CDB9033
---

# Select-NetVirtualizationNextHop

## SYNOPSIS
Selects the next hop MAC address.

## SYNTAX

```
Select-NetVirtualizationNextHop [[-SourceCustomerAddress] <String>] [-DestinationCustomerAddress] <String>
 [-SourceVirtualSubnetID] <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Select-NetVirtualizationNextHop** cmdlet selects the next hop media access control (MAC) address to use to reach a destination virtual machine from a Hyper-V Network Virtualization database.
Use this cmdlet to diagnose connection issues.

## EXAMPLES

### Example 1: Select the next hop MAC address
```
PS C:\>Select-NetVirtualizationNextHop -DestinationCustomerAddress 10.20.20.6 -SourceCustomerAddress 10.20.20.5 -SourceVirtualSubnetID 5001
```

This command selects the next hop MAC address for the destination customer IP address, the source customer IP address, and the virtual subnet ID.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DestinationCustomerAddress
Specifies the Customer Address of a destination virtual machine.
If you specify an address, this cmdlet selects a next hop MAC address for this destination virtual machine.
A Customer Address is the IP address that a customer assigns to a virtual machine, based on their network infrastructure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceCustomerAddress
Specifies the Customer Address of a source virtual machine.
If you specify an address, this cmdlet selects a next hop MAC address for this source virtual machine.
A Customer Address is the IP address that a customer assigns to a virtual machine, based on their network infrastructure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVirtualSubnetID
Specifies a Hyper-V Network Virtualization tenant isolation ID of a source virtual machine.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

