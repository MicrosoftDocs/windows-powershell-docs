---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisconfigsection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISConfigSection
---

# Get-IISConfigSection

## SYNOPSIS
Gets a configuration section object to work further with the IIS Configuration Store.

## SYNTAX

```
Get-IISConfigSection [[-SectionPath] <String>] [[-CommitPath] <String>] [[-Location] <String>]
 [[-Clr] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISConfigSection** cmdlet gets a configuration section (Microsoft.Web.Administration.ConfigurationSection) object to work further with the Internet Information Services (IIS) Configuration Store.
It is generally the first cmdlet to use if configuration is to be read or updated.
The output of this cmdlet can be passed to other cmdlets in the pipeline where ConfigurationElement objects are expected, since ConfigurationSection inherits from ConfigurationElement.

If the *SectionPath* parameter is not used, the cmdlet lists all the available sections.
The sections that can be used are either defined in the applicationHost.config (IIS Configuration) or root web.config (.NET Framework).

## EXAMPLES

### Example 1: Get a configuration section object for a section path
```
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.applicationHost/sites"
```

This command gets the configuration section object for the system.applicationHost/sites section.

### Example 2: Get process state information for an IIS website
```
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.applicationHost/sites"
Get-IISConfigCollection $configSection | Get-IISConfigCollectionElement -ConfigAttribute @{"Name"="Default Web Site"} | Get-IISConfigAttributeValue -AttributeName "State"
```

This command gets runtime state information for the Default Web Site.

### Example 3: Add a new default document at the global configuration level
```
PS C:\> Get-IISConfigSection -SectionPath "system.webServer/defaultDocument" | Get-IISConfigCollection -CollectionName "files" | New-IISConfigCollectionElement  -ConfigAttribute @{"Value" = "MyDefDoc.htm"}
```

This command adds filename MyDefDoc.htm to the \<files\> collection of the \<defaultDocument\> section of the applicationHost.config file.

### Example 4: Create an application pool
```
PS C:\> Start-IISCommitDelay
PS C:\> $ConfigSectionCollection = Get-IISConfigSection -SectionPath "system.applicationHost/applicationPools" | Get-IISConfigCollection
PS C:\> New-IISConfigCollectionElement -ConfigCollection $configSectionCollection -ConfigAttribute @{"name"="MyNewSiteAppPool"; "autoStart"=$true; "managedPipelineMode"="Integrated" }
PS C:\> Stop-IISCommitDelay
```

This command creates an application pool and stores the result in variable $ConfigSectionCollection.

### Example 5: Create a collection element and specify the CLR version
```
PS C:\> $collection = Get-IISConfigSection -SectionPath "appSettings" -Clr 2.0
```

This command creates a new collection element using the *SectionPath* "appSettings"; that element is stored in a variable named $collection.
In addition, the *Clr* parameter is used to set the Common Language Runtime to version 2.0.

## PARAMETERS

### -Clr
Specifies the version of the root level .NET Framework Common Language Runtime (CLR) that IIS points to.
If this parameter is omitted then the default CLR version is used.
Note, however, that if the *CommitPath* parameter is included in the command the *Clr* parameter will be ignored and the runtime version of the corresponding application pool will be used instead.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CommitPath
Specifies the path where the configuration will be retrieved from.
If CommitPath is omitted, applicationHost.config or root .NET configuration (root web.config) will be used.

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

### -Location
Specifies the name of the IIS configuration location for which a configuration object is returned.
This corresponds to the \<location\> tag in configuration files.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SectionPath
Specifies the name of the IIS configuration section for which a configuration object is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISServerManager](./Get-IISServerManager.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

