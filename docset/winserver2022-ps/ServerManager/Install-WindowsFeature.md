---
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: ServerManager
online version:
schema: 2.0.0
---

# Install-WindowsFeature

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ComponentNamesAndRunningComputer (Default)
```
Install-WindowsFeature [-Name] <Feature[]> [-Restart] [-IncludeAllSubFeature] [-IncludeManagementTools]
 [-Source <String[]>] [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ComponentNamesAndVhdPath
```
Install-WindowsFeature [-Name] <Feature[]> -Vhd <String> [-IncludeAllSubFeature] [-IncludeManagementTools]
 [-Source <String[]>] [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ConfigurationFile
```
Install-WindowsFeature -ConfigurationFilePath <String> [-Vhd <String>] [-Restart] [-Source <String[]>]
 [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf] [-Confirm]
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

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationFilePath
{{ Fill ConfigurationFilePath Description }}

```yaml
Type: String
Parameter Sets: ConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllSubFeature
{{ Fill IncludeAllSubFeature Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeManagementTools
{{ Fill IncludeManagementTools Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
{{ Fill LogPath Description }}

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
{{ Fill Name Description }}

```yaml
Type: Feature[]
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Restart
{{ Fill Restart Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ConfigurationFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
{{ Fill Source Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vhd
{{ Fill Vhd Description }}

```yaml
Type: String
Parameter Sets: ComponentNamesAndVhdPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ConfigurationFile
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
Type: SwitchParameter
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

### Microsoft.Windows.ServerManager.Commands.Feature[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
