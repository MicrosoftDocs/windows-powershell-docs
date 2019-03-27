---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMNetworkAdapterAcl
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CCA47110-FE0F-40DE-ADEC-8C6D7E254DAA
---

# Get-VMNetworkAdapterAcl

## SYNOPSIS
Gets the ACLs configured for a virtual machine network adapter.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterAcl [[-VMName] <String[]>] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>]
 [<CommonParameters>]
```

### VMSnapshot
```
Get-VMNetworkAdapterAcl [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### ManagementOS
```
Get-VMNetworkAdapterAcl [-ManagementOS] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>]
 [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterAcl [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMNetworkAdapterAcl** cmdlet gets the ACLs configured for a virtual machine network adapter.
If an ACL entry is created to be applied to both directions, it will appear under the list of entries for the inbound direction and under the list of entries for the outbound direction in the output from Get-VMNetworkAdapterAcl.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMNetworkAdapterAcl -VMName Redmond
```

Gets all the port ACLs configured on virtual machine Redmond.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the ACLs configured for a virtual machine network adapter are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the ACLs are to be configured in the management (i.e.
the parent, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter for which the configured ACLs are to be retrieved.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: ResourceObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the virtual network adapter name for which the configured ACLs are to be retrieved.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot in which the ACLs configured for a virtual machine network adapter are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

