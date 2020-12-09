---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: DAB869BC-1192-4261-81FA-8EFB92367EC5
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-WebBinding

## SYNOPSIS
Removes a binding from an IIS Web site.

## SYNTAX

### InputBindingProperties (Default)
```
Remove-WebBinding [-Protocol <String>] [-Name <String>] [-IPAddress <String>] [-Port <String>]
 [-HostHeader <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-WebBinding -InputObject <PSObject> [-Protocol <String>] [-Name <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputBindingInformation
```
Remove-WebBinding [-Protocol <String>] [-Name <String>] -BindingInformation <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes a binding from an IIS Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Adding and removing a site binding --------------
```
IIS:\>New-WebBinding -Name "Default Web Site" -Port 1234 -IPAddress * -HostHeader "testsite" "Sleep 5 seconds before removing the binding"; Sleep 5 Get-WebBinding -Port 1234 -Name "Default Web Site" | Remove-WebBinding
```

The example demonstrates how to create a new binding, and then remove that binding after waiting 5 seconds.
Piping is used to remove the site binding returned by theGet-WebBindingcmdlet.

## PARAMETERS

### -BindingInformation
ABindingInformationobject.

```yaml
Type: String
Parameter Sets: InputBindingInformation
Aliases: 

Required: True
Position: Named
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
The host header of the site binding that is to be removed.

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
The IP address of the site from which the binding is removed.
The use of globbing (*) is supported to specify all IP addresses.

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

### -InputObject
Specifies an object that contains site binding information.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The name of the site from which the binding is removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
The port used by the binding that is to be removed.

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

### -Protocol
The protocol of the binding to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

