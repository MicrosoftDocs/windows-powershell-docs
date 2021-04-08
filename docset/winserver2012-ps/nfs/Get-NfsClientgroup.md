---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsclientgroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsClientgroup

## SYNOPSIS
Gets client groups configured on an NFS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsClientgroup [[-ClientGroupName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ExcludeName <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsClientgroup [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -LiteralName <String[]>
```

## DESCRIPTION
The **Get-NfsClientGroup** cmdlet gets a list of client groups configured on a Network File System (NFS) server and the list of members of the client groups.
By default, the cmdlet enumerates all the client groups configured on a server.
You can use the optional **ClientGroupName** parameter to get a specific client group.

## EXAMPLES

### Example 1: Get client groups by using a name
```
PS C:\> Get-NfsClientgroup -ClientGroupName ClientGroup*
ClientGroupMembers : {contoso-fs2}
ClientGroupName    : clientgroupA

ClientGroupMembers : {contoso-fs1}
ClientGroupName    : clientgroupB
```

This command gets the client groups on local computer that start with the name ClientGroup.

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

### -ClientGroupName
Specifies an array of client group names.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludeName
Specifies an array of client group names to exclude from the client groups that the cmdlet gets from the NFS server.

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

### -LiteralName
Specifies an array of client groups to get from the NFS server.

The cmdlet uses the value of **LiteralName** exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsClientgroup

## NOTES

## RELATED LINKS

[New-NfsClientgroup](./New-NfsClientgroup.md)

[Remove-NfsClientgroup](./Remove-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

[Set-NfsClientgroup](./Set-NfsClientgroup.md)

