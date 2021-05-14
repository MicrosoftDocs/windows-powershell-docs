---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/remove-nfsnetgroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NfsNetgroup

## SYNOPSIS
Removes a netgroup.

## SYNTAX

```
Remove-NfsNetgroup [-NetGroupName] <String> [[-LdapServer] <String>] [[-LdapNamingContext] <String>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Remove-NfsNetgroup** cmdlet removes a netgroup.

You can remove netgroups that are stored in Active Directory Domain Services (AD DS) or Active Directory Lightweight Directory Services (AD LDS) only.
To remove a netgroup that is stored in Network Information Service (NIS), use the corresponding NIS administration tool.
For more information about how to manage an NIS server, see Server for NIS Administrationhttp://technet.microsoft.com/en-us/library/cc753089.

If you do not specify a netgroup store, the **Remove-NfsNetgroup** cmdlet removes the netgroup from a netgroup store that is configured on the local computer.

## EXAMPLES

### Example 1: Remove an NFS netgroup
```
PS C:\> Remove-NfsNetgroup -NetGroupName "AppServers" -LdapInstanceName "Contoso.com"
```

This command removes an NFS netgroup that is named AppServers from a netgroup store in Contoso.com.

### Example 2: Remove an NFS netgroup from a configured store
```
PS C:\>Remove-NfsNetgroup -NetGroupName "AppServers"
```

This command removes an NFS netgroup that is named AppServers.
Because the netgroup store is not specified, the cmdlet removes the netgroup from the netgroup store that is configured on the local NFS server.

## PARAMETERS

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of a netgroup store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapServer
Specifies an LDAP server name of a netgroup store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetGroupName
Specifies the name of a netgroup to remove.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsNetgroup](./Get-NfsNetgroup.md)

[Set-NfsNetgroup](./Set-NfsNetgroup.md)

[New-NfsNetgroup](./New-NfsNetgroup.md)

