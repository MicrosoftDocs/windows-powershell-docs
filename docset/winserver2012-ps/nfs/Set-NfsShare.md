---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/set-nfsshare?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NfsShare

## SYNOPSIS
Changes configuration settings of an NFS share.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NfsShare [-Name] <String> [[-Authentication] <String[]>] [[-EnableAnonymousAccess] <Boolean>]
 [[-EnableUnmappedAccess] <Boolean>] [[-AnonymousGid] <Int32>] [[-AnonymousUid] <Int32>]
 [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>] [[-Permission] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-NetworkName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NfsShare [-Path] <String> [[-Authentication] <String[]>] [[-EnableAnonymousAccess] <Boolean>]
 [[-EnableUnmappedAccess] <Boolean>] [[-AnonymousGid] <Int32>] [[-AnonymousUid] <Int32>]
 [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>] [[-Permission] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NfsShare** cmdlet changes configuration settings for an existing share that Server for Network File System (NFS) exports.
You can use the **NetworkName** parameter to select a share in a server cluster.
**NetworkName** is not required when you modify configuration settings of non-clustered (standard) shares.

## EXAMPLES

### Example 1: Enable unmapped user access on an NFS share
```
PS C:\> Set-NfsShare -Name "NFSshare01" -EnableUnmappedAccess $true
```

This command enables unmapped users to access the NFS share NFSshare01.

### Example 2: Set the authentication protocol of an NFS share
```
PS C:\> Set-NfsShare -Name "NFSshare01" -Authentication sys,krb5 -AnonymousUid 100 -AnonymousGid 200
```

This command sets the authentication protocol as AUTH_SYS and Kerberos v5 on the NFS share NFSshare01.
The command also sets the anonymous UID to 100 and the anonymous GID to 200.

## PARAMETERS

### -AllowRootAccess
Grants the UNIX root user access to a share.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AnonymousGid
Specifies the group identifier (GID) that Server for NFS uses for anonymous users who access an NFS share.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AnonymousUid
Specifies the user identifier (UID) that Server for NFS uses for anonymous users who access an NFS share.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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

### -Authentication
Specifies an array of authentication types that an NFS client can use to access NFS shares.

Valid values are: 
 -- Sys (AUTH_SYS authentication) 
- Krb5 (Kerberos v5 authentication)
- Krb5i (Kerberos v5 authentication with integrity checking)
- Krb5p (Kerberos v5 authentication with privacy)
- All
- Default

If you specify **All**, Server for NFS configures Sys, Krb5, Krb5i, and Krb5p on the share.
If you specify **Default**, Server for NFS configures Sys, Krb5, and Krb5i on the share.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAnonymousAccess
Configures the NFS share to allow anonymous users to access it.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableUnmappedAccess
Configures the NFS share to allow unmapped UNIX users to access the share by using a UID or GID.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LanguageEncoding
Specifies the language encoding to configure on an NFS share.
You can use only one language on the share.

Valid values are:
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
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an NFS share to modify.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkName
Specifies the network name of the share.
You cannot change the network name of an existing share.

For a local share, the network name is the host name.
For a server cluster, the network name is the network name in the resource group to which the share is scoped.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of an NFS share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Permission
Configures the type of global ("All Machines") permissions on the NFS share.
The acceptable values for this parameter are:
- Readwrite
- Readonly
- No-access

Valid values are:
- Readwrite
- Readonly
- No-access

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 9
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

## NOTES

## RELATED LINKS

[Get-NfsShare](./Get-NfsShare.md)

[New-NfsShare](./New-NfsShare.md)

[Remove-NfsShare](./Remove-NfsShare.md)

