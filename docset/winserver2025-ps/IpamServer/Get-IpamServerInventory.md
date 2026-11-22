---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamServerInventory.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamserverinventory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamServerInventory
---

# Get-IpamServerInventory

## SYNOPSIS
Gets the properties of managed servers in the IPAM server inventory.

## SYNTAX

### ByName
```
Get-IpamServerInventory -Name <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByAddressFamily
```
Get-IpamServerInventory [-AddressFamily <AddressFamily[]>] [-ServerType <ServerRole[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamServerInventory** cmdlet gets the list of managed servers in the IP Address Management (IPAM) server inventory.
Managed servers include the servers that perform domain controller (DC), Dynamic Host Configuration Protocol (DHCP), Domain Name Service (DNS), or Network Policy Server (NPS) roles.
You can filter the list of servers based on address family, the type of server role, or a list of fully qualified domain names (FQDNs).

## EXAMPLES

### Example 1: Get all IPv4 servers in the IPAM server inventory
```
PS C:\> Get-IpamServerInventory -AddressFamily IPv4 | Format-List Name, ServerType
Name       : dhcp1.contoso.com

ServerType : DHCP
Name       : DC1.contoso.com

ServerType : DC
```

This command gets all IPv4 servers in the IPAM server inventory.

### Example 2: Get all IPv4 DHCP servers in the IPAM server inventory
```
PS C:\> Get-IpamServerInventory -AddressFamily IPv4 -ServerType DHCP| Format-List Name, ServerType
Name       : dhcp1.contoso.com

ServerType : DHCP
```

This command gets all IPv4 DHCP servers in the IPAM server inventory.

## PARAMETERS

### -AddressFamily
Specifies an array of address families to which the infrastructure server belongs.

The acceptable values for this parameter are: IPv4 or IPv6.

```yaml
Type: AddressFamily[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Name
Specifies fully qualified domain names of the servers for which to get data.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerType
Specifies an array of server roles on which to filter the results.

```yaml
Type: ServerRole[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: DC, DNS, DHCP, NPS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamServerInventory
This cmdlet returns an object that represents a managed infrastructure server in IPAM system.

## NOTES

## RELATED LINKS

[Add-IpamServerInventory](./Add-IpamServerInventory.md)

[Remove-IpamServerInventory](./Remove-IpamServerInventory.md)

[Set-IpamServerInventory](./Set-IpamServerInventory.md)

