---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsShare.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsShare
---

# Get-NfsShare

## SYNOPSIS
Gets NFS shares on an NFS server.

## SYNTAX

### ByName (Default)
```
Get-NfsShare [[-Name] <String[]>] [-ExcludeName <String[]>] [[-NetworkName] <String[]>] [-IsClustered]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLiteralName
```
Get-NfsShare -LiteralName <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPath
```
Get-NfsShare [[-Path] <String[]>] [-ExcludePath <String[]>] [[-NetworkName] <String[]>] [-IsClustered]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLiteralPath
```
Get-NfsShare -LiteralPath <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
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

### -ExcludeName
Specifies an array of share names to exclude from the list of shares that the cmdlet gets from an NFS server.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludePath
Specifies an array of share paths to exclude from the list of shares that the cmdlet gets from an NFS server.

```yaml
Type: String[]
Parameter Sets: ByPath
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
Parameter Sets: ByName, ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralName
Specifies an array of share names to get from an NFS server.

The cmdlet uses the value of *LiteralName* exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell®not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: ByLiteralName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath
Specifies an array of share paths to get from an NFS server.

The cmdlet uses the value of *LiteralPath* exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: ByLiteralPath
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
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkName
Specifies an array of network names.
**Get-NfsShare** gets the NFS shares scoped to specified networks.

For a local NFS share, the network name is the host name.
For a server cluster, the network name is the network name in the resource group to which the share is scoped.

```yaml
Type: String[]
Parameter Sets: ByName, ByPath
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies an array of share paths on a local NFS server.

```yaml
Type: String[]
Parameter Sets: ByPath
Aliases:

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsShare

## NOTES

## RELATED LINKS

[New-NfsShare](./New-NfsShare.md)

[Remove-NfsShare](./Remove-NfsShare.md)

[Set-NfsShare](./Set-NfsShare.md)

