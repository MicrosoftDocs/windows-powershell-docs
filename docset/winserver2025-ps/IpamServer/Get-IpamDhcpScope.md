---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDhcpScope.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdhcpscope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDhcpScope
---

# Get-IpamDhcpScope

## SYNOPSIS
Gets information about DHCP scopes from IPAM database.

## SYNTAX

```
Get-IpamDhcpScope [-AddressFamily] <AddressFamily[]> [[-ScopeId] <IPAddress[]>] [[-ServerFqdn] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDhcpScope** cmdlet retrieves information about the Dynamic Host Configuration Protocol (DHCP) scopes in the IP Address Management (IPAM) database.
Scopes represent the IP addresses that a DHCP server can lease to clients.
In most cases, scopes correspond to IP subnets.

As a general rule, DHCP servers can only lease addresses from a single scope.
However, superscopes provide a mechanism that allows a DHCP server to lease addresses from multiple scopes.
See the **Get-IpamDhcpSuperscope** cmdlet for more information.

## EXAMPLES

### Example 1: Get information about all IPv4 scopes
```
PS C:\> Get-IpamDhcpScope -AddressFamily "IPv4"
```

This command returns all the IPv4 DHCP scopes found in the IPAM database.

### Example 2: Get information about the IPv4 scopes on a specific server
```
PS C:\> Get-IpamDhcpScope -AddressFamily "IPv4" -ServerFqdn "dhcp.contoso.com"
```

This command also returns IPv4 DHCP scopes.
In this case, however, the only scopes returned are the ones found on the server dhcp.contoso.com.

## PARAMETERS

### -AddressFamily
Specifies the address family for the DHCP scopes that this cmdlet gets.

The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: (All)
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

### -ScopeId
Specifies the ID of the DHCP scope that this cmdlet gets.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerFqdn
Specifies the fully qualified domain name (FQDN) of the DHCP server hosting the DHCP scopes that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDhcpScope

This cmdlet returns an object that represents an **IpamDhcpScope** object.

## NOTES

## RELATED LINKS

[Get-IpamDhcpServer](./Get-IpamDhcpServer.md)

[Get-IpamDhcpSuperscope](./Get-IpamDhcpSuperscope.md)
