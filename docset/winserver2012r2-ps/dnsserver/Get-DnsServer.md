---
external help file: PS_DnsServer_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version: 
schema: 2.0.0
title: Get-DnsServer
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AB325C11-CDA0-4071-A573-30FFBD46760D
---

# Get-DnsServer

## SYNOPSIS
Retrieves a DNS server configuration.

## SYNTAX

```
Get-DnsServer [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServer** cmdlet retrieves a Domain Name System (DNS) server configuration.
The DNS server must be running Windows Server® 2008 R2 operating system or above.

You can pipe the output of the **Get-DnsServer** cmdlet to the **Export-Clixml** cmdlet, which generates an XML file of the configuration.
You can use the XML file to back up or transfer DNS settings between computers.
For more information about **Export-Clixml**, see Using the Export-Clixml Cmdlethttp://technet.microsoft.com/en-us/library/ee176824.aspx.

## EXAMPLES

### Example 1: Get a DNS server configuration
```
PS C:\>Get-DnsServer -ComputerName "10.255.255.254"
```

This command gets a DNS server configuration.

### Example 2: Get local DNS server configuration and pipe it to Export-Clixml
```
PS C:\>Get-DnsServer | Export-Clixml -Path "c:\config\DnsServerConfig.xml"
```

This command gets the DNS server configuration on the local server and pipes it to the **Export-Clixml** cmdlet to be translated into an XML file.

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

### -ComputerName
Specifies a DNS server. 
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServer

## NOTES

## RELATED LINKS

[Set-DnsServer](./Set-DnsServer.md)

[Test-DnsServer](./Test-DnsServer.md)

