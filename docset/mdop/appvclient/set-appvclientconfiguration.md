---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 0CBA3CDF-C735-442E-969E-34C7C593592C
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AppvClientConfiguration
---

# Set-AppvClientConfiguration

## SYNOPSIS
Applies configuration settings to the App-V Client.

## SYNTAX

```
Set-AppvClientConfiguration [-AllowHighCostLaunch <Boolean>] [-AutoLoad <UInt32>]
 [-CertFilterForClientSsl <String>] [-EnablePackageScripts <Boolean>] [-EnablePublishingRefreshUI <Boolean>]
 [-IntegrationRootGlobal <String>] [-IntegrationRootUser <String>] [-LocationProvider <String>]
 [-MigrationMode <Boolean>] [-PackageInstallationRoot <String>] [-PackageSourceRoot <String>]
 [-RequirePublishAsAdmin <Boolean>] [-ReestablishmentInterval <UInt32>] [-ReestablishmentRetries <UInt32>]
 [-ReportingDataBlockSize <UInt32>] [-ReportingDataCacheLimit <UInt32>] [-ReportingEnabled <Boolean>]
 [-ReportingInterval <UInt32>] [-ReportingRandomDelay <UInt32>] [-ReportingServerURL <String>]
 [-ReportingStartTime <UInt32>] [-RoamingFileExclusions <String>] [-RoamingRegistryExclusions <String>]
 [-SharedContentStoreMode <Boolean>] [-VerifyCertificateRevocationList <Boolean>]
 [-ExperienceImprovementOptIn <Boolean>] [-ProcessesUsingVirtualComponents <String[]>]
 [-EnableDynamicVirtualization <Boolean>] [-IgnoreLocationProvider <Boolean>] [-SupportBranchCache <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvClientConfiguration** cmdlet applies configuration settings to the Microsoft Application Virtualization (App-V) client.
Each parameter represents a setting that can be changed.

## EXAMPLES

### Example 1: Set a client configuration parameter
```
PS C:\> Set-AppvClientConfiguration -parameter1 "parameterVal1"
```

This schematic example sets a particular client configuration parameter.

## PARAMETERS

### -AllowHighCostLaunch
Specifies whether virtualized applications are launched on Windows 8 computers connected via a metered network connection (e.g.
4G).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoLoad
Specifies how new packages should be loaded automatically by App-V on a specific computer.
Valid values are: 

- 0 for None 
- 1 for Previously used
- 2 for All

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertFilterForClientSsl
Specifies the path to a valid certificate in the certificate store.

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

### -EnableDynamicVirtualization
Specifies whether to enable dynamic virtualization.
Dynamic virtualization allows supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and work with virtual applications.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePackageScripts
Specifies whether to enable the ability for scripts defined in the package manifest of configuration files to run.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePublishingRefreshUI
Specifies whether to enable the publishing refresh progress bar for the Client.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExperienceImprovementOptIn
Specifies whether to opt in ($True) or opt out ($False) of the Customer Experience Improvement Program.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLocationProvider
Specifies whether to force the client to ignore the Location Provider path and instead use the Package Source Root.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntegrationRootGlobal
Specifies the location to create symbolic links associated with the current version of a globally published package.
All virtual application extensions, for example shortcuts and file type associations, will point to this path.
If you do not specify a path, symbolic links will not be used when you publish the package.
For example: %allusersprofile%\Microsoft\AppV\Client\Integration.

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

### -IntegrationRootUser
Specifies the location to create symbolic links associated with the current version of a per-user published package.
All virtual application extensions, for example shortcuts and file type associations, will point to this path.
If you do not specify a path, symbolic links will not be used when you publish the package.
For example: %localappdata%\Microsoft\AppV\Client\Integration.

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

### -LocationProvider
Specifies the class ID (CLSID) for a compatible implementation of the IAppvPackageLocationProvider interface.

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

### -MigrationMode
Specifies whether to use migration mode.
Migration mode allows the App-V client to control shortcuts and FTAs for packages published using a previous version of App-V .

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageInstallationRoot
Specifies directory where all new applications and updates are installed.

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

### -PackageSourceRoot
Specifies a value that overrides source location for downloading package content.

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

### -ProcessesUsingVirtualComponents
Specifies a list of process paths which are candidates for using dynamic virtualization of supported shell extensions, browser helper objects, and ActiveX controls.
This parameter may contain wildcards.
Only processes whose full path matches one of these items can use dynamic virtualization.

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

### -ReestablishmentInterval
Specifies the number of seconds between attempts to reestablish a dropped session.
Valid values are: between 0 and 3600.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReestablishmentRetries
Specifies the number of times to retry a dropped session.
Valid values are: between 0 and 99.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingDataBlockSize
Specifies the maximum size in bytes to transmit to the server for reporting upload requests.
This can help avoid permanent transmission failures when the log has reached a significant size.
Valid values are: between 1024 and unlimited.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingDataCacheLimit
Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.
The size applies to the cache in memory.
When the limit is reached, the log file will roll over.
Valid values are: between 0 and 1024.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingEnabled
Specifies whether to enable the client to return information to a reporting server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingInterval
Specifies the retry interval that the client uses to resend data to the reporting server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingRandomDelay
Specifies the maximum delay, in minutes, for data to be sent to the reporting server. 
When the scheduled task is started, the client generates a random delay between 0 and *ReportingRandomDelay* and waits the specified duration before sending data.
This can help to prevent collisions on the server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingServerURL
Specifies the location on the reporting server where client information is saved.

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

### -ReportingStartTime
Specifies the time to initiate the client to send data to the reporting server.
Valid values are: integers between 0-23 corresponding to the hour of the day.
By default, the *ReportingStartTime* starts on the current day at 10 P.M or 22.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequirePublishAsAdmin
(Applicable starting in App-V 5.0 SP3.) Specifies whether an unelevated user can publish registered App-V packages.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoamingFileExclusions
Specifies the file paths relative to %userprofile% that do not roam with a user's profile.
Example usage: `-RoamingFileExclusions='desktop;my pictures'`.

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

### -RoamingRegistryExclusions
Specifies the registry paths that do not roam with a user profile.
Example usage: `-RoamingRegistryExclusions=software\\\\classes;software\\\\clients`.

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

### -SharedContentStoreMode
Specifies whether streamed package contents are not saved to the local hard disk.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportBranchCache
Specifies whether branch caching is turned on.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VerifyCertificateRevocationList
Specifies whether to verify Server certificate revocation status before steaming using HTTPS.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientConfiguration

## OUTPUTS

### Microsoft.AppvAgent.AppvClientConfiguration
The object is displayed as a two column table.
The first column contains the specific configuration and the second column contains the associated current value.

In the case where the name/value option is passed, the cmdlet returns the same two column table, but only for the configuration requested.

## NOTES
* Before applying new configuration, the cmdlet checks if Group Policy already owns any configuration by checking HKLM\Software\Policies\Microsoft\Application Virtualization. If any of the provided configuration is in the GP registry node, the cmdlet fail.s If GP does not own any of the supplied configuration, the settings are written to the HKLM\Software\Microsoft\AppV registry node. If the cmdlet is attempting to modify multiple settings, if any are owned by GP, the entire operation fails.
* In the case where GP owns the setting, the cmdlet returns the following error: The App-V configuration trying to be modified is being managed by Group Policy. The cmdlet cannot perform the modification. An error code is returned.
* If any of the provided configuration are not valid App-V Client settings, the cmdlet fails and returns an error.
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns an error.
* If the action to set a property fails, the cmdlet returns an error.

## RELATED LINKS

[Get-AppvClientConfiguration](./Get-AppvClientConfiguration.md)


