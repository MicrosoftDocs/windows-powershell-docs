---
external help file: Microsoft.Windows.Bcd.Cmdlets.dll-Help.xml
Module Name: Microsoft.Windows.Bcd.Cmdlets
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.bcd.cmdlets/set-bcdhypervisorsettings?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BcdHypervisorSettings
---

# Set-BcdHypervisorSettings

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### SerialWithDebugPort
```
Set-BcdHypervisorSettings [[-Store] <BcdStoreInfo>] [-Baudrate <Int64>] -DebugPort <Int64> [-Serial] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 1394
```
Set-BcdHypervisorSettings [[-Store] <BcdStoreInfo>] [-Channel <Int64>] [-Ieee1394] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NET
```
Set-BcdHypervisorSettings [[-Store] <BcdStoreInfo>] -HostIp <String> -Port <Int64> [-Net] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SerialWithOutDebugPort
```
Set-BcdHypervisorSettings [[-Store] <BcdStoreInfo>] [-Serial] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Baudrate
{{ Fill Baudrate Description }}

```yaml
Type: System.Int64
Parameter Sets: SerialWithDebugPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Channel
{{ Fill Channel Description }}

```yaml
Type: System.Int64
Parameter Sets: 1394
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugPort
{{ Fill DebugPort Description }}

```yaml
Type: System.Int64
Parameter Sets: SerialWithDebugPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostIp
{{ Fill HostIp Description }}

```yaml
Type: System.String
Parameter Sets: NET
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ieee1394
{{ Fill Ieee1394 Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: 1394
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Net
{{ Fill Net Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NET
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
{{ Fill Port Description }}

```yaml
Type: System.Int64
Parameter Sets: NET
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Serial
{{ Fill Serial Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SerialWithDebugPort, SerialWithOutDebugPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Store
{{ Fill Store Description }}

```yaml
Type: Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdStoreInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdStoreInfo

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
