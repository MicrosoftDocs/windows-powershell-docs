---
external help file: iSCSISession.cdxml-help.xml
Module Name: iSCSI
online version: 
schema: 2.0.0
title: Unregister-IscsiSession
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BD05B373-4201-4531-BBAE-89C400F95573
---

# Unregister-IscsiSession

## SYNOPSIS
Removes an active iSCSI session from being persistent using the session identifier as input.

## SYNTAX

### BySessionIdentifier (Default)
```
Unregister-IscsiSession -SessionIdentifier <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Unregister-IscsiSession -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-IscsiSession** cmdlet removes a registered iSCSI session to prevent it from automatically reconnection on reboot.

## EXAMPLES

### Example 1
```
This information shows the output from the Get-iSCSISession. Since no additional switches or filters were used, this returns information about all iSCSI sessions across all iSCSI connections.
PS C:\>Get-IscsiSession
AuthenticationType      : NONE 
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0 
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com 
InitiatorPortalAddress  : 
InitiatorSideIdentifier : 400001370001 
IsConnected             : True 
IsDataDigest            : False 
IsDiscovered            : True 
IsHeaderDigest          : False 
IsMultipathEnabled      : False 
IsPersistent            : True 
NumberOfConnections     : 1 
SessionIdentifier       : fffffa800d008430-4000013700000001 
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target 
TargetSideIdentifier    : 0200
 
AuthenticationType      : NONE 
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0 
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com 
InitiatorPortalAddress  : 
InitiatorSideIdentifier : 400001370004 
IsConnected             : True 
IsDataDigest            : False 
IsDiscovered            : True 
IsHeaderDigest          : False 
IsMultipathEnabled      : False 
IsPersistent            : True 
NumberOfConnections     : 1 
SessionIdentifier       : fffffa800d008430-4000013700000002 
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target 
TargetSideIdentifier    : 0100 
 
AuthenticationType      : NONE 
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0 
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com 
InitiatorPortalAddress  : 
InitiatorSideIdentifier : 400001370002 
IsConnected             : True 
IsDataDigest            : False 
IsDiscovered            : True 
IsHeaderDigest          : False 
IsMultipathEnabled      : False 
IsPersistent            : True 
NumberOfConnections     : 1 
SessionIdentifier       : fffffa800d008430-4000013700000003 
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target 
TargetSideIdentifier    : 0300 


PS C:\>Unregister-IscsiSession -SessionIdentifier fffffa800d008430-4000013700000001
```

This example gets a list of sessions, and then uses this cmdlet to remove the session.

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

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 
                         
To send items from the interactive window down the pipeline, click to select the items and then click OK. 
Shift-click and Ctrl-click are supported.

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

### -SessionIdentifier
Specifies the session identifier.

```yaml
Type: String[]
Parameter Sets: BySessionIdentifier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

[iSCSI on TechNet](https://www.microsoft.com/iSCSI)

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Get-iSCSISession](./Get-IscsiSession.md)


