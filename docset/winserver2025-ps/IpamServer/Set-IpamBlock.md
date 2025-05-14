---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamBlock.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamblock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamBlock
---

# Set-IpamBlock

## SYNOPSIS
Modifies an IP address block in IPAM.

## SYNTAX

### ByKeySet
```
Set-IpamBlock [-NetworkId] <String[]> [-StartIPAddress] <IPAddress[]> [-EndIPAddress] <IPAddress[]>
 [-NewNetworkId <String>] [-NewStartIpAddress <IPAddress>] [-NewEndIpAddress <IPAddress>] [-Rir <String>]
 [-RirReceivedDate <DateTime>] [-Description <String>] [-LastAssignedDate <DateTime>] [-Owner <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-IpamBlock -InputObject <CimInstance[]> [-NewNetworkId <String>] [-NewStartIpAddress <IPAddress>]
 [-NewEndIpAddress <IPAddress>] [-Rir <String>] [-RirReceivedDate <DateTime>] [-Description <String>]
 [-LastAssignedDate <DateTime>] [-Owner <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamBlock** cmdlet modifies an IP address block in IP Address Management (IPAM).
Specify an address block by using the *StartIPAddress* and *EndIPAddress* parameters, or use the *InputObject* parameter to specify the input to this cmdlet.

If you specify the *NewStartIPAddress*, *NewEndIPAddress*, or *NewNetworkId* parameters, the cmdlet resets the utilization trend information for the address block.

## EXAMPLES

### Example 1: Modify the description child IP address ranges
```
PS C:\> $Parent = Get-IpamBlock -NetworkId "10.0.0.0/8" -StartIPAddress 10.0.0.0 -EndIPAddress 10.255.255.255
PS C:\> Get-IpamBlock -MappingToParentBlock $Parent | Set-IpamBlock -Description "IP Blocks assigned to Site01" -PassThru
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

Description        : IP Blocks assigned to Site01

RirReceivedDate    :

PercentageAssigned : 0
Utilization        : Under

NetworkId          : 10.13.0.0/16

StartAddress       : 10.13.0.0

EndAddress         : 10.13.255.255

Rir                :

LastAssignedDate   :

TotalAddresses     : 65536

AssignedAddresses  : 0

UtilizedAddresses  : 0

PercentageUtilized : 0

AddressCategory    : Private

Owner              :

Description        : IP Blocks assigned to Site01

RirReceivedDate    :

PercentageAssigned : 0
```

This example modifies the description of all child IP address ranges that belongs to an address block.

The first command gets an **IpamBlock** object that contains the IP address block from the network that has the ID 10.0.0.0/8.
The command stores the **IpamBlock** object in the $Parent variable.

The second command gets all the child IP address ranges for the address block stored in the $Parent variable.
The command passes the child IP address ranges to the **Set-IpamBlock** cmdlet by using the pipeline operator.
The command modifies the description for the child IP address ranges.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Modify key properties of an address block
```
PS C:\> Get-IpamBlock -NetworkId "10.11.0.0/16" -StartIPAddress 10.11.0.0 -EndIPAddress 10.11.255.255 | Set-IpamBlock -NewNetworkId 10.13.0.0/16 -NewStartIPAddress 10.13.0.0 -NewEndIpAddress 10.13.255.255


Confirm

Changing the NetworkId, StartIPAddress, EndIPAddress of an IP address block will reset its utilization trend information

Do you want to continue? Y
```

This command uses the Get-IpamBlock to get the IP address block from the network that has the ID 10.11.0.0/16.
The command specifies the start and end address of the address block.
The command passes the address block to the **Set-IpamBlock** cmdlet by using the pipeline operator.
The **Set-IpamBlock** cmdlet specifies new values for the network ID, start address and end address for the address block.
Because the command modifies the network ID, start address, and end address of the address block, the command resets the utilization trend of the address block.

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

### -Description
Specifies a description for the address block.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndIPAddress
Specifies the end address of the IP address block.
If you specify this parameter, you must specify the *StartIPAddress* parameter.

```yaml
Type: IPAddress[]
Parameter Sets: ByKeySet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LastAssignedDate
Specifies the last date, as a **DateTime** object, on which the block was assigned to devices on a network.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies the IP network prefix, in Classless Interdomain Routing (CIDR) notation, for the network block that you want modified.

```yaml
Type: String[]
Parameter Sets: ByKeySet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewEndIpAddress
Specifies a new value for the end IP address of the address block.
Specify a value that is compatible with the values that you specify for the *NewNetworkId* and *NewStartIPAddress* parameters.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewNetworkId
Specifies an IP network prefix, in Classless Interdomain Routing (CIDR) notation.
This is the new value for the network from which the IP address block is added to IPAM.

Specify a value that is compatible with the values that you specify for the *NewStartIPAddress* and *NewEndIPAddress* parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewStartIpAddress
Specifies a new value for the start IP address of the address block.
Specify a value that is compatible with the values that you specify for the *NewNetworkId* and *NewEndIPAddress* parameters.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the owner of the IP address block.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Rir
Specifies the regional internet registry (RIR) for public addresses.
RIR is a built-in custom field in the IPAM server that contains the following built-in values:

- AFRINIC
- APNIC
- ARIN
- LACNIC
- RIPE

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RirReceivedDate
Specifies the date, as a **DateTime** object, when you obtained the public address block from the RIR.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies the start address for the IP address block.
If you specify this parameter, you must specify the *EndIPAddress* parameter.

```yaml
Type: IPAddress[]
Parameter Sets: ByKeySet
Aliases:

Required: True
Position: 2
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

## OUTPUTS

### IpamBlock
This cmdlet returns an object that represents an address block object in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamBlock](./Get-IpamBlock.md)

[Add-IpamBlock](./Add-IpamBlock.md)

[Remove-IpamBlock](./Remove-IpamBlock.md)

