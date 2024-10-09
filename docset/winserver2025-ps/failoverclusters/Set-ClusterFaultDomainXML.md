---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterFaultDomain.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterfaultdomainxml?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterFaultDomainXML
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

The `Set-ClusterFaultDomainXML` cmdlet sets the cluster fault domain using XML.

## EXAMPLES

### Example 1

```powershell
Set-ClusterFaultDomainXML -XML @"
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

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

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

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterFaultDomainXML](./Get-ClusterFaultDomainXML.md)
