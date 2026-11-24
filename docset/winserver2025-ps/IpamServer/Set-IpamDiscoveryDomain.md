---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDiscoveryDomain.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamdiscoverydomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamDiscoveryDomain
---

# Set-IpamDiscoveryDomain

## SYNOPSIS
Modifies the IPAM discovery configuration.

## SYNTAX

```
Set-IpamDiscoveryDomain [-Name] <String> [-DiscoverDc <Boolean>] [-DiscoverDns <Boolean>]
 [-DiscoverDhcp <Boolean>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamDiscoveryDomain** cmdlet modifies the discovery configuration for an Active Directory domain.
Use this cmdlet to configure IPAM to discover particular types of servers, such as domain controllers, Dynamic Host Configuration Protocol (DHCP) servers, or Domain Name System (DNS) servers.

## EXAMPLES

### Example 1: Modify an existing discovery domain
```
PS C:\> Set-IpamDiscoveryDomain -Name "contoso.com" -DiscoverDc $False -PassThru
DomainName                    DiscoverDc                    DiscoverDns                   DiscoverDhcp

----------                    ----------                    -----------                   ------------

contoso.com                   False                         True                          True
```

This command modifies an existing discovery domain to prevent server discovery of domain controllers in the domain.
The command outputs an object for use with another cmdlet.
The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Modify an existing discovery domain to discover domain controllers
```
PS C:\> Set-IpamDiscoveryDomain -Name "contoso.com" -DiscoverDc $True -PassThru
DomainName                    DiscoverDc                    DiscoverDns                   DiscoverDhcp

----------                    ----------                    -----------                   ------------

contoso.com                   True                          True                          True
```

This command modifies an existing discovery domain in IPAM to discover an additional server type in the domain.
The command includes the *PassThru* parameter, so it displays results to the console.

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

### -DiscoverDc
Indicates whether IPAM discovers domain controller servers in a domain.
By default, the value is True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiscoverDhcp
Indicates whether IPAM discovers DHCP servers in a domain.
By default, the value is True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiscoverDns
Indicates whether IPAM discovers DNS servers in a domain.
By default, the value is True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the fully qualified domain name (FQDN) of an Active Directory domain in which to modify the discovery settings.

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

### IpamDiscoveryDomain
This cmdlet returns an object that represents an active directory domain in which IPAM will discover infrastructure servers.

## NOTES

## RELATED LINKS

[Add-IpamDiscoveryDomain](./Add-IpamDiscoveryDomain.md)

[Get-IpamDiscoveryDomain](./Get-IpamDiscoveryDomain.md)

[Remove-IpamDiscoveryDomain](./Remove-IpamDiscoveryDomain.md)

