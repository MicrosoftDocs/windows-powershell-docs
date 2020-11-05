---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 7BC49A0B-D4DE-4351-8FC8-FB93946E98E4
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-WebVirtualDirectory

## SYNOPSIS
Creates a new virtual directory in IIS.

## SYNTAX

```
New-WebVirtualDirectory [-Site <String>] [-Application <String>] [-Name] <String> [-PhysicalPath <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
Creates a new virtual directory in IIS.

## EXAMPLES

### -------------- EXAMPLE 1: Creating a Virtual Directory --------------
```
IIS:\>New-WebVirtualDirectory -Site "Default Web Site" -Name ContosoVDir -PhysicalPath c:\inetpub\contoso
```

The example creates a new virtual directory named "ContosoVDir" on the Default Web Site.

## PARAMETERS

### -Application
The application under which the virtual directory is created.

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

### -Force
Specifies that the user is not prompted for confirmation.

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

### -Name
The name of the virtual directory to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalPath
The physical path to the folder in which the new virtual directory is created.
The specified folder must already exist.

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

### -Site
The site name under which the virtual directory is created.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

