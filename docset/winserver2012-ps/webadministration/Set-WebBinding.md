---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/set-webbinding?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WebBinding

## SYNOPSIS
Changes a property of an IIS site binding.

## SYNTAX

### InputBindingProperties (Default)
```
Set-WebBinding [[-Name] <String>] [[-IPAddress] <String>] [[-Port] <UInt32>] [-HostHeader <String>]
 -PropertyName <String> -Value <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputBindingInformation
```
Set-WebBinding [[-Name] <String>] [-BindingInformation] <String> -PropertyName <String> -Value <String>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Changes a property of an existing IIS site binding.

## EXAMPLES

### -------------- EXAMPLE 1: Changing a Web site binding property --------------
```
IIS:\>Set-WebBinding -Name 'Default Web Site' -BindingInformation "*:80:" -PropertyName Port -Value 1234
```

Changes the setting for the Port property for the Default Web Site from 80 to 1234.

## PARAMETERS

### -BindingInformation
A Binding Information object.

```yaml
Type: String
Parameter Sets: InputBindingInformation
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostHeader
The Host header of the binding.

```yaml
Type: String
Parameter Sets: InputBindingProperties
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
The IP address of the site binding to change.

```yaml
Type: String
Parameter Sets: InputBindingProperties
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The name of the site for which the binding property is changed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
The port of the site binding to change.

```yaml
Type: UInt32
Parameter Sets: InputBindingProperties
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PropertyName
The property name of the binding property to change.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
The value of the binding property.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

