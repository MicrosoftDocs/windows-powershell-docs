---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsnetgroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsNetgroup

## SYNOPSIS
Gets a netgroup.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsNetgroup [[-NetGroupName] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsNetgroup [-LdapServer] <String> [[-LdapNamingContext] <String>] [[-NetGroupName] <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NfsNetgroup [-NisServer] <String> [[-NisDomain] <String>] [[-NetGroupName] <String>]
```

## DESCRIPTION
The **Get-NfsNetgroup** cmdlet gets a netgroup from a configured netgroup store that Network File System (NFS) server uses.

## EXAMPLES

### Example 1: Get a netgroup from an NFS domain
```
PS C:\> Get-NfsNetgroup -LdapServer "Contoso.com" -NetGroupName "ExchangeServers"


NetgroupName          : ExchangeServers
NetgroupNamingContext : CN=mappedidentity,DC=Contoso,DC=com
NetgroupMembers       : {}
```

This command gets the netgroup that is named ExchangeServers from an NFS domain netgroup store that is named Contoso.com.

## PARAMETERS

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of the netgroup store.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapServer
Gets the netgroups that are configured on a specified LDAP server.
The LDAP server name can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or other LDAP server.

If you do not specify the **LdapServer** parameter or a Network Information Service (NIS) server, the **Get-NfsNetgroup** cmdlet uses the netgroup store configuration that exists on the local NFS server.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetGroupName
Specifies the name of a netgroup.
If no name is specified, all netgroups in the specified or configured store are enumerated.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NisDomain
Specifies the domain of an NIS server that stores information about netgroups.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NisServer
Specifies the host name of an NIS server that stores information about netgroups.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.FileServices.Powershell.Nfs.NetGroup

## NOTES

## RELATED LINKS

[New-NfsNetgroup](./New-NfsNetgroup.md)

[Remove-NfsNetgroup](./Remove-NfsNetgroup.md)

[Set-NfsNetgroupStore](./Set-NfsNetgroupStore.md)

