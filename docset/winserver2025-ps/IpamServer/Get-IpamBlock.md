---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamBlock.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamblock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamBlock
---

# Get-IpamBlock

## SYNOPSIS
Gets a set of address blocks from IPAM.

## SYNTAX

### ByNetworkId
```
Get-IpamBlock -NetworkId <String[]> -StartIPAddress <IPAddress[]> -EndIPAddress <IPAddress[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAddressFamily
```
Get-IpamBlock [-AddressFamily] <AddressFamily[]> [[-AddressCategory] <AddressCategory[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByParent
```
Get-IpamBlock -MappingToParentBlock <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamBlock** cmdlet gets a set of IP address blocks from IP Address Management (IPAM).
Specify the *AddressFamily* parameter to get a set of IP addresses for address families.
Specify the *NetworkId*, *StartIPAddress*, and *EndIPAddress* parameters to get a set of IP address blocks for networks.
Specify the *MappingToParentBlock* parameter to get all child IP address ranges that belong to an address block.

## EXAMPLES

### Example 1: Get all private IPv4 address blocks
```
PS C:\> Get-IpamBlock -AddressFamily IPv4 -AddressCategory Private | Format-List NetworkId, StartIPAddress, EndIPAddress
NetworkId      : 10.0.0.0/8

StartIPAddress : 10.0.0.0

EndIPAddress   : 10.255.255.255
```

This command gets all private IPv4 blocks in IPAM.
The command returns only the top-level blocks in the block hierarchy.
The command uses the **Format-List** cmdlet to display the output in the form of a table.
For more information, type `Get-Help Format-Table`.

### Example 2: Get an address block by using a network Id
```
PS C:\> Get-IpamBlock -NetworkId "10.0.0.0/8" -StartIPAddress 10.0.0.0 -EndIPAddress 10.255.255.255
Utilization        : Under

NetworkId          : 10.0.0.0/8

StartAddress       : 10.0.0.0

EndAddress         : 10.255.255.255

Rir                :

LastAssignedDate   :

TotalAddresses     : 16777216

AssignedAddresses  : 2440

UtilizedAddresses  : 732

PercentageUtilized : 30

AddressCategory    : Private

Owner              :

Description        : IP block to be used for Region1

RirReceivedDate    :

PercentageAssigned : 0.01454353
```

This command gets the IP address block from the network that has the ID 10.0.0.0/8.
The command specifies the start and end addresses for the address block.

### Example 3: Get child IP address ranges mapped to an address block
```
PS C:\> $Parent = Get-IpamBlock -NetworkId "10.0.0.0/8" -StartIPAddress 10.0.0.0 -EndIPAddress 10.255.255.255PS
C:\> Get-IpamBlock -MappingToParentBlock $Parent
Utilization        : Under

NetworkId          : 10.11.0.0/16

StartAddress       : 10.11.0.0

EndAddress         : 10.11.255.255

Rir                :

LastAssignedDate   :

TotalAddresses     : 65536

AssignedAddresses  : 200

UtilizedAddresses  : 90

PercentageUtilized : 45

AddressCategory    : Private

Owner              :

Description        : IP block to be used for Region1

RirReceivedDate    :

PercentageAssigned : 0.3051758
Utilization        : Under

NetworkId          : 10.12.0.0/16

StartAddress       : 10.12.0.0

EndAddress         : 10.12.255.255

Rir                :

LastAssignedDate   :

TotalAddresses     : 65536

AssignedAddresses  : 0

UtilizedAddresses  : 0

PercentageUtilized : 0

AddressCategory    : Private

Owner              :

Description        : IP block to be used for Region1

RirReceivedDate    :

PercentageAssigned : 0
```

This example gets all child IP address ranges for an address block.

The first command gets an **IpamBlock** object that contains the IP address block from the network that has the ID 10.0.0.0/8.
The command stores the **IpamBlock** object in the $Parent variable.

The second command gets all the child IP address ranges for the address block stored in $Parent.

## PARAMETERS

### -AddressCategory
Specifies an array of IP address categories.
If you specify this parameter, you must specify the *AddressFamily* parameter.

The acceptable values for this parameter are:

- Public
- Private

```yaml
Type: AddressCategory[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: Public, Private, Global

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressFamily
Specifies an array of address families of IP addresses.

The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -EndIPAddress
Specifies an array of end addresses for IP address blocks.

```yaml
Type: IPAddress[]
Parameter Sets: ByNetworkId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingToParentBlock
Specifies an **IpamBlock** object.
This is the parent address block.
The cmdlet gets all the child IP address ranges for the parent address block.

```yaml
Type: CimInstance
Parameter Sets: ByParent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NetworkId
Specifies an IP network prefix, in Classless InterDomain Routing (CIDR) notation.

```yaml
Type: String[]
Parameter Sets: ByNetworkId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies an array of start addresses for IP address blocks.

```yaml
Type: IPAddress[]
Parameter Sets: ByNetworkId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Set-IpamBlock](./Set-IpamBlock.md)

[Add-IpamBlock](./Add-IpamBlock.md)

[Remove-IpamBlock](./Remove-IpamBlock.md)

