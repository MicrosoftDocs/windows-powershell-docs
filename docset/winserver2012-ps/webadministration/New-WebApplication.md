---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webapplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WebApplication

## SYNOPSIS
Creates a new IIS Web application.

## SYNTAX

```
New-WebApplication [-Site <String>] [-Name] <String> [-PhysicalPath <String>] [-ApplicationPool <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
Creates a new IIS Web application.

## EXAMPLES

### -------------- EXAMPLE 1: Creating a new web application --------------
```
IIS:\>New-WebApplication -Name testApp -Site 'Default Web Site' -PhysicalPath c:\test -ApplicationPool DefaultAppPool
```

This example creates a new Web application named testApp on the Default Web Site.
The application files are stored in the C:\Test folder, and the application runs in the DefaultAppPool application pool.

## PARAMETERS

### -ApplicationPool
The name of the application pool in which the new Web application executes.

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
Forces the creation of the application without prompting for user confirmation.

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
The name of the Web application to create.

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
The physical path to the Web application files.

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
The name of the site on which the application is created.

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

