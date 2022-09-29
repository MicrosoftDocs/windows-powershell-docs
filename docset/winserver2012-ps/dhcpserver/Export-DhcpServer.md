---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/export-dhcpserver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-DhcpServer

## SYNOPSIS
Exports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, to the specified file.

## SYNTAX

```
Export-DhcpServer [-File] <String> [-CimSession <CimSession>] [-ComputerName <String>] [-Force] [-Leases]
 [-Prefix <IPAddress[]>] [-ScopeId <IPAddress[]>]
```

## DESCRIPTION
The **Export-DhcpServer** cmdlet exports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, to the specified file.

If the **ScopeId** or **Prefix** parameter is specified, then only the specified scopes or prefixes and all server level settings are exported.

If neither **ScopeId** nor **Prefix** is specified, then the entire DHCP server service configuration including all scopes, v4 and v6 and optionally the lease data, is exported.

If **Leases** parameter is specified, then the lease data is also exported in addition to configuration data.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml
```

This example exports all of the DHCP server, DHCPv4 and DHCPv6, configurations including scopes present on the DHCP server service to the specified export file in XML file format.

### EXAMPLE 2
```
PS C:\> Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml -ScopeId 10.10.10.0,20.20.20.0
```

This example exports the specified scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service to the specified export file in XML file format.
The DHCPv4 server level configuration will also be exported to the specified file.

### EXAMPLE 3
```
PS C:\> Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml -ScopeId 10.10.10.0,20.20.20.0 -Leases
```

This example exports the specified scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service to the specified export file in XML file format, including the leases present in the specified scopes.
The DHCPv4 server level configuration will also be exported to the specified file.

### EXAMPLE 4
```
PS C:\> Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030::
```

This example exports the specified scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: present on the DHCP server service to the specified export file in XML file format.
The DHCPv6 server level configuration will also be exported to the specified file.

### EXAMPLE 5
```
PS C:\> Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases
```

This example exports the specified scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: present on the DHCP server service to the specified export file in XML file format, including the leases present in the specified scopes.
The DHCP server level configuration will also be exported to the specified file.

### EXAMPLE 6
```
PS C:\> Import-Csv -Path ScopeList.txt | Export-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exportdir\dhcpexport.xml -Leases
```

This example exports a list of scopes specified in file named ScopeList.txt to the specified export file in XML file format.
The Import-Csvhttp://go.microsoft.com/fwlink/p/?LinkId=113341 cmdlet returns the objects containing the scope IDs output and pipes the objects into this cmdlet, which exports the specified scopes. 

The file named ScopeList.txt should contain the following format: 

ScopeId 

10.10.10.0 

20.20.20.0 

30.30.30.0

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### -File
Specifies the name of the file to which the data will be exported.
If the complete file path is not specified, then the file will be created in the current working directory.
If there is an existing file by the same name, then an error will be returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that, if there is a file that already exists with the specified name, the file will be overwritten.

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
Specifies that IP address leases will also be exported.

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
Specifies one or more subnet prefixes of the IPv6 scopes which are to be exported.

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
Specifies the scope identifiers, in IPv4 address format, which are to be exported.

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

[Import-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113341)

[Backup-DhcpServer](./Backup-DhcpServer.md)

[Import-DhcpServer](./Import-DhcpServer.md)

[Restore-DhcpServer](./Restore-DhcpServer.md)

