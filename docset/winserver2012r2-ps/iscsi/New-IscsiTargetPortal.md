---
external help file: iSCSITargetPortal.cdxml-help.xml
Module Name: iSCSI
online version: 
schema: 2.0.0
title: New-IscsiTargetPortal
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8740AFC8-89A6-404C-967D-F7C0D3877BC5
---

# New-IscsiTargetPortal

## SYNOPSIS
Configures an iSCSI target portal.

## SYNTAX

```
New-IscsiTargetPortal -TargetPortalAddress <String> [-TargetPortalPortNumber <UInt16>]
 [-InitiatorPortalAddress <String>] [-IsHeaderDigest <Boolean>] [-IsDataDigest <Boolean>]
 [-AuthenticationType <String>] [-InitiatorInstanceName <String>] [-ChapUsername <String>]
 [-ChapSecret <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-IscsiTargetPortal** cmdlet connects a new iSCSI target portal.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-IscsiTargetPortal -TargetPortalAddress testIscsi
InitiatorInstanceName      : 
InitiatorNodeAddress       : 
InitiatorPortalAddress     : 
InititorIPAdressListNumber : 4294967295 
IsDataDigest               : False 
IsHeaderDigest             : False 
TargetPortalAddress        : testIscsi 
TargetPortalPortNumber     : 3260
```

This example adds a new iSCSI target portal with the name testIscsi to perform discovery

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

### -AuthenticationType
Specifies the type of authentication to use when logging into the target.
Valid values are **None**, **OneWayCHAP**, and **MutualCHAP**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChapSecret
Specifies the CHAP secret to use when establishing a connection authenticated by using CHAP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChapUsername
Specifies the user name to use when establishing a connection authenticated by using Mutual CHAP.

```yaml
Type: String
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

### -InitiatorInstanceName
The name of the initiator instance that the iSCSI initiator service uses to send **SendTargets** requests to the target portal.
If no instance name is specified, the iSCSI initiator service chooses the initiator instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorPortalAddress
Specifies the IP address or DNS name associated with the portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IA

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsDataDigest
Enables data digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsHeaderDigest
Enables header digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPortalAddress
Specifies the IP address or DNS name of the target portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TA

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPortalPortNumber
Specifies the TCP/IP port number for the target portal.
By default, the port number is `3260`.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](https://www.microsoft.com/iSCSI)

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)


