---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsAttestation
ms.assetid: A0BA9FED-90DF-4B72-B6BD-49D2B2B7027D
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsAttestationHostGroup
ms.reviewer:
---

# Get-HgsAttestationHostGroup

## SYNOPSIS
Gets attestation policies based on host groups.

## SYNTAX

```
Get-HgsAttestationHostGroup [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsAttestationHostGroup** cmdlet gets attestation policies that are based on the configuration of Active Directory host groups.
To obtain a particular host group policy, specify it by name.

## EXAMPLES

### Example 1: Get policies for all host groups
```
PS C:\> Get-HgsAttestationHostGroup
```

This command gets policies for all host groups configured with the Attestation service.

### Example 2: Get a specific policy for a host group
```
PS C:\> Get-HgsAttestationHostGroup -Name "TrustedADHostGroup14"
```

This command gets the policy for the host group named TrustedADHostGroup14.

## PARAMETERS

### -Name
Specifies the friendly name of the host group for which this cmdlet gets the policy.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Specialized.StringCollection
This cmdlet returns a **StringCollection** object.

## NOTES

## RELATED LINKS

[Add-HgsAttestationHostGroup](./Add-HgsAttestationHostGroup.md)

[Remove-HgsAttestationHostGroup](./Remove-HgsAttestationHostGroup.md)

