---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamAddress
---

# Remove-IpamAddress

## SYNOPSIS
Removes a set of addresses from IPAM.

## SYNTAX

### ByAddress
```
Remove-IpamAddress [-IpAddress] <IPAddress[]> [[-ManagedByService] <String[]>] [[-ServiceInstance] <String[]>]
 [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-IpamAddress -InputObject <CimInstance[]> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamAddress** cmdlet removes a set of addresses from IP Address Management (IPAM).
The cmdlet removes the specified IP address records permanently from the IPAM database.
Specify the IP addresses to remove or use the *InputObject* parameter to specify an **IpamAddress** object to remove.

The cmdlet does not remove any reservations on the Dynamic Host Configuration Protocol (DHCP) server or Domain Name System (DNS) records.
You can use Windows PowerShell for DHCP Server to remove a reservation from the DHCP server.
You can use Windows PowerShell for DNS to remove the DNS records associated with the IP addresses that you remove.

## EXAMPLES

### Example 1: Remove all IP addresses in range
```
PS C:\> $Range = Get-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254
PS C:\> Get-IpamAddress -MappingToRange $Range | Remove-IpamAddress
Confirm

Deleting the given IP Address from IPAM database. You will not be able to undo this action. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This example removes all IP addresses in a range.

The first command uses the **Get-IpamRange** cmdlet to get an **IpamRange** object that contains the addresses that belong to a range of IP addresses.
The command stores the object in the $Range variable.

The second command uses the **Get-IpamAddress** cmdlet to get an **IpamAddress** object that contains the IP addresses that map to the range stored in the $Range variable.
The command passes the **IpamAddress** object to the **Remove-IpamAddress** cmdlet by using the pipeline operator.
The command removes the addresses in the range stored in the $Range variable.

### Example 2: Remove all expired physical addresses managed by IPAM
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -ManagedByService IPAM | Where-Object {$_.ExpiryStatus -eq "Expired"} | Remove-IpamAddress
```

This command gets an **IpamAddress** object that contains the physical addresses managed by IPAM that have expired.
The command passes the **IpamAddress** object to the **Remove-IpamAddress** cmdlet by using the pipeline operator.
The **Remove-IpamAddress** cmdlet removes the **IpamAddress** object.

### Example 3: Remove a customer IP address
```
PS C:\> Remove-IpamAddress -IpAddress 172.16.10.16 -AddressSpace "Default"
```

This command removes the customer IP address 172.16.10.16 from the default address space.

### Example 4: Remove a provider IP address
```
PS C:\> Remove-IpamAddress -IpAddress 172.16.10.19 -AddressSpace "Default" -NetworkType Provider
```

This command removes the provider IP address 172.16.10.19 from the default address space.

## PARAMETERS

### -AddressSpace
Specifies an array of address spaces.
The cmdlet removes the addresses that belong to the address spaces that you specify.
If you specify this parameter, you must specify the *IpAddress* parameter.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases:

Required: False
Position: Named
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

### -Force
Forces the command to run without asking for user confirmation.

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

### -IpAddress
Specifies an array of IP addresses.

```yaml
Type: IPAddress[]
Parameter Sets: ByAddress
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedByService
Specifies an array of services that manage the IP addresses that you specify in the *IpAddress* parameter.
If you specify this parameter, you must specify the *IpAddress* parameter.

The values that you specify for this parameter must exist in the set of values that you defined for the **ManagedByService** custom field in IPAM.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases: MB

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies the network type of the address.
The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

The default value is NonVirtualized.

If you specify Default for the *AddressSpace* parameter, the valid values for this parameter are Provider and NonVirtualized.
If you specify a provider type of address space for the *AddressSpace* parameter, you must specify Provider for this parameter.
If you specify a customer type of address space for the *AddressSpace* parameter, you must specify Customer for this parameter.

```yaml
Type: VirtualizationType[]
Parameter Sets: ByAddress
Aliases:
Accepted values: NonVirtualized, Provider, Customer

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

### -ServiceInstance
Specifies an array of instances of the services that manage the IP addresses.
Specify the instances of the services that you specified for the *ManagedByService* parameter.
If you specify this parameter, you must specify the *IpAddress* parameter.
The value that you specify for this parameter must exist in the set of values that you defined for the **ServiceInstance** custom field in IPAM.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases: SI

Required: False
Position: 3
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

### IpamAddress
This cmdlet returns an object that represents an IP address on the IPAM server.

## NOTES

## RELATED LINKS

[Get-IpamAddress](./Get-IpamAddress.md)

[Add-IpamAddress](./Add-IpamAddress.md)

[Set-IpamAddress](./Set-IpamAddress.md)

[Import-IpamAddress](./Import-IpamAddress.md)

[Export-IpamAddress](./Export-IpamAddress.md)

[Get-IpamAddressSpace](./Get-IpamAddressSpace.md)

