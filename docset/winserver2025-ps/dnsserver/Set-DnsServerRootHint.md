---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerRootHint_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverroothint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerRootHint
---

# Set-DnsServerRootHint

## SYNOPSIS
Replaces a list of root hints.

## SYNTAX

```
Set-DnsServerRootHint [-InputObject] <CimInstance> [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerRootHint** cmdlet replaces the list of root hints on a Domain Name System (DNS) server.
This cmdlet overwrites the list of root hints with the list of root hints that you specify by using the *InputObject* parameter.

## EXAMPLES

### Example 1: Change the IP address of a root hint
```
The first command adds a root hint for the DNS name server that is named H.Root-Servers.net and the IP address 172.24.60.128.
PS C:\> Add-DnsServerRootHint -NameServer "H.Root-Servers.contoso.net" -IPAddress 172.24.60.128

The second command assigns the value that is returned by the **Get-DnsServerRootHint** cmdlet to the variable $a. **Get-DnsServerRootHint** gets a list of all root hints on the local DNS server. The command then passes that collection to the **Where-Object** cmdlet by using the pipeline operator. **Where-Object** filters the resource record to get the root hint for the DNS name server that is named H.Root-Servers.net.
PS C:\> $a = (Get-DnsServerRootHint | Where-Object {$_.NameServer.RecordData.NameServer -eq "H.Root-Servers.contoso.net."} )

The third command sets the value of the IP address of the root hint to 172.24.60.132 for the DNS name server H.Root-Servers.net.
PS C:\> $a.IPAddress[0].RecordData.Ipv4address = "172.24.60.132"

The fourth command replaces the list of root hints on the local DNS server with the root hint for the DNS name server H.Root-Servers.net.
PS C:\> Set-DnsServerRootHint $a
```

This example adds a root hint to the list of root hints on a DNS server and changes the IP address of the root hint.

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

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerRootHint

## NOTES

## RELATED LINKS

[Get-DnsServerRootHint](./Get-DnsServerRootHint.md)

[Import-DnsServerRootHint](./Import-DnsServerRootHint.md)

[Add-DnsServerRootHint](./Add-DnsServerRootHint.md)

[Remove-DnsServerRootHint](./Remove-DnsServerRootHint.md)

