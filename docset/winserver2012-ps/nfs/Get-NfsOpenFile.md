---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsopenfile?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsOpenFile

## SYNOPSIS
Gets information about files that are open on an NFS server for a client computer.

## SYNTAX

```
Get-NfsOpenFile [[-Path] <String[]>] [[-StateId] <String[]>] [[-ClientId] <UInt64[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NfsOpenFile** cmdlet gets information about files that are in a Network File System (NFS) share and hosted by an NFS server, and that a client computer is currently holding open.
You can specify a client identifier to view all files that are in an open state for the specified client.

## EXAMPLES

### Example 1: Get all open files on an NFS server
```
PS C:\> Get-NfsOpenFile
```

This command gets all open files on an NFS server.

### Example 2: Get all open files for a specified client computer on an NFS server
```
PS C:\> Get-NfsOpenFile -ClientId 101
```

This command gets all open files on an NFS server for a client computer that has the ID 101.

### Example 3: Get all open files on an NFS server by path and file name by using a wildcard
```
PS C:\> Get-NfsOpenFile -Path "C:\Windows\Setup*"
```

This command gets all open files on an NFS server that are in the C:\Windows folder and that contain the word Setup.

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

### -ClientId
Specifies the ID of one or more client computers.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path and file name of an open file on an NFS server.
For example, C:\Windows\Setup.log.
You can also use a wildcard to specify multiple paths and files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -StateId
Specifies the state ID of one or more open files.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsOpenFile

## NOTES

## RELATED LINKS

[Revoke-NfsOpenFile](./Revoke-NfsOpenFile.md)

