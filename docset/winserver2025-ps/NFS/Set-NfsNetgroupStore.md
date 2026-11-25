---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsNetgroupStore.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsnetgroupstore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NfsNetgroupStore
---

# Set-NfsNetgroupStore

## SYNOPSIS
Modifies netgroup configuration settings.

## SYNTAX

```
Set-NfsNetgroupStore [-InputObject <CimInstance[]>] [-NetgroupStoreType <String>] [-NisServer <String>]
 [-NisDomain <String>] [-LdapServer <String>] [-LDAPNamingContext <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NfsNetgroupStore** cmdlet modifies configuration settings that a Network File System (NFS) Server uses to obtain netgroups from a specified netgroup store.

An NFS server can get netgroups from Network Information Service (NIS) or RFC-2307-compliant Lightweight Directory Access Protocol (LDAP)-based stores, such as Active Directory Domain Services (AD DS) or Active Directory Lightweight Directory Services (AD LDS).

## EXAMPLES

### Example 1: Configure an NFS server to get netgroups from an LDAP store
```
PS C:\> Set-NfsNetgroupStore -NetgroupSourceType "LDAP" -LdapServer "Contoso.com"
```

This command configures an NFS server to get netgroups from an LDAP store that is named Contoso.com.

### Example 2: Configure an NFS server to get netgroups from an NIS store
```
PS C:\> Set-NfsNetgroupStore -NetgroupSourceType "NIS" -NisServer "NIS.Contoso.com"
```

This command configures an NFS server to get netgroups from an NIS store that is named NIS.Contoso.com.

## PARAMETERS

### -AsJob
Indicates that this cmdlet runs the command as a background job on a remote computer.
Use this parameter to run commands that take an extensive time to finish.

When you use the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.
You can continue to work in the session while the job finishes.
To manage the job, use the **Job** cmdlets.
To get the job results, use the Receive-Job cmdlet.

The *AsJob* parameter resembles using the Invoke-Command cmdlet to run a Start-Job command remotely.
However, with *AsJob*, the job is created on the local computer, even though the job runs on a remote computer, and the results of the remote job are automatically returned to the local computer.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251) and [about_Remote_Jobs](https://go.microsoft.com/fwlink/?LinkID=135184).

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

### -InputObject
Gets an array of Common Information Model (CIM) instances from a CIM server.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LDAPNamingContext
Specifies an LDAP naming context that the NFS server uses when it performs LDAP queries to obtain netgroup information.

The NFS server uses this parameter only if the *NetgroupSourceType* parameter is set to LDAP.
If *NetgroupSourceType* is set to NIS or None, the NFS server ignores the value set for this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ldapdn, nc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LdapServer
Specifies an LDAP server name or an Active Directory domain name that stores netgroup information.

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

### -NetgroupStoreType
Specifies the type of netgroup store.
The acceptable values for this parameter are:

- LDAP
- NIS
- None

```yaml
Type: String
Parameter Sets: (All)
Aliases: netgrouptype
Accepted values: none, ldap, nis

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NisDomain
Specifies the NIS domain of the NIS server where information about netgroups is stored.

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

### -NisServer
Specifies the host name of the NIS server where information about netgroups is stored.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsNetgroupStore

Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsNetgroupStore

## NOTES

## RELATED LINKS

[RFC-2307](http://www.rfc-editor.org/rfc/rfc2307.txt)

[Get-NfsNetgroupStore](./Get-NfsNetgroupStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)
