---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0092F253-EE7B-4908-BD7F-60BF9DF5BE4A
manager: dansimp
---

# Get-NfsSharePermission

## SYNOPSIS
Gets information about permissions that an NFS server grants to exported NFS shares.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsSharePermission [-Name] <String> [[-ClientName] <String>] [[-ClientType] <String>]
 [[-Permission] <String>] [-AsJob] [-CimSession <CimSession[]>] [-NetworkName <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsSharePermission [-Path] <String> [[-ClientName] <String>] [[-ClientType] <String>]
 [[-Permission] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NfsSharePermission** cmdlet gets information about access permissions granted by a Network File System (NFS) server that has an NFS share configured.

## EXAMPLES

### Example 1: Get all permissions for a specified NFS share
```
PS C:\> Get-NfsSharePermission -Name "Export"
ClientName        : All Machines
ClientType        : Built-in Group
Name              : Export
Path              : C:\shares\Export
Permission        : READ, WRITE
AllowRootAccess   : ALLOW ACCESS
LanguageEncoding  : ansi
```

This command gets the permissions for an NFS share named Export.

### Example 2: Get read/write permissions for a specified NFS share
```
PS C:\> Get-NfsSharePermission -Name "Export" -Permission "readwrite"
```

This command gets the read/write permissions for an NFS share named Export.

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

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies a client type.
The acceptable values for this parameter are:

- host
- clientgroup
- netgroup

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
Specifies the type of access to get for an NFS share.
The acceptable values for this parameter are:

- no-access
- readonly
- readwrite

A client can have either read-only or read/write access.
Only the All Machines group can have all three types of access.

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/nfs/MSFT_NfsSharePermission

## NOTES

## RELATED LINKS



