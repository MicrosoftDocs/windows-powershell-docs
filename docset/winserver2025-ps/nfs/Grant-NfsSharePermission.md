---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/grant-nfssharepermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-NfsSharePermission
---

# Grant-NfsSharePermission

## SYNOPSIS
Grants permission to access shares that an NFS server exports.

## SYNTAX

### ByName (Default)
```
Grant-NfsSharePermission [-ClientName] <String> [-ClientType] <String> [[-Permission] <String>]
 [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>] [-Name] <String> [-NetworkName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPath
```
Grant-NfsSharePermission [-Path] <String> [-ClientName] <String> [-ClientType] <String>
 [[-Permission] <String>] [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-NfsSharePermission** cmdlet configures access permissions to a Network File System (NFS) share that an NFS server exports.
You can use **Grant-NfsSharePermission** to grant permissions for a share by using a specified name or path.

You can choose the type of permissions to provide to client computers, netgroups, or client groups.

You can choose to fence the language encoding across individual hosts or netgroups.
Services for NFS supports fencing of shares by using the following principals:

- Hosts
- Client groups
- Netgroups

## EXAMPLES

### Example 1: Grant NFS share permissions to a specified client computer
```
PS C:\> Grant-NfsSharePermission -Name "Export" -ClientName "contoso-fs" -ClientType "host" -Permission "readwrite"
```

This command grants read/write access to a share named Export for a computer named contoso-fs.

### Example 2: Grant NFS share permissions to a specified client group
```
PS C:\> Grant-NfsSharePermission -Name "Export" -ClientName "contoso-clientgroup" -ClientType "clientgroup" -Permission "readonly"
```

This command grants read-only access to a share named Export for a client group named contoso-clientgroup.

### Example 3: Grant NFS share permissions to a specific UNIX computer with root user access
```
PS C:\> Grant-NfsSharePermission -Name "Export" -ClientName "192.168.1.8" -ClientType "host" -Permission "readonly" -AllowRootAccess:$true
```

This command grants read access to a share named Export for a computer specifying its IP address, and also grants UNIX root user access.

## PARAMETERS

### -AllowRootAccess
Specifies whether to grant the UNIX root user access to an NFS share.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
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

### -ClientName
Specifies a client name.
The client name can be a host name or IP address, netgroup name, or client group name.
To specify the type of client, use the *ClientType* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Client

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies a client type.
Use the builtin client type only when the *ClientName* parameter value is All Machines.

Valid values are:

- host
- clientgroup
- netgroup
- builtin

```yaml
Type: String
Parameter Sets: (All)
Aliases: Type
Accepted values: host, netgroup, clientgroup, builtin

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -LanguageEncoding
Specifies the type of language encoding used for access permissions configured on an NFS share.
You can use only one of the following values for a share:

- euc-jp (Japanese)
- euc-tw (Chinese)
- euc-kr (Korean)
- shift-jis (Japanese)
- big5 (Chinese)
- ksc5601 (Korean)
- gb2312-80 (Simplified Chinese)
- ansi

```yaml
Type: String
Parameter Sets: (All)
Aliases: Lang, Encoding
Accepted values: euc-jp, euc-tw, euc-kr, shift-jis, big5, ksc5601, gb2312-80, ansi

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an NFS share.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ShareName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkName
Specifies the scoped network name of an NFS share.

On a local share, *NetworkName* is the host name.
On a cluster, it is the network name in the resource group to which the share is scoped.

```yaml
Type: String
Parameter Sets: ByName
Aliases: netname

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
Parameter Sets: ByPath
Aliases: SharePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
Specifies the type of access to grant for an NFS share.
Valid values are:

- no-access
- readonly
- readwrite

```yaml
Type: String
Parameter Sets: (All)
Aliases: Access
Accepted values: no-access, readonly, readwrite

Required: False
Position: 3
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

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsSharePermission](./Get-NfsSharePermission.md)

[Revoke-NfsSharePermission](./Revoke-NfsSharePermission.md)

