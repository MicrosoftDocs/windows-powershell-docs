---
external help file: Microsoft.Windows.Bcd.Cmdlets.dll-Help.xml
Module Name: Microsoft.Windows.Bcd.Cmdlets
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.bcd.cmdlets/set-bcddebugsettings?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BcdDebugSettings
---

# Set-BcdDebugSettings

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### SerialWithDebugPort
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] [-Baudrate <Int64>] -DebugPort <Int64> [-Serial]
 [-StartPolicy <StartPolicy>] [-NoUserModeExceptions] [-Force] [<CommonParameters>]
```

### SerialWithOutDebugPort
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] [-Serial] [-StartPolicy <StartPolicy>] [-NoUserModeExceptions]
 [-Force] [<CommonParameters>]
```

### NETWithKey
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] -Port <Int64> -HostIp <String> [-Net] -Key <String> [-NoDhcp]
 [-StartPolicy <StartPolicy>] [-NoUserModeExceptions] [-Force] [<CommonParameters>]
```

### NETCreateKey
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] -Port <Int64> -HostIp <String> [-Net] [-NewKey] [-NoDhcp]
 [-StartPolicy <StartPolicy>] [-NoUserModeExceptions] [-Force] [<CommonParameters>]
```

### 1394
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] -Channel <Int64> [-Ieee1394] [-StartPolicy <StartPolicy>]
 [-NoUserModeExceptions] [-Force] [<CommonParameters>]
```

### Usb
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] [-Usb] [-TargetName <String>] [-StartPolicy <StartPolicy>]
 [-NoUserModeExceptions] [-Force] [<CommonParameters>]
```

### Local
```
Set-BcdDebugSettings [[-Store] <BcdStoreInfo>] [-Local] [-StartPolicy <StartPolicy>] [-NoUserModeExceptions]
 [-Force] [<CommonParameters>]
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

Required: True
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
Parameter Sets: NETWithKey, NETCreateKey
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

### -Key
{{ Fill Key Description }}

```yaml
Type: System.String
Parameter Sets: NETWithKey
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local
{{ Fill Local Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Local
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
Parameter Sets: NETWithKey, NETCreateKey
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewKey
{{ Fill NewKey Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NETCreateKey
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDhcp
{{ Fill NoDhcp Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NETWithKey, NETCreateKey
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoUserModeExceptions
{{ Fill NoUserModeExceptions Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoUmex

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
{{ Fill Port Description }}

```yaml
Type: System.Int64
Parameter Sets: NETWithKey, NETCreateKey
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

### -StartPolicy
{{ Fill StartPolicy Description }}

```yaml
Type: Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.StartPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Active, AutoEnable, Disable

Required: False
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

### -TargetName
{{ Fill TargetName Description }}

```yaml
Type: System.String
Parameter Sets: Usb
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usb
{{ Fill Usb Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Usb
Aliases:

Required: True
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
