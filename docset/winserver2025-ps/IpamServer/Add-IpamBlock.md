---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamBlock.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamblock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamBlock
---

# Add-IpamBlock

## SYNOPSIS
Adds an IP address block to IPAM.

## SYNTAX

```
Add-IpamBlock [-NetworkId] <String> [[-StartIPAddress] <IPAddress>] [[-EndIPAddress] <IPAddress>]
 [-Rir <String>] [-RirReceivedDate <DateTime>] [-Description <String>] [-LastAssignedDate <DateTime>]
 [-Owner <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamBlock** cmdlet adds an IP address block to IP Address Management (IPAM).
Specify the network from which the IP address block is added by using the *NetworkID* parameter.
If the address category of the block you add is public, you must specify the *Rir* parameter.
The *Rir* parameter is optional for private address blocks.

## EXAMPLES

### Example 1: Add an IPv4 private address block
```
PS C:\> Add-IpamBlock -NetworkId "10.0.0.0/8" -Description "IP block for Contoso" -PassThru


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

Description        : IP block for Contoso

RirReceivedDate    :

PercentageAssigned : 1.454353
```

This command adds an IPv4 private address block to the IPAM server.
The command uses the first address and last address of the network that has the ID 10.0.0.0/8 for the start and end addresses of the block.
The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Add a public address block
```
PS C:\> Add-IpamBlock -NetworkId "206.73.118.0/24" -Rir "APNIC" -PassThru


Utilization        : Under

NetworkId          : 206.73.118.0/24

StartAddress       : 206.73.118.0

EndAddress         : 206.73.118.255

Rir                : APNIC

LastAssignedDate   :

TotalAddresses     : 256

AssignedAddresses  : 0

UtilizedAddresses  : 0

PercentageUtilized : 0

AddressCategory    : Public

Owner              :

Description        :

RirReceivedDate    :

PercentageAssigned : 0
```

This command adds a public address block to the IPAM server.
You must specify the **Rir** parameter if the address category of the block you add is Public.

### Example 3: Add an IPv6 address block
```
PS C:\> Add-IpamBlock -NetworkId 2001:DB8:ff00::/120 -PassThru


Utilization        : Under

NetworkId          : 2001:db8:ff00::/120

StartAddress       : 2001:db8:ff00::

EndAddress         : 2001:db8:ff00::ff

Rir                :

LastAssignedDate   :

TotalAddresses     : 256

AssignedAddresses  : 0

UtilizedAddresses  : 0

PercentageUtilized : 0

AddressCategory    : Global

Owner              :

Description        :

RirReceivedDate    :

PercentageAssigned : 0
```

This command adds an IPv6 address block to the IPAM server.

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
Specifies the end address for the IP address block.
If you do not specify this parameter, the cmdlet uses the last IP address of the network that you specify for the *NetworkId* parameter.
If you specify this parameter, you must specify the *StartIPAddress* parameter.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies an IP network prefix, in Classless InterDomain Routing (CIDR) notation.
This is the network from which the IP address block is added to the IPAM server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
If you do not specify this parameter, the cmdlet uses the first address of the network that you specify for the *NetworkId* parameter.
If you specify this parameter, you must specify the *EndIPAddress* parameter.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
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

## NOTES

## RELATED LINKS

[Get-IpamBlock](./Get-IpamBlock.md)

[Set-IpamBlock](./Set-IpamBlock.md)

[Remove-IpamBlock](./Remove-IpamBlock.md)

