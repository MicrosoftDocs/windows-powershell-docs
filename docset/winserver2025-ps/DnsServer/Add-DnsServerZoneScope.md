---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneScope_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverzonescope?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerZoneScope
---

# Add-DnsServerZoneScope

## SYNOPSIS
Adds a zone scope to an existing zone.

## SYNTAX

```
Add-DnsServerZoneScope [-ZoneName] <String> [-Name] <String> [-LoadExisting] [-PassThru]
 [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerZoneScope** cmdlet adds a zone scope to an existing zone on the Domain Name System (DNS) server.
A DNS server can load an existing scope from its data file.
The name of the scope should adhere to the same conventions as the zone name.
The scope name cannot be same as the zone name to which this cmdlet adds it.

When a scope is created, its data is persisted in a file named `%Systemroot%\system32\dns\<zone name>\<scope name>.dns`.

## EXAMPLES

### Example 1: Add a scope on a zone
```powershell
PS C:\> Add-DnsServerZoneScope -ZoneName "contoso.com" -Name "contoso_NorthAmerica" -Verbose -PassThru
VERBOSE: A scope contoso_NorthAmerica will be added for the zone contoso.com on server Server17.

ZoneScope                 FileName
---------                 --------
contoso_NorthAmerica      contoso_NorthAmerica.dns
```

This command adds a scope on an existing zone named contoso.com.

### Example 2: Add a scope on a zone with existing file
```powershell
PS C:\> Add-DnsServerZoneScope -ZoneName "contoso.com" -Name "contoso_NorthAmerica" -LoadExisting -PassThru
ZoneScope                 FileName
---------                 --------
contoso_NorthAmerica      contoso_NorthAmerica.dns
```

This command adds a scope on an existing zone named contoso.com.
The command specifies the *LoadExisting* parameter, so the server loads the scope from an existing file.

### Example 3: Add a cache scope
```powershell
PS C:\> Add-DnsServerZoneScope -ZoneName "..cache" -Name "ContosoScope" -PassThru
ZoneScope             FileName
---------             --------
ContosoScope          cache.dns
```

This command adds a cache scope named ContosoScope.

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

### -LoadExisting
Indicates that the server loads an existing file for the zone.
If you do not specify this parameter, the cmdlet creates default zone records automatically.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the zone scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ZoneScope

Required: True
Position: 2
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

### -ZoneName
Specifies the name of a zone.
This cmdlet adds a zone to the zone that this parameter specifies.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsZoneScope

## NOTES

## RELATED LINKS

[Get-DnsServerZoneScope](./Get-DnsServerZoneScope.md)

[Remove-DnsServerZoneScope](./Remove-DnsServerZoneScope.md)

