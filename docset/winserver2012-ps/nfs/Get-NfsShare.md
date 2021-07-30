---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsshare?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsShare

## SYNOPSIS
Gets NFS shares on an NFS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsShare [[-Name] <String[]>] [-IsClustered] [[-NetworkName] <String[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-ExcludeName <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsShare [[-Path] <String[]>] [-IsClustered] [[-NetworkName] <String[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-ExcludePath <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NfsShare [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -LiteralPath <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-NfsShare [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -LiteralName <String[]>
```

## DESCRIPTION
The **Get-NfsShare** cmdlet gets Network File System (NFS) shares that are configured on a computer.
By default, the cmdlet gets all the nonclustered (standard) shares from the local computer.
If the server belongs to a server cluster, the cmdlet enumerates all the local shares in addition to the cluster shares that belong to resource groups that the local node owns.

The local node is the node where you run the cmdlet.
Shares that belong to resource groups that other nodes of the cluster own are not enumerated.

## EXAMPLES

### Example 1: Get an NFS share
```
PS C:\> Get-NfsShare -Name "NFSshare01"
Name:                 nfsexport
Path:                 C:\shares\nfsexport
NetworkName:          GAPRASAD-TST22
Availability:         Standard (not clustered)
Online:               True
AnonymousAccess:       Disabled
AnonymousGid: -2
AnonymousUID: -2
UnmappedUserAccess:   Enabled
Authentication:         {sys, Krb5, Krb5i, Krb5p}
```

This command gets an NFS share named NFSshare01.

### Example 2: Get all NFS shares on a local computer
```
PS C:\> Get-NfsShare

Name:                  nfsexportA
Path:                  C:\shares\nfsexportA
NetworkName:           contoso-fs
Availability:          Standard (not clustered)
Online:                True
AnonymousAccess:       Disabled
AnonymousGID:          -2
AnonymousUID:          -2
UnmappedUserAccess:    Enabled
Authentication:        {sys, Krb5, Krb5i, Krb5p}
Name:                  nfsexportB
Path:                  C:\shares\nfsexportB
NetworkName:           contoso-fs
Availability:          Standard (not clustered)
Online:                True
AnonymousAccess:       Disabled
AnonymousGID:          -2
AnonymousUID:          -2
UnmappedUserAccess:    Enabled
Authentication:        {sys, Krb5, Krb5i, Krb5p}
```

This command gets all the NFS shares on a local computer.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -ExcludeName
Specifies an array of share names to exclude from the list of shares that the cmdlet gets from an NFS server.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ExcludePath
Specifies an array of share paths to exclude from the list of shares that the cmdlet gets from an NFS server.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsClustered
Enumerates shares that are highly available and are configured in a failover cluster.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralName
Specifies an array of share names to get from an NFS server.

The cmdlet uses the value of **LiteralName** exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell®not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath
Specifies an array of share paths to get from an NFS server.

The cmdlet uses the value of **LiteralName** exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of share names to get from a local NFS server.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NetworkName
Specifies an array of network names.
**Get-NfsShare** gets the NFS shares scoped to specified networks.

For a local NFS share, the network name is the host name.
For a server cluster, the network name is the network name in the resource group to which the share is scoped.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies an array of share paths on a local NFS server.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsShare

## NOTES

## RELATED LINKS

[New-NfsShare](./New-NfsShare.md)

[Remove-NfsShare](./Remove-NfsShare.md)

[Set-NfsShare](./Set-NfsShare.md)

