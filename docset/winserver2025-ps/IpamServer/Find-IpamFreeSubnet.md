---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/find-ipamfreesubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Find-IpamFreeSubnet
---

# Find-IpamFreeSubnet

## SYNOPSIS
Finds one or more free IP subnets in a specified IP block.

## SYNTAX

```
Find-IpamFreeSubnet [-InputObject] <CimInstance> [-SubnetPrefix] <UInt32> [[-NumberOfSubnets] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Find-IpamFreeSubnet** cmdlet finds available free subnets in the IP Address Management (IPAM) database in a specified IP block.
The IP block within which free IP subnet is to be searched is passed in InputObject parameter.

## EXAMPLES

### Example 1: Find free subnets with a specified subnet prefix
```
PS C:\> $IPAMBlock= Get-IpamBlock -NetworkId 10.1.0.0/16 -StartIPAddress 10.1.0.0 -EndIPAddress 10.1.255.255
PS C:\> Find-IpamFreeSubnet -InputObject $IPAMBlock -SubnetPrefix 24
```

This first command gets all IP addresses from network ID 10.1.0.0/16 with a specific range of IP addresses and stores the result in the variable named $IPAMBlock.
The second command then finds all the free subnets that have a subnet prefix of 24 that is contained in the variable named $IPAMBlock.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NumberOfSubnets
Specifies the number of free subnets to be returned.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetPrefix
Specifies the prefix for the subnet to be returned.
The prefix is an integer value indicating the number of bits set in a subnet mask.

The subnet prefix tells you the number of IP addresses available on that subnet.
For instance, a subnet with a prefix value of 24 has 256 IP addresses.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Find-IpamFreeAddress](./Find-IpamFreeAddress.md)

[Find-IpamFreeRange](./Find-IpamFreeRange.md)

