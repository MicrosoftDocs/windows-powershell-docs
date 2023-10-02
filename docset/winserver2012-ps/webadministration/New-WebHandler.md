---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webhandler?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WebHandler

## SYNOPSIS
Creates a new IIS request handler.

## SYNTAX

```
New-WebHandler [-Name] <String> -Path <String> -Verb <String> [-Type <String>] [-Modules <String>]
 [-ScriptProcessor <String>] [-Precondition <String>] [-ResourceType <String>] [-RequiredAccess <String>]
 [-Force] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Creates a new IIS request handler.

## EXAMPLES

### -------------- EXAMPLE 1: Add a new handler --------------
```
IIS:\>New-WebHandler -Name testHandler -Path *.test -Verb 'GET,POST' -Modules IsapiModule -PSPath "IIS:\sites\Default Web Site"
```

Adds a handler named "testHandler" to the Default Web Site.

## PARAMETERS

### -Force
Forces creation of the new handler.

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
Configuration location in which the handler is configured.

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
Modules used for the handler.

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
The name of the new request handler.

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

### -Path
The physical path to the handler (native modules only).

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
Specifies any preconditions that are used for the new handler.

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
The user rights that are required for the new handler: Read, Write, Execute, or Script.

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
The resource type this handler executes.

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
The script processor that executes for the module.

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
The managed type of the new module (managed modules only).

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
The HTTP verbs handled by the new handler.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

