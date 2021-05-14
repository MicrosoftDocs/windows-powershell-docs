---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/add-dtcclustertmmapping?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DtcClusterTMMapping

## SYNOPSIS
Adds a cluster DTC mapping.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DtcClusterTMMapping [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -ClusterResourceName <String> -Local <Boolean> -Name <String> -Service <String>
```

### UNNAMED_PARAMETER_SET_2
```
Add-DtcClusterTMMapping [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -ClusterResourceName <String> -ExecutablePath <String> -Local <Boolean> -Name <String>
```

### UNNAMED_PARAMETER_SET_3
```
Add-DtcClusterTMMapping [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -ClusterResourceName <String> -ComPlusAppId <String> -Local <Boolean> -Name <String>
```

## DESCRIPTION
The **Add-DtcClusterTMMapping** cmdlet adds a cluster Distributed Transaction Coordinator (DTC) mapping.
This cmdlet is supported on clustered computers only.

## EXAMPLES

### Example 1: Create a cluster mapping
```
PS C:\> Add-DtcClusterTMMapping -ClusterResourceName "DtcResource1" -ExecutablePath "C:\TestApp\App.exe" -Local $False -Name "LocalTestAppMapping"
```

This command creates a DTC cluster Transaction Manager (TM) mapping.

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
This cmdlet associates this mapping with the resource that the name specifies.

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
If the application type is local, the application maps to the Local DTC instance and the cmdlet ignores the value of the **ClusterResourceName** parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Service
Specifies the name of the Windows service to associate with this mapping.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

## NOTES

## RELATED LINKS

[Get-DtcClusterTMMapping](./Get-DtcClusterTMMapping.md)

[Remove-DtcClusterTMMapping](./Remove-DtcClusterTMMapping.md)

[Set-DtcClusterTMMapping](./Set-DtcClusterTMMapping.md)

