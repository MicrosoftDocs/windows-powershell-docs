---
external help file: PS_DnsServer_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version: 
schema: 2.0.0
title: Set-DnsServer
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 0DB991F6-E926-4036-B04A-42E6E237CEE9
---

# Set-DnsServer

## SYNOPSIS
Overwrites a DNS server configuration.

## SYNTAX

```
Set-DnsServer [-InputObject] <CimInstance> [-ComputerName <String>] [-Force] [-CreateFileBackedPrimaryZones]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServer** cmdlet uses an input object to overwrite a specified Domain Name System (DNS) server configuration.
You can generate the input object by using an XML file that is exported by using any of the following cmdlets: **Get-DnsServer**, **Export-Clixml**, or **Import-Clixml**.

For more information about **Export-Clixml**, see  Export-Clixmlhttp://technet.microsoft.com/en-us/library/hh849916.aspx.
For more information about **Import-Clixml**, see  Import-Clixmlhttp://technet.microsoft.com/en-us/library/hh849906.aspx.

## EXAMPLES

### Example 1: Overwrite a DNS server configuration by using an input object
```
PS C:\>Get-DnsServer -ComputerName "DNSServer13.Contoso.com" | Export-Clixml -Path "c:\DnsServerConfig.xml"
PS C:\>$x = Import-Clixml "c:\DnsServerConfig.xml"
PS C:\>Set-DnsServer -InputObject $x -ComputerName "DNSServer22.Contoso.com"
```

This set of commands uses an input object to overwrite a DNS server configuration.

As shown in the code block, the first command gets DNS server configuration by using the **Get-DnsServer** cmdlet.
It then pipes the information to the **Export-Clixml** cmdlet, which exports the data into an XML file.

The second command gets and stores the XML file data in variable $x.

The third command uses the data that is stored in variable $x to overwrite an existing DNS server configuration.

### Example 2: Set DNS server configuration by using the Cimsession parameter
```
PS C:\>Get-DnsServer -CimSession 172.22.50.137 | Set-DnsServer
```

This command gets DNS server configuration from a server that has an IP address of 172.22.50.137 and applies it to the server on which the **Set-DnsServer cmdlet** is run.

### Example 3: Migrate DNS server configuration by using IP addresses
```
PS C:\>Get-DnsServer -CimSession 172.22.50.137 | Set-DnsServer -ComputerName 172.22.50.138
```

This command migrates DNS server configuration from a server that has an IP address of 172.22.50.137 to a server that has an IP address of 172.22.50.138.

### Example 4: Create a file-backed primary zone
```
PS C:\>Get-DnsServer -CimSession 172.22.50.137 | Set-DnsServer -CreateFileBackedPrimaryZones
```

This command creates file-backed primary zones on the specified local DNS server.
The file that contains resource records must exist in the **%windir%\system32\dns** directory.

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
The acceptable values for this parameter are: an IP v4 address; an IP v6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -CreateFileBackedPrimaryZones
Indicates that you must create new file-backed primary zones in the input object.
The files that contains the resource records must exist in the %windir%\system32\dns directory.

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

### -Force
Overrides the default confirmation setting before the cmdlet performs the action.

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
ps_cimcommon_asjob

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServer

## NOTES

## RELATED LINKS

[Get-DnsServer](./Get-DnsServer.md)

[Test-DnsServer](./Test-DnsServer.md)

