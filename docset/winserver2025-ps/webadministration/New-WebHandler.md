---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webhandler?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebHandler
---

# New-WebHandler

## SYNOPSIS
Creates an IIS request handler.

## SYNTAX

```
New-WebHandler [-Name] <String> -Path <String> -Verb <String> [-Type <String>] [-Modules <String>]
 [-ScriptProcessor <String>] [-Precondition <String>] [-ResourceType <String>] [-RequiredAccess <String>]
 [-Force] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebHandler** cmdlet creates an Internet Information Services (IIS) request handler.

## EXAMPLES

### Example 1: Add a new handler
```
IIS:\> New-WebHandler -Name "TestHandler" -Path "*.test" -Verb "GET,POST" -Modules "IsapiModule" -PSPath "IIS:\sites\Default Web Site"
```

This command adds a handler named TestHandler to the default website.

## PARAMETERS

### -Force
Forces the creation of the new handler.

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

### -Location
Specifies the configuration location in which the handler is configured.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Modules
Specifies the modules used for the handler.

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

### -Name
Specifies the name of the new request handler.

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

### -PSPath
Specifies an IIS configuration path.

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

### -Path
Specifies the physical path to the handler.
This parameter applies to native modules only.

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

### -Precondition
Specifies preconditions for the new handler.

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

### -RequiredAccess
Specifies the user rights that are required for the new handler.
The acceptable values for this parameter are:

- Read
- Write
- Execute
- Script

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: None, Read, Write, Script, Execute

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Specifies the resource type this handler runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: File, Directory, Either, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScriptProcessor
Specifies the script processor that runs for the module.

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

### -Type
Specifies the managed type of the new module.
This parameter applies to managed modules only.

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

### -Verb
Specifies the HTTP verbs that are handled by the new handler.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebHandler](./Get-WebHandler.md)

[Remove-WebHandler](./Remove-WebHandler.md)

[Set-WebHandler](./Set-WebHandler.md)

