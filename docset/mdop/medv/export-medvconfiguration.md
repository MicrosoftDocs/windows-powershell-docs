---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
external help file: Microsoft.Medv.Administration.Commands.Configuration.dll-Help.xml
online version: 
schema: 2.0.0
title: Export-MedvConfiguration
ms.reviewer:
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro 
ms.date: 12/05/2016
ms.topic: reference
ms.devlang: powershell
ms.assetid: 23E84610-D01D-4E48-9DE3-D2FE3B4E45BD
---

# Export-MedvConfiguration

## SYNOPSIS
Exports a MED-V configuration object to a registry file.

## SYNTAX

```
Export-MedvConfiguration [-Path] <String> [-Append [<SwitchParameter>]] [-Force [<SwitchParameter>]] [-NoClobber [<SwitchParameter>]] [-PassThru [<SwitchParameter>]] -InputObject <MedvConfiguration> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]] [<CommonParameters>]
```

## DESCRIPTION
The **Export-MedvConfiguration** cmdlet exports a **MedvConfiguration** object to a file that has a .reg file name extension.
These registry settings changes will be made to the HKLM hive.

## EXAMPLES

### Example 1: Export new object to a file
```
C:\PS>New-MedvConfiguration -UxLogonStartEnabled $True -CloseActionMode HIBERNATE | Export-MedvConfiguration -Path "c:\temp\medvsettings.reg"
```

This command uses the **New-MedvConfiguration** cmdlet to create a **MedvConfiguration** object, and then passes that object to the current cmdlet by using the pipeline operator.
That cmdlet saves the object as a .reg file.

### Example 2: Export an object that contains redirection URLs
```
C:\PS>New-MedvConfiguration -RedirectUrls "http://webapp1/contoso.com","http://webapp2/contoso.com" | Export-MedvConfiguration -Path "c:\temp\redirUrls.reg"
```

This command creates a **MedvConfiguration** object that contains redirection URLs for the browser in the guest virtual machine.
The command exports the configuration object to a file.

## PARAMETERS

### -Append
Indicates that this cmdlet appends the settings in the **MedvConfiguration** object to an existing registry file.
The existing registry file must contain a registry file header.
If you specify this parameter but the specified registry file does not exist, the cmdlet creates a new registry file.

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

### -Force
Indicates that this cmdlet attempts to clear the read-only attribute of the output file, if necessary.
The cmdlet attempts to reset the read-only attribute after the command has run.

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

### -InputObject
Specifies a **MedvConfiguration** object to export to a registry file.

```yaml
Type: MedvConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoClobber
Indicates that this cmdlet does not overwrite an existing file.
By default, if a file exists in the specified path, this cmdlet overwrites that file without warning.

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

### -PassThru
Indicates that this cmdlet returns a **FileInfo** object for the registry file.
By default, this cmdlet does not return any object.

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

### -Path
Specifies the path of a file that receives the registry settings.
You must have permission to write in the specified location.
If you specify a file that already exists, the cmdlet overwrites that file without warning.
To prevent overwriting, specify the *NoClobber* parameter.
To append to an existing file, specify the *Append* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Medv.Administration.Commands.MedvConfiguration
This cmdlet accepts a **MedvConfiguration** object.
A **MedvConfiguration** object contains MED-V settings to set for a particular scope.

## OUTPUTS

### FileInfo
This cmdlet generates **FileInfo** object.

## NOTES

## RELATED LINKS

[New-MedvConfiguration](./New-MedvConfiguration.md)


