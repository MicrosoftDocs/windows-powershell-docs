---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/revoke-nfssharepermission?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Revoke-NfsSharePermission

## SYNOPSIS
Revokes permission to access shares that an NFS server exports.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Revoke-NfsSharePermission [-Name] <String> [-ClientName] <String> [-ClientType] <String> [-AsJob]
 [-CimSession <CimSession[]>] [-NetworkName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Revoke-NfsSharePermission [-Path] <String> [-ClientName] <String> [-ClientType] <String> [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Revoke-NfsSharePermission** cmdlet revokes permissions previously granted by a Network File System (NFS) server that has an NFS share configured.
You can use the **Get-NfsSharePermission** cmdlet to get a list of the permissions configured on an NFS share.

## EXAMPLES

### Example 1: Revoke NFS share permissions for a specified host
```
PS C:\> Revoke-NfsSharePermission -Name "Export" -ClientName "contoso-fs" -ClientType "host"
```

This command revokes permissions for a host computer named contoso-fs on an NFS share called Export.
The command identifies the client as a host client type.

### Example 2: Revoke NFS share permissions for a specified group
```
PS C:\> Revoke-NfsSharePermission -Name "Export" -ClientName "contoso-netgroup" -ClientType "netgroup"
```

This command revokes permissions for a netgroup named contoso-netgroup on an NFS share called Export.
The command identifies the client as a netgroup type.

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
Specifies the network name of an NFS share.

For a local share, the network name is the host name.
For a cluster, the network name is the network name displayed in the resource group to which the share is scoped.

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

[Grant-NfsSharePermission](./Grant-NfsSharePermission.md)

