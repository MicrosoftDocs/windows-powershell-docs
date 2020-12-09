---
external help file: IpamCapabilities.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Get-IpamCapability
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 575CBD45-55A1-476A-B107-1BB40946DAD5
---

# Get-IpamCapability

## SYNOPSIS
Gets all optional capabilities in IPAM.

## SYNTAX

```
Get-IpamCapability [-Capability <Capability[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamCapability** cmdlet gets all available optional capabilities in Internet Protocol address management (IPAM).
If you do not specify the **Capability** parameter, the cmdlet gets all optional capabilities in IPAM.
By default, IPAM enables all available optional capabilities.

Use the Disable-IpamCapability cmdlet to disable an optional IPAM capability.
Use the Enable-IpamCapability cmdlet to enable an optional IPAM capability.

Currently, IP address tracking is the only optional capability available.

## EXAMPLES

### Example 1: Get all optional capabilities in IPAM
```
PS C:\> Get-IpamCapability
Name                                                        Status

----                                                        ------

IpAddressTracking                                           Enabled
```

This command gets all the available optional capabilities in IPAM and the current status of the capabilities.

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

### -Capability
Specifies an array of optional IPAM capabilities.
Currently, IpAddressTracking is the only valid value for this parameter.

```yaml
Type: Capability[]
Parameter Sets: (All)
Aliases: 
Accepted values: IpAddressTracking

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### IpamCapability
An object that represents an optional IPAM capability and its status (enabled/disabled)

## NOTES

## RELATED LINKS

[Enable-IpamCapability](./Enable-IpamCapability.md)

[Disable-IpamCapability](./Disable-IpamCapability.md)

