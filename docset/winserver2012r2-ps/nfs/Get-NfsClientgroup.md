---
external help file: MSFT_NfsClientGroup.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Get-NfsClientgroup
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A1D81FC8-CCD1-4003-8EAA-135CED48B62D
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-NfsClientgroup

## SYNOPSIS
Gets client groups configured on an NFS server.

## SYNTAX

### ByName (Default)
```
Get-NfsClientgroup [[-ClientGroupName] <String[]>] [-ExcludeName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLiteralName
```
Get-NfsClientgroup -LiteralName <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
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
Aliases: Session

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
Parameter Sets: ByName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludeName
Specifies an array of client group names to exclude from the client groups that the cmdlet gets from the NFS server.

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

### -LiteralName
Specifies an array of client groups to get from the NFS server.

The cmdlet uses the value of **LiteralName** exactly as typed.
The cmdlet does not interpret any characters as wildcards.
If the name includes escape characters, enclose it in single quotation marks (').
Single quotation marks instruct Windows PowerShell not to interpret any characters as escape sequences.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsClientgroup

## NOTES

## RELATED LINKS

[New-NfsClientgroup](./New-NfsClientgroup.md)

[Remove-NfsClientgroup](./Remove-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

[Set-NfsClientgroup](./Set-NfsClientgroup.md)

