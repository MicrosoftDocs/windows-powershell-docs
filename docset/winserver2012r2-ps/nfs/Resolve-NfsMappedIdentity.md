---
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/nfs/resolve-nfsmappedidentity?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-NfsMappedIdentity
---

# Resolve-NfsMappedIdentity

## SYNOPSIS
Resolves the mapping of a Windows user account or group account to a UNIX identifier.

## SYNTAX

### ById (Default)
```
Resolve-NfsMappedIdentity [[-AccountType] <WindowsAccountType>] [-Id] <UInt32> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Resolve-NfsMappedIdentity [-AccountName] <String> [[-AccountType] <WindowsAccountType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Resolve-NfsMappedIdentity** cmdlet queries a Network File System (NFS) server to resolve the mapping of a Windows user account or group account to a UNIX identifier.

When **Resolve-NfsMappedIdentity** queries the local NFS server, the local NFS server searches its cache.
If the NFS server finds the mapping, the information is returned.
If the NFS server mapping does not find the mapping in the server cache, the NFS server queries the configured mapping store.
If the NFS server finds the mapping in the mapping store, the mapping is returned, locally cached, and periodically refreshed.

The main purpose of **Resolve-NfsMappedIdentity** is to perform mapping diagnostics.
Administrators can determine whether the NFS server can successfully get the correct mappings for users and groups by using its current configuration.

For more information about NFS, see Network File Systemhttp://technet.microsoft.com/en-us/library/jj592688.
For more information about NFS account mapping, see NFS Account Mapping Guidehttp://technet.microsoft.com/en-us/library/hh509020(v=ws.10) and Identity Management for UNIXhttp://technet.microsoft.com/en-us/library/cc772571.

## EXAMPLES

### Example 1: Resolve a Windows user account to a UNIX UID
```
PS C:\> Resolve-NfsMappedIdentity -AccountName "PSPinto" -AccountType "User"
Windows Account : PSPinto
Account Type    : User
Identifier      : 402
```

This command resolves the Windows user account PSPinto to UNIX user identifier 402.
The output reflects the identity mapping that the local NFS server returns.

## PARAMETERS

### -AccountName
Specifies the account name of the user or group to resolve.
You can use the **AccountType** parameter to specify whether the **AccountName** parameter value represents a user or a group.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountType
Specifies the type of Windows account name or identifier to resolve.
Valid values are User and Group.

```yaml
Type: WindowsAccountType
Parameter Sets: (All)
Aliases: type
Accepted values: User, Group

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Id
Specifies the UNIX identifier to resolve to a Windows account name.
You can use the **AccountType** parameter to specify whether the **Id** parameter value is a user or a group.

```yaml
Type: UInt32
Parameter Sets: ById
Aliases: uid, gid, Identifier

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/nfs/MSFT_NfsMappedIdentity

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

