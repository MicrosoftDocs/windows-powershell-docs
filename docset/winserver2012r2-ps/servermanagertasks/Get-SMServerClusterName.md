---
external help file: ServerManagerTasks.cdxml-help.xml
Module Name: ServerManagerTasks
online version: 
schema: 2.0.0
title: Get-SMServerClusterName
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2C57BC34-F9B7-419A-80E6-563465BCCF2A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SMServerClusterName

## SYNOPSIS
Gets the name of the failover cluster of which a server is a member, if applicable.

## SYNTAX

```
Get-SMServerClusterName [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMServerClusterName** cmdlet retrieves the name of the failover cluster to which a server belongs, if it is a member of a cluster.

## EXAMPLES

### Example 1: Get the server cluster name
```
PS C:\>Get-SMServerClusterName
```

This command gets the server cluster name.
The command fails if the server is not a member of a cluster.

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

## NOTES

## RELATED LINKS

