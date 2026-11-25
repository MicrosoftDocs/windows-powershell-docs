---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerGlobalQueryBlockList_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverglobalqueryblocklist?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerGlobalQueryBlockList
---

# Set-DnsServerGlobalQueryBlockList

## SYNOPSIS
Changes settings of a global query block list.

## SYNTAX

```
Set-DnsServerGlobalQueryBlockList [-Enable <Boolean>] [[-List] <String[]>] [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerGlobalQueryBlockList** cmdlet changes settings of a global query block list on a Domain Name System (DNS) server.
This cmdlet replaces all names in the list of names that the DNS server does not resolve with the names that you specify.

If you need the DNS server to resolve names such as ISATAP and WPAD, remove these names from the list.
Web Proxy Automatic Discovery Protocol (WPAD) and Intra-site Automatic Tunnel Addressing Protocol (ISATAP) are two commonly deployed protocols that are particularly vulnerable to hijacking.

## EXAMPLES

### Example 1: Replace the names in a global query block list
```
PS C:\> Set-DnsServerGlobalQueryBlockList -List "Isatap" -PassThru -Verbose
VERBOSE: Setting DNS server GlobalQueryBlockList on Fabrikam01 server.

VERBOSE: GlobalQueryBlockList successfully set on server Fabrikam01.
Enable : True

List   : {isatap}
```

This command replaces the existing host names in a global query block list that has the host name Isatap.

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

### -Enable
Specifies whether the server enables support for the global query block list that blocks name resolution for names in the list.
The DNS Server service creates and enables the global query block list by default the first time that the service starts.

When you disable the global query block list, the DNS Server service responds to queries for names in the block list.
When you enable the global query block list, the DNS Server service does not respond to queries for names in the block list.

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

### -List
Specifies an array of host names.

This cmdlet replaces the current global query block list with a list of the names that you specify.
To add a name to the list, you must also include all existing names in the list.
If you do not specify any names, the cmdlet clears the block list.

By default, the global query block list contains the following items: ISATAP and WPAD.
The DNS Server service removes these names when it starts the first time if it finds these names in an existing zone.
If you need the DNS server to resolve names such as ISATAP and WPAD, remove them from the list.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerGlobalQueryBlockList

## NOTES

## RELATED LINKS

[Get-DnsServerGlobalQueryBlockList](./Get-DnsServerGlobalQueryBlockList.md)

