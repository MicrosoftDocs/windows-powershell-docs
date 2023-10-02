---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsnetgroupstore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsNetgroupStore

## SYNOPSIS
Gets settings for a netgroup store.

## SYNTAX

```
Get-NfsNetgroupStore [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NfsNetgroupStore** cmdlet gets configuration settings for a netgroup store that a Network File System (NFS) server uses.
These settings specify whether an NFS server must get a list of configured netgroups from a server that is based on Network Information Service (NIS) or Lightweight Directory Access Protocol (LDAP).

## EXAMPLES

### Example 1: Get configuration settings for an NFS netgroup
```
PS C:\>Get-NfsNetgroupStore
LdapServer         : Contoso.com
LdapNamingContext  :
NetgroupStoreType  : LDAP
NisServer :
NisDomain
```

This command gets the configuration settings for an NFS netgroup.

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
Type: CimSession
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsNetgroupStore

## NOTES

## RELATED LINKS

[Set-NfsNetgroupStore](./Set-NfsNetgroupStore.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

