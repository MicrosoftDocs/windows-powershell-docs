---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/remove-webconfigurationlocation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WebConfigurationLocation

## SYNOPSIS
Removes an IIS configuration location.

## SYNTAX

```
Remove-WebConfigurationLocation [[-Name] <String>] [-Recurse] [[-PSPath] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes an IIS configuration location.

## EXAMPLES

### -------------- EXAMPLE 1: Add and remove a configuration location --------------
```
IIS:\>Set-WebConfigurationProperty -PSPath "IIS:\" -Filter //windowsAuthentication -Location "Default Web Site/mypage.htm" -Name enabled -Value true Get-WebConfigurationLocation -Name "Default Web Site" -PSPath "IIS:\" "Sleep 5 seconds before removing the configuration location"; Sleep 5 Remove-WebConfigurationLocation -Name "Default Web Site/my*" Get-WebConfigurationLocation -Name "Default Web Site" -PSPath "IIS:\"
```

This example adds, and then removes, a configuration location.

## PARAMETERS

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

### -Name
The name of the configuration location that is to be removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
An IIS configuration path.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Recurse
When theRecurseparameter is used, it specifies that locations within the hierarchy of the specified location are also removed.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

