---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMultichannelConnection.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Update-SmbMultichannelConnection
ms.reviewer:
ms.assetid: 42A5CB1C-50F8-4AB1-B699-9B51A54B02D4
---

# Update-SmbMultichannelConnection

## SYNOPSIS
Forces the SMB client to update the multi-channel-related information.

## SYNTAX

```
Update-SmbMultichannelConnection [[-ServerName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SmbMultichannelConnection** cmdlet forces the Server Message Block (SMB) client to update the multi-channel-related information.
To do this, the SMB client communicates with one or more servers to which it is connected to get the latest information about the network interfaces that is shared.
If you specify a server name, the SMB client communicates with only that server to get the information.
If no parameter is specified, the SMB client communicates with all of the servers to which it is connected.

## EXAMPLES

### Example 1: Update multi-channel-related information
```
PS C:\>Update-SmbMultichannelConnection
```

This command forces the SMB client to update the multi-channel-related information.

### Example 2: Update multi-channel-related information for an SMB server
```
PS C:\>Update-SmbMultichannelConnection -ServerName "Contoso-SO"
```

This command forces the SMB client to update the multi-channel-related information for the SMB server named Contoso-SO.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the name of the server to which to connect from the SMB client to get the latest information about the network interfaces it has.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)

