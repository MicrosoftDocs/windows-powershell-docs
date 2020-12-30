---
external help file: SmbMultichannelConnection.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Update-SmbMultichannelConnection
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 42A5CB1C-50F8-4AB1-B699-9B51A54B02D4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Update-SmbMultichannelConnection

## SYNOPSIS
Forces the Server Message Block (SMB) client to update the multi-channel-related information.

## SYNTAX

```
Update-SmbMultichannelConnection [[-ServerName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SmbMultichannelConnection** cmdlet forces the Server Message Block (SMB) client to update the multi-channel-related information.
To do this the SMB client will communicate with one or more servers to which it is connected, to get the latest information on the network interfaces that is shared.
If a server name is provided, then the SMB client will communicate with only that server to get the information.
If no parameter is provided, then the SMB client will communicate with all of the servers to which it is connected.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Update-SmbMultichannelConnection
```

This example forces the SMB client to update the multi-channel-related information.

### EXAMPLE 2
```
PS C:\>Update-SmbMultichannelConnection -ServerName Contoso-SO
```

This example forces the SMB client to update the multi-channel-related information for the SMB server named Contoso-SO.

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

### -ServerName
Specifies the name of the server to which to connect from the SMB client to get the latest information on the network interfaces it has.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)

