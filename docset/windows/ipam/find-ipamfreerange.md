---
author: brianlic
description: 
external help file: IpamRange.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Find-IpamFreeRange
ms.assetid: 1C04AE5F-128B-4C48-8C6C-FA38B98C34D4
---

# Find-IpamFreeRange

## SYNOPSIS
Finds one or more free IP ranges from a specified subnet.

## SYNTAX

```
Find-IpamFreeRange [-InputObject] <CimInstance> [-NumberOfAddresses] <UInt32> [[-NumberOfRanges] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Find-IpamFreeRange** cmdlet finds available IP address ranges from a specified subnet in the IP Address Management (IPAM) database.
An IP range is a unique collection of IP addresses, generally corresponding to a Dynamic Host Configuration Protocol (DHCP) scope.
The subnet within which free IP range is to be searched is passed in InputObject parameter.

## EXAMPLES

### Example 1: Find free ranges that have 256 IP addresses
```
PS C:\>$Subnet = Get-IpamSubnet -NetworkId 12.1.0.0/16
PS C:\> Find-IpamFreeRange -InputObject $Subnet -NumberOfAddresses 256
StartIPAddress : 12.1.0.0
EndIPAddress   : 12.1.0.255
NetworkId      : 12.1.0.0/16
```

The first command gets the IPAM subnet for a specific network ID and stores it in the variable named $Subnet.
The second command finds all the free IP ranges of the subnet specified in the $Subnet variable that have IP addresses of 256.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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
{{Fill InputObject Description}}

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

### -NumberOfAddresses
Specifies the size of the IP range to be returned.
This number denotes the number of free IP addresses required in the IP range.

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

### -NumberOfRanges
Specifies the number of free IP ranges to be returned.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
The cmdlet returns an instance of the **IpamFreeRange** object.

## NOTES

## RELATED LINKS

[Find-IpamFreeAddress](./Find-IpamFreeAddress.md)

[Find-IpamFreeSubnet](./Find-IpamFreeSubnet.md)

