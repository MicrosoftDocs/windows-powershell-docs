---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DhcpServerMigration-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/import-dhcpserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-DhcpServer
---

# Import-DhcpServer

## SYNOPSIS
Imports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, from a file.

## SYNTAX

```
Import-DhcpServer [-File] <String> [-BackupPath] <String> [-ScopeId <IPAddress[]>] [-Prefix <IPAddress[]>]
 [-ScopeOverwrite] [-Leases] [-ServerConfigOnly] [-Force] [-ComputerName <String>] [-CimSession <CimSession>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-DhcpServer** cmdlet imports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, from the specified file.

If you specify either the *ScopeId* or the *Prefix* parameter, or both, only the specified scopes or prefixes are imported.

If you specify neither the *ScopeId* nor the *Prefix* parameter, all of the configurations that is contained in the file, and optionally any lease data, is imported.

If you specify the *Leases* parameter, the lease data in the specified file is imported in addition to configuration data.

If you specify the *ScopeOverWrite* parameter and the scope being imported exists on the destination server, the scope on the target DHCP server service is overwritten.
If this parameter is not specified and the scope being imported exists on the destination DHCP server service, a warning message is displayed and the import proceeds to process the next scope being imported.

If you specify the *ServerConfigOnly* parameter, only the server level configuration is imported on the destination DHCP server service.
If the file specified contains any scope information, the same information is not imported on the destination DHCP server service.

## EXAMPLES

### Example 1: Import configuration data
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\"
```

This example imports the configuration data in the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The file can contain DHCPv4 and DHCPv6 configuration data.

### Example 2: Import configuration and lease data
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -Leases
```

This example imports the configuration and lease data in the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The file can contain DHCPv4 and DHCPv6 configuration data.

### Example 3: Import configuration data for specified scopes
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -ScopeId 10.10.10.0,10.20.20.0
```

This example imports the configuration data for scopes 10.10.10.0 and 10.20.20.0 from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 10.20.20.0, those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### Example 4: Import configuration and lease data for specified scopes
```powershell
PS C:\> Import-DhcpServer -ComputerName dhcpserver.contoso.com -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -ScopeId 10.10.10.0,10.20.20.0 -Leases
```

This example imports the configuration and lease data for scopes 10.10.10.0 and 10.20.20.0 from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 10.20.20.0, those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### Example 5: Import configuration and lease data for specified scopes with overwrite
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -ScopeId 10.10.10.0,10.20.20.0 -Leases -ScopeOverwrite
```

This example imports the configuration and lease data for scopes 10.10.10.0 and 10.20.20.0 from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 10.10.10.0 and 10.20.20.0, those scopes are ignored.
The DHCPv4 server level configuration data, if present in the export file, is also imported onto the server.
If the scopes 10.10.10.0 and 10.20.20.0 are already present on the DHCP server service that runs one the computer named dhcpserver.contoso.com, the scopes are deleted and recreated from the data in the export file.

### Example 6: Import server level configuration data
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -ServerConfigOnly
```

This example imports only the server level configuration data in the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
Any scope configuration data, if present in the file, is ignored.

### Example 7: Import configuration data for specified scopes for DHCPv6
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030::
```

This example imports the configuration data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### Example 8: Import configuration and lease data for specified scopes for DHCPv6
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases
```

This example imports the configuration and lease data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.

### Example 9: Import configuration and lease data for specified scopes for DHCPv6 with overwrite
```powershell
PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exports\dhcpexport.xml" -BackupPath "C:\dhcpbackup\" -Prefix 2001:4898:7020:1020::,2001:4898:7020:1030:: -Leases -ScopeOverwrite
```

This example imports the configuration and lease data for scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: from the specified file onto the DHCP server service that runs on the computer named dhcpserver.contoso.com.
If the export file contains scopes besides 2001:4898:7020:1020:: and 2001:4898:7020:1030::, those scopes are ignored.
The DHCPv6 server level configuration data, if present in the export file, is also imported onto the DHCP server service.
If the scopes 2001:4898:7020:1020:: and 2001:4898:7020:1030:: are already present on the DHCP server service that runs on the computer named dhcpserver.contoso.com, the scopes are deleted and recreated from the data in the export file.

### Example 10: Import scopes specified in a file
```powershell
PS C:\> $ScopeIdList = Import-Csv -Path ".\ScopeList.txt"

PS C:\> Import-DhcpServer -ComputerName "dhcpserver.contoso.com" -File "C:\exportdir\dhcpexport.xml" -Leases -ScopeId $ScopeIdList.ScopeId -BackupPath "C:\dhcpbackup\"
```

This example imports a list of scopes specified in file named _ScopeList.txt_ to the DHCP server service that runs on the computer named dhcpserver.contoso.com.

The **Import-Csv** cmdlet gets the list of scopes to import and returns it in the variable named _$ScopeIdList_. The second line imports the scopes using the variable named _$ScopeIdList_ as input for the _ScopeId_ parameter.

The file named _ScopeList.txt_ should contain the following format:

ScopeID \
10.10.10.0 \
10.20.20.0 \
10.30.30.0

## PARAMETERS

### -BackupPath
Specifies the path where DHCP server database is backed up before it makes any configuration changes as part of the import operation.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the name of the file from which the data is imported.
If a complete file path is not specified, the file is read from the current working directory.

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
Specifies that the lease data is also imported.

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
Specifies the subnet prefixes of IPv6 scopes which are imported.

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
Specifies the scope identifiers (IDs), in IPv4 address format, which must be imported.

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
Specifies that, if the scope being imported exists on the target server, the scope on the destination DHCP server service are overwritten.

If this parameter is not specified and the scope being imported exists on the destination DHCP server service, a warning message is displayed and import will proceed to process the next scope being imported.

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
Specifies that only server level configuration is imported on the destination DHCP server service.
If the file specified contains any scope information, the same is not imported on the destination DHCP server service.

Both DHCPv4 and DHCPv6 server level configurations is imported.

The server level configuration includes of (both v4 and v6):

- Class definitions.
- Option definitions.
- Option values.
- Server level Policies (DHCPv4).
- MAC address filters (DHCPv4).
- Other Server Properties (ConflictDetectionAttempts, DHCPv6 stateless store).

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Import-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113341)

[Backup-DhcpServer](./Backup-DhcpServer.md)

[Export-DhcpServer](./Export-DhcpServer.md)

[Restore-DhcpServer](./Restore-DhcpServer.md)
