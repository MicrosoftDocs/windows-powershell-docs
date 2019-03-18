---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 00E203F4-D1F7-49CF-AC07-2630E820DC3E
---

# Import-DhcpServer

## SYNOPSIS
Imports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, from the specified file.

## SYNTAX

```
Import-DhcpServer [-File] <String> [-BackupPath] <String> [-CimSession <CimSession>] [-ComputerName <String>]
 [-Force] [-Leases] [-Prefix <IPAddress[]>] [-ScopeId <IPAddress[]>] [-ScopeOverwrite] [-ServerConfigOnly]
```

## DESCRIPTION
The **Import-DhcpServer** cmdlet imports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, from the specified file.
This cmdlet is only supported for the DHCP server services running on Windows Server® 2012.

If either the **ScopeId** or the **Prefix** parameter, or the **ScopeId** and **Prefix** parameters are specified, then only the specified scopes or prefixes will be imported.

If neither the **ScopeId** nor the **Prefix** parameter is specified, then all of the configurations contained in the file, and optionally any lease data, will be imported.

If the **Leases** parameter is specified, then the lease data in the specified file is imported in addition to configuration data.

If the **ScopeOverWrite** parameter is specified and the scope being imported exists on the destination server, then the scope on the target DHCP server service will be overwritten.
If this parameter is not specified and the scope being imported exists on the destination DHCP server service, then a warning message is displayed and the import will proceed to process the next scope being imported.

If the **ServerConfigOnly** parameter is specified, then only the server level configuration will be imported on the destination DHCP server service.
If the file specified contains any scope information, then the same information will not be imported on the destination DHCP server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\
```

This example imports the configuration data in the specified file onto the DHCP server service running one the computer named dhcpserver.contoso.com.
The file can contain DHCPv4 as well as DHCPv6 configuration data.

### EXAMPLE 2
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -Leases
```

This example imports the configuration and lease data in the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
The file can contain DHCPv4 as well as DHCPv6 configuration data.

### EXAMPLE 3
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -ScopeId 10.10.10.0,20.20.20.0
```

This example imports the configuration data for scopes 10.10.10.0 and 20.20.20.0 from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 20.20.20.0, then those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### EXAMPLE 4
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -ScopeId 10.10.10.0,20.20.20.0 -Leases
```

This example imports the configuration and lease data for scopes 10.10.10.0 and 20.20.20.0 from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 20.20.20.0, then those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### EXAMPLE 5
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -ScopeId 10.10.10.0,20.20.20.0 -Leases -ScopeOverwrite
```

This example imports the configuration and lease data for scopes 10.10.10.0 and 20.20.20.0 from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 20.20.20.0, then those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the server.
If the scopes 10.10.10.0 and 20.20.20.0 are already present on the DHCP server service running one the computer named dhcpserver.contoso.com, then the scopes are deleted and recreated from the data in the export file.

### EXAMPLE 6
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -ServerConfigOnly
```

This example imports only the server level configuration data in the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
Any scope configuration data, if present in the file, is ignored.

### EXAMPLE 7
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030::
```

This example imports the configuration data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, then those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### EXAMPLE 8
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases
```

This example imports the configuration and lease data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, then those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### EXAMPLE 9
```
PS C:\>Import-DhcpServer -ComputerName dhcpserver.contoso.com -File C:\exports\dhcpexport.xml -BackupPath C:\dhcpbackup\ -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases -ScopeOverwrite
```

This example imports the configuration and lease data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service running on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, then those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.
If the scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: are already present on the DHCP server service running on the computer named dhcpserver.contoso.com, then the scopes are deleted and recreated from the data in the export file.

### EXAMPLE 10
```
@{navigationLink=@{uri=http://go.microsoft.com/fwlink/p/?LinkId=113341; linkText=Import-Csv}; #text=System.Management.Automation.PSObject[]}
```

This example imports a list of scopes specified in file named ScopeList.txt to the DHCP server service running on the computer named dhcpserver.contoso.com. 

The file named ScopeList.txt should contain the following format: 

ScopeID 

10.10.10.0 

20.20.20.0 

30.30.30.0

## PARAMETERS

### -BackupPath
Specifies the path where DHCP server database is backed up before making any configuration changes as part of the import operation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Specifies the name of the file from which the data will be imported.
If a complete file path is not specified, then the file will be read from the current working directory.

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
Forces the command to run without asking for user confirmation.

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
Specifies that the lease data will also be imported.

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
Specifies the subnet prefixes of IPv6 scopes which are to be imported.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope identifiers (IDs), in IPv4 address format, which need to be imported.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeOverwrite
Specifies that, if the scope being imported exists on the target server, the scope on the destination DHCP server service will be overwritten. 

If this parameter is not specified and the scope being imported exists on the destination DHCP server service, then a warning message is displayed and import will proceed to process the next scope being imported.

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

### -ServerConfigOnly
Specifies that only server level configuration will be imported on the destination DHCP server service.
If the file specified contains any scope information, then the same will not be imported on the destination DHCP server service. 

Both DHCPv4 and DHCPv6 server level configurations will be imported. 

The server level configuration comprises of (both v4 and v6): 

 -- Class definitions. 

 -- Option definitions. 

 -- Option values. 

 -- Server level Policies (DHCPv4). 

 -- MAC address filters (DHCPv4). 

 -- Other Server Properties (ConflictDetectionAttempts, DHCPv6 stateless store).

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

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Import-Csv](http://go.microsoft.com/fwlink/p/?LinkId=113341)

[Backup-DhcpServer](./Backup-DhcpServer.md)

[Export-DhcpServer](./Export-DhcpServer.md)

[Restore-DhcpServer](./Restore-DhcpServer.md)

