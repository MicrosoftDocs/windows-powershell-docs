---
author: brianlic-msft
description: 
external help file: ClusterFaultDomain.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterFaultDomainXML
ms.assetid: E588BA4C-36AB-4A22-ADBA-4683E4530354
---

# Get-ClusterFaultDomainXML

## SYNOPSIS
Gets the fault domain as an XML string.

## SYNTAX

```
Get-ClusterFaultDomainXML [-Flags <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterFaultDomainXML** cmdlet gets the fault domain as an XML string.

## EXAMPLES

### Example 1: Get all fault domains in the cluster in XML form
```
PS C:\>Get-ClusterFaultDomainXML
<Topology>
        <Node Name="NMALIWA-VM-1101" Description="" Location=""/>
</Topology>
```

This command gets all the fault domains in the cluster on the local node in XML form.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

### -Flags
Specifies an optional set of flags that can change this cmdlet, currently none are supported.
Reserved for future use

```yaml
Type: UInt32
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

[Set-ClusterFaultDomainXML](./Set-ClusterFaultDomainXML.md)

