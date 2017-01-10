---
author: brianlic
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
title: Set-ClusterFaultDomainXML
ms.assetid: C5269D6A-8D07-4601-997C-F517E3D26DC4
---

# Set-ClusterFaultDomainXML

## SYNOPSIS
Sets the cluster fault domain using XML.

## SYNTAX

```
Set-ClusterFaultDomainXML [-XML] <String> [-Flags <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ClusterFaultDomainXML** cmdlet sets the cluster fault domain using XML.

## EXAMPLES

### Example 1:
```
PS C:\>Set-ClusterFaultDomainXML -XML @"
<Topology>

 <Site Name="site1" Description="Site 1 with 4 nodes" Location="Site 1">
  <rack name="rack1_in_site_1" description="the only rack in site 1">
   <Node Name="K0617-VM02"/>
   <Node Name="K0617-VM03"/>
   <Node Name="K0617-VM04"/>
   <Node Name="K0617-VM05"/>
  </rack>
 </Site>

 <Site Name="site2" Description="Site 2 with 4 nodes" Location="Site 2">
  <rack name="rack1_in_site_2" description="the only rack in site 2">
   <Node Name="K0617-VM12"/>
   <Node Name="K0617-VM13"/>
   <Node Name="K0617-VM14"/>
   <Node Name="K0617-VM15"/>
  </rack>
 </Site>

 <Site Name="site3" Description="Site 3 with 4 nodes" Location="Site 3">
  <rack name="rack1_in_site_3" description="the only rack in site 3">
   <Node Name="K0621-VM17"/>
   <Node Name="K0621-VM18"/>
   <Node Name="K0621-VM19"/>
   <Node Name="K0621-VM20"/>
  </rack>
 </Site>

 <Site Name="site4" Description="Site 4 with 4 nodes" Location="Site 4">
  <rack name="rack1_in_site_4" description="the only rack in site 4">
   <Node Name="K0629-VM07"/>
   <Node Name="K0629-VM08"/>
   <Node Name="K0629-VM09"/>
   <Node Name="K0629-VM10"/>
  </rack>
 </Site>

</Topology>
"@
```

This command sets the cluster fault domain using the xml in the example

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
Specifies any flags that need to be passed in when setting the cluster fault domain.

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

### -XML
Specifies a string form containing XML that describes what to set the cluster fault domains to.

```yaml
Type: String
Parameter Sets: (All)
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

[Get-ClusterFaultDomainXML](./Get-ClusterFaultDomainXML.md)

