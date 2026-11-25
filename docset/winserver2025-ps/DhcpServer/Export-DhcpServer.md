---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DhcpServerMigration-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/export-dhcpserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-DhcpServer
---

# Export-DhcpServer

## SYNOPSIS
Exports the DHCP server service configuration and lease data.

## SYNTAX

```
Export-DhcpServer [-File] <String> [-ScopeId <IPAddress[]>] [-Prefix <IPAddress[]>] [-Leases] [-Force]
 [-ComputerName <String>] [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-DhcpServer** cmdlet exports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, to the specified file.

If you specify the *ScopeId* or *Prefix* parameter,only the specified scopes or prefixes and all server level settings are exported.

If you specify neither *ScopeId* or *Prefix*, the DHCP server service configuration including all scopes, v4 and v6 and optionally the lease data, is exported.

If you specify the *Leases* parameter, the lease data is also exported in addition to configuration data.

## EXAMPLES

### Example 1: Export all DHCP configurations
```
PS C:\> Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml"
```

This example exports all of the DHCP server, DHCPv4 and DHCPv6, configurations including scopes present on the DHCP server service to the specified export file in XML file format.

### Example 2: Export the specified scopes
```
PS C:\> Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -ScopeId 10.10.10.0,10.20.20.0
```

This example exports the scopes 10.10.10.0 and 10.20.20.0 present on the DHCP server service to the specified export file in XML file format.
The DHCPv4 server level configuration is also exported to the specified file.

### Example 3: Export specified scopes and their leases
```
PS C:\> Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -ScopeId 10.10.10.0,10.20.20.0 -Leases
```

This example exports the scopes 10.10.10.0 and 10.20.20.0 present on the DHCP server service to the specified export file in XML file format.
This includes the leases present in the specified scopes.
The DHCPv4 server level configuration will also be exported to the specified file.

### Example 4: Export the specified scopes and DHCPv6 server level configuration
```
PS C:\> Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030::
```

This example exports the specified scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: present on the DHCP server service to the specified export file in XML file format.
The DHCPv6 server level configuration is also exported to the specified file.

### Example 5: Export the specified scopes, their leases, and DHCPv6 server level configuration
```
PS C:\> Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases
```

This example exports the specified scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: present on the DHCP server service to the specified export file in XML file format.
This includes the leases present in the specified scopes.
The DHCP server level configuration is also exported to the specified file.

### Example 6: Export scopes specified in a file
```
PS C:\> Import-Csv -Path "ScopeList.txt" | Export-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -Leases
```

This example exports a list of scopes specified in file named ScopeList.txt to the specified export file in XML file format.
The **Import-Csv** cmdlet returns the objects that contain the scope IDs output and pipes the objects into this cmdlet, which exports the specified scopes.

The file named ScopeList.txt should contain the following format:

ScopeId

10.10.10.0

20.20.20.0

30.30.30.0

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Specifies the name of the file to which the data will be exported.
If the complete file path is not specified, the file is created in the current working directory.
If there is an existing file by the same name, an error is returned.

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

### -Force
Specifies that, if there is a file that already exists with the specified name, the file is overwritten.

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

### -Leases
Specifies that IP address leases is also exported.

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

### -Prefix
Specifies one or more subnet prefixes of the IPv6 scopes which are exported.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope identifiers, in IPv4 address format, which are exported.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Backup-DhcpServer](./Backup-DhcpServer.md)

[Import-DhcpServer](./Import-DhcpServer.md)

[Restore-DhcpServer](./Restore-DhcpServer.md)

