---
external help file: MSFT_NetNat.cdxml-help.xml
Module Name: NetNat
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netnat/new-netnat?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetNat
---

# New-NetNat

## SYNOPSIS
Creates a NAT object.

## SYNTAX

```
New-NetNat [-Name] <String> -ExternalIPInterfaceAddressPrefix <String> [-InternalRoutingDomainId <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetNat** cmdlet creates a Network Address Translation (NAT) object that translates an internal network address to an external network address.
NAT modifies IP address and port information in packet headers.

You can modify some  settings by using the Set-NetNat cmdlet.

## EXAMPLES

### Example 1: Create a NAT object for a routing domain
```
PS C:\> New-NetNat -Name "TSQATenant" -ExternalIPInterfaceAddress "a.b.c.0/24" -InternalRoutingDomainId "{bb47986c-f134-4a29-ad87-24010bf2c92f}"
```

This command creates a NAT object named TSQATenant.
The command specifies an IP interface address and internal routing domain for TSQATenant.
This example uses the placeholder a.b.c.0/24 to represent a public Internet address prefix.

### Example 2: Create a NAT object for all the computers on a subnet
```
PS C:\> New-NetNat -Name "AllTenants" -ExternalIPInterfaceAddress "a.b.c.0/24"
```

This command creates a NAT object named AllTenants for all the computers in the specified subnet.
This example uses the placeholder a.b.c.0/24 to represent a public Internet address prefix.

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

### -ExternalIPInterfaceAddressPrefix
Specifies the address prefix of the external interface, which connects the NAT to the external network.

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

### -InternalRoutingDomainId
Specifies the GUID of the routing domain of the internal interface.

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

### -Name
Specifies a name for the NAT object.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNat

## NOTES

## RELATED LINKS

[Get-NetNat](./Get-NetNat.md)

[Remove-NetNat](./Remove-NetNat.md)

[Set-NetNat](./Set-NetNat.md)

