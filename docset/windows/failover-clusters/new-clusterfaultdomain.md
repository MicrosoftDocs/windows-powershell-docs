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
title: New-ClusterFaultDomain
ms.assetid: C52F5314-DF0E-4C1F-B0AD-A5AB290493F9
---

# New-ClusterFaultDomain

## SYNOPSIS
Creates a fault domain in the cluster.

## SYNTAX

```
New-ClusterFaultDomain -Name <String> [-FaultDomain <String>] -FaultDomainType <FaultDomainType>
 [-Description <String>] [-Location <String>] [-Flags <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-ClusterFaultDomain** cmdlet creates a fault domain in the cluster.
Additionally, you can specify the relationship between the fault domains when they are created.

## EXAMPLES

### Example 1: Create a cluster fault domain in an existing fault domain
```
PS C:\>New-ClusterFaultDomain -Type Rack -Name "Rack1" -FaultDomain "Site001"
Name  Type ParentName ChildrenNames
----  ---- ---------- -------------
Rack1 Rack Site1
```

This command creates a cluster fault domain of type Rack named Rack1 in the existing fault domain named Site001.

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

### -Description
Specifies the description of the cluster fault domain that this cmdlet creates.

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

### -FaultDomain
Specifies the name of the fault domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Parent

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainType
Specifies the type of the fault domain that this cmdlet creates.

The acceptable values for this parameter are:

- Unknown
- Site
- Rack
- Chassis
- Node

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases: Type
Accepted values: Unknown, Site, Rack, Chassis, Node

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Flags
Any flags that need to be passed in when creating the cluster fault domain.

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

### -Location
A string describing the location of the cluster fault domain that will be created.

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

### -Name
Specifies the name of the cluster fault domain that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-ClusterFaultDomain](./Get-ClusterFaultDomain.md)

[Remove-ClusterFaultDomain](./Remove-ClusterFaultDomain.md)

[Set-ClusterFaultDomain](./Set-ClusterFaultDomain.md)

