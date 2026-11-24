---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDhcpSuperscope.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamdhcpsuperscope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDhcpSuperscope
---

# Get-IpamDhcpSuperscope

## SYNOPSIS
Gets information about DHCP superscopes from IPAM database.

## SYNTAX

```
Get-IpamDhcpSuperscope [[-SuperscopeName] <String[]>] [[-ServerFqdn] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDhcpSuperscope** cmdlet gets information about Dynamic Host Configuration Protocol (DHCP) superscopes in the IP Address Management (IPAM) server database.
Scopes represent the IP addresses that a DHCP server can lease to clients.
In most cases, scopes correspond to IP subnets.
As a general rule, DHCP servers can only lease addresses from a single scope.
However, superscopes provide a mechanism that allows a DHCP server to lease addresses from multiple scopes.
Superscopes are only available for IPv4 addresses.

## EXAMPLES

### Example 1: Get information about all the superscopes
```
PS C:\> Get-IpamDhcpSuperscope
```

This command returns information about all the DHCP superscopes in the IPAM database.

### Example 2: Get information about all superscopes on a server
```
PS C:\> Get-IpamDhcpSuperscope -ServerFqdn "dhcp.contoso.com"
```

This command returns all the DHCP superscopes found on the DHCP server named dhcp.contoso.com.

### Example 3: Get information for a single superscope
```
PS C:\> Get-IpamDhcpSuperscope -ServerFqdn "dhcp.contoso.com"-SuperscopeName "SuperScope01"
```

This command returns information for a single DHCP superscope named SuperScope01 that is located on the server named dhcp.contoso.com.

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

### -ServerFqdn
Specifies the fully qualified domain name of the DHCP server hosting the DHCP superscopes to be retrieved.
For example:

`-ServerFqdn "dhcp.contoso.com"`

``

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SuperscopeName
Specifies the name of the DNS superscope to be retrieved.
For example: .

`-SuperscopeName "Pacific Northwest"`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### Get-IpamDhcpSuperscope

This cmdlet returns an object that represents an instance of **Get-IpamDhcpSuperscope**.

## NOTES

## RELATED LINKS

[Get-IpamDhcpScope](./Get-IpamDhcpScope.md)

[Get-IpamDhcpServer](./Get-IpamDhcpServer.md)
