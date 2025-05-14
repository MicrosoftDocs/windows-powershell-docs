---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/new-nfsshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NfsShare
---

# New-NfsShare

## SYNOPSIS
Creates an NFS file share.

## SYNTAX

```
New-NfsShare [-Name] <String> [-Path] <String> [[-NetworkName] <String>] [[-Authentication] <String[]>]
 [[-AnonymousUid] <Int32>] [[-AnonymousGid] <Int32>] [[-LanguageEncoding] <String>]
 [[-EnableAnonymousAccess] <Boolean>] [[-EnableUnmappedAccess] <Boolean>] [[-AllowRootAccess] <Boolean>]
 [[-Permission] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NfsShare** cmdlet creates a Network File System (NFS) file share.
To create a share, you must specify a name and a path.
If you do not use the optional parameters for this cmdlet, **New-NfsShare** assigns default values for these share settings.

If you specify a path to a clustered disk for a new NFS share, this cmdlet creates a highly available clustered share.
You can use the *NetworkName* parameter to scope a share to a specified network name.
The network name must belong to the same resource group as the clustered disk.
If you do not specify the network name, **New-NfsShare** assigns an arbitrary network name that is available in the same resource group to scope the share.

## EXAMPLES

### Example 1: Create an NFS share for a folder
```
PS C:\> New-NfsShare -Name "NFSshare01" -Path "C:\shares\NFSshare01"
Name                   : nfsexport
Path                   : C:\shares\nfsexport
NetworkName            : GAPRASAD-TST22
Availability           : Standard (not clustered)
Online                 : True
AnonymousAccess        : Disabled
AnonymousGID           : -2
AnonymousUID           : -2
UnmappedUserAccess     : Enabled
Authentication         : {sys, Krb5, Krb5i}
```

This command creates an NFS share named NFSshare01 for sharing the folder C:\shares\NFSshare01.

### Example 2: Create an NFS share that has unmapped access
```
PS C:\> New-NfsShare -Name "NFSshare01" -Path "C:\shares\NFSshare01" -EnableUnmappedAccess $True -Authentication krb5,krb5i
```

This command creates an NFS share named NFSshare01 for sharing the folder C:\shares\ NFSshare01.
This command enables unmapped access on the new share and configures Krb5 and Krb5i authentication on the share.

## PARAMETERS

### -AllowRootAccess
Grants the UNIX root user access to a share.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AnonymousGid
Specifies the group identifier (GID) that Server for NFS uses for anonymous users who access an NFS share.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: AnonGid

Required: False
Position: 5
Default value: -2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AnonymousUid
Specifies the user identifier (UID) that Server for NFS uses for anonymous users who access an NFS share.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: AnonUid

Required: False
Position: 4
Default value: -2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Authentication
Specifies an array of authentication types that an NFS client can use to access NFS shares.
The acceptable values for this parameter are:

 -- Sys (AUTH_SYS authentication)
- Krb5 (Kerberos v5 authentication)
- Krb5i (Kerberos v5 authentication with integrity checking)
- Krb5p (Kerberos v5 authentication with privacy)
- All
- Default

If you specify All, Server for NFS configures Sys, Krb, Krbi, and Krbp on the share.
If you specify Default, Server for NFS configures Sys, Krb, and Krbi on the share.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: af, auth
Accepted values: sys, krb5, krb5i, krb5p, all, default

Required: False
Position: 3
Default value: Default
Accept pipeline input: True (ByPropertyName)
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

### -EnableAnonymousAccess
Configures an NFS share to allow anonymous users to access it.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: anon, AnonymousAccess

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableUnmappedAccess
Configures an NFS share to allow unmapped UNIX users to access a share by using the UID or GID.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: unmapped, UnmappedAccess

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LanguageEncoding
Specifies language encoding to configure on an NFS share.
You can use only one language on the share.

The acceptable values for this parameter are:

- Euc-jp (Japanese)
- Euc-tw (Chinese)
- Euc-kr (Korean)
- Shift-jis (Japanese)
- Big5 (Chinese)
- Ksc5601 (Korean)
- Gb2312-80 (Simplified Chinese)
- Ansi

```yaml
Type: String
Parameter Sets: (All)
Aliases: lang, encoding
Accepted values: euc-jp, euc-tw, euc-kr, shift-jis, big5, ksc5601, gb2312-80, ansi

Required: False
Position: 6
Default value: Ansi
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the NFS share to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ShareName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkName
Specifies the network name of a share.

For a local share, the network name is the host name.
For a server cluster, the network name is the network name in the resource group to which the share is scoped.

This parameter is not required when you create a local share.
In the case of a server cluster, specify the client access point.
If you do not specify a network name, **New-NfsShare** assigns a network name that belongs to the same resource group by default.

```yaml
Type: String
Parameter Sets: (All)
Aliases: netname

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of a new NFS share.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SharePath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
Configures the type of global ("All Machines") permissions on the NFS share.
The acceptable values for this parameter are:

- Readwrite
- Readonly
- No-access

```yaml
Type: String
Parameter Sets: (All)
Aliases: access
Accepted values: no-access, readonly, readwrite

Required: False
Position: 10
Default value: No-access
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsShare

## NOTES

## RELATED LINKS

[Get-NfsShare](./Get-NfsShare.md)

[Remove-NfsShare](./Remove-NfsShare.md)

[Set-NfsShare](./Set-NfsShare.md)

