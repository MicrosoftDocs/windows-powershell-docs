---
author: Kateyanne
description: 
external help file: MSFT_WdsClient_v1.0.cdxml-help.xml
manager: jasgro
Module Name: WDS
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wds/deny-wdsclient?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Deny-WdsClient
---

# Deny-WdsClient

## SYNOPSIS
Denies approval for clients.

## SYNTAX

```
Deny-WdsClient [-RequestID <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Deny-WdsClient** cmdlet denies approval for clients.
Unknown clients require approval before the server that runs Windows Deployment Services boots the client in Pre-Boot Execution Environment (PXE).
Use the Approve-WdsClient cmdlet to approve clients.

You can specify a single device to deny by using a request ID.
The server that runs Windows Deployment Services allocates a request ID to a device.
If you do not specify a client to deny, the cmdlet denies approval for all pending clients.

## EXAMPLES

### Example 1: Deny approval for all pending clients
```
PS C:\> Deny-WdsClient
```

This command denies approval for all pending pre-staged clients.

### Example 2: Deny approval for a pending client
```
PS C:\>Deny-WdsClient -RequestID 5
```

This command denies approval for the pre-staged client that has the specified request ID.

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

### -RequestID
Specifies the request ID that the server that runs Windows Deployment Services allocates to a device in the Pending Device database.
To find the Request ID, use the Get-WdsClient cmdlet and look for the **RequestId** property of the client.
If you do not specify this parameter, the cmdlet denies all devices.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Approve-WdsClient](./Approve-WdsClient.md)

[Get-WdsClient](./Get-WdsClient.md)

[New-WdsClient](./New-WdsClient.md)

[Remove-WdsClient](./Remove-WdsClient.md)

[Set-WdsClient](./Set-WdsClient.md)

