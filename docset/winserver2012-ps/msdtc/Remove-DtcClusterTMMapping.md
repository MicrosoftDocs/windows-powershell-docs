---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/remove-dtcclustertmmapping?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DtcClusterTMMapping

## SYNOPSIS
Removes a cluster DTC mapping.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-All] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DtcClusterTMMapping [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -Name <String> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Remove-DtcClusterTMMapping** cmdlet removes a cluster Distributed Transaction Coordinator (DTC) mapping.
This cmdlet is supported on clustered computers only.

## EXAMPLES

### Example 1: Remove a local mapping
```
PS C:\> Remove-DtcClusterTMMapping -Name "LocalTestAppMapping" 
Confirm

Are you sure you want to perform this action? 

Removing Tm Mapping will result in the application using default Dtc as its transactions coordinator. 

[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Yes
```

This command removes a local **DtcClusterTMMapping** object.

## PARAMETERS

### -All
Indicates that this cmdlet deletes all TM mappings.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Name
Specifies the mapping name of the TM mapping to delete.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-DtcClusterTMMapping](./Add-DtcClusterTMMapping.md)

[Get-DtcClusterTMMapping](./Get-DtcClusterTMMapping.md)

[Set-DtcClusterTMMapping](./Set-DtcClusterTMMapping.md)

