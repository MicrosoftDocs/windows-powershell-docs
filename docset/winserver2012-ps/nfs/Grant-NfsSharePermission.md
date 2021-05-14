---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/grant-nfssharepermission?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Grant-NfsSharePermission

## SYNOPSIS
Grants permission to access shares that an NFS server exports.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Grant-NfsSharePermission [-Name] <String> [-ClientName] <String> [-ClientType] <String>
 [[-Permission] <String>] [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>] [-AsJob]
 [-CimSession <CimSession[]>] [-NetworkName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Grant-NfsSharePermission [-Path] <String> [-ClientName] <String> [-ClientType] <String>
 [[-Permission] <String>] [[-LanguageEncoding] <String>] [[-AllowRootAccess] <Boolean>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
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

## PARAMETERS

### -AllowRootAccess
Specifies whether to grant the UNIX root user access to an NFS share.

```yaml
Type: Boolean
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

### -ClientName
Specifies a client name.
The client name can be a host name or IP address, netgroup name, or client group name.
To specify the type of client, use the **ClientType** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies a client type.
Use the builtin client type only when the **ClientName** parameter value is All Machines.

Valid values are:

- host
- clientgroup
- netgroup
- builtin

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an NFS share.

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
Specifies the scoped network name of an NFS share.

On a local share, **NetworkName** is the host name.
On a cluster, it is the network name in the resource group to which the share is scoped.

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
Aliases: 

Required: False
Position: 4
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

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsSharePermission](./Get-NfsSharePermission.md)

[Revoke-NfsSharePermission](./Revoke-NfsSharePermission.md)

