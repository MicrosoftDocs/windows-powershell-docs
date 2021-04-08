---
author: Kateyanne
external help file: MsDTC_Cmdlets.xml
manager: dansimp
Module Name: MsDTC
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msdtc/set-dtcclustertmmapping?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DtcClusterTMMapping

## SYNOPSIS
Modifies an existing cluster DTC mapping.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ClusterResourceName <String>] [-ThrottleLimit <Int32>]
 -Local <Boolean> -Name <String>
```

### UNNAMED_PARAMETER_SET_2
```
Set-DtcClusterTMMapping [-CimSession <CimSession[]>] [-Local <Boolean>] [-ThrottleLimit <Int32>]
 -ClusterResourceName <String> -Name <String>
```

### UNNAMED_PARAMETER_SET_3
```
Set-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ClusterResourceName <String>] [-Local <Boolean>]
 [-ThrottleLimit <Int32>] -ComPlusAppId <String> -Name <String>
```

### UNNAMED_PARAMETER_SET_4
```
Set-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ClusterResourceName <String>] [-Local <Boolean>]
 [-ThrottleLimit <Int32>] -ExecutablePath <String> -Name <String>
```

### UNNAMED_PARAMETER_SET_5
```
Set-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ClusterResourceName <String>] [-Local <Boolean>]
 [-ThrottleLimit <Int32>] -Name <String> -Service <String>
```

## DESCRIPTION
The **Set-DtcClusterTMMapping** cmdlet modifies an existing cluster Distributed Transaction Coordinator (DTC) mapping.
This cmdlet is supported on clustered computers only.

## EXAMPLES

### Example 1: Modify a DTC cluster mapping
```
PS C:\> Set-DtcClusterTMMapping -ExecutablePath "C:\TestApp\SampleApp.exe" -Name "LocalTestAppMapping" -ClusterResourceName "DtcResource2"
```

This command modifies an existing DTC cluster TM mapping.

## PARAMETERS

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

### -ClusterResourceName
Specifies the name of a cluster DTC resource.
This cmdlet sets the TM mapping of the resource that the name specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComPlusAppId
Specifies the COM+ application identifier to associate with this mapping.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExecutablePath
Specifies the path of the application to associate with this mapping.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local
Specifies whether the application type is local.
If you specify a value of $False, the application is a clustered resource.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the DTC mapping to add.

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

### -Service
Specifies the name of the Windows service to associate with this mapping.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5
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

## INPUTS

## OUTPUTS

### DtcClusterTMMapping

## NOTES
* This cmdlet returns a **DtcClusterTMMapping** object that contains modified mapping information.

## RELATED LINKS

[Add-DtcClusterTMMapping](./Add-DtcClusterTMMapping.md)

[Get-DtcClusterTMMapping](./Get-DtcClusterTMMapping.md)

[Remove-DtcClusterTMMapping](./Remove-DtcClusterTMMapping.md)

