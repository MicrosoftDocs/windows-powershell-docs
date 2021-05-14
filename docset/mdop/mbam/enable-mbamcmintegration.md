---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Enable-MbamCMIntegration
---

# Enable-MbamCMIntegration

## SYNOPSIS
Enables the MBAM Microsoft Endpoint Configuration Manager Integration feature.

## SYNTAX

### ParameterSetCMReportsOnly
```
Enable-MbamCMIntegration [-SkipValidation] [-SsrsServer <String>] [-SsrsInstance <String>] [-ReportsOnly]
 -ReportsCollectionID <String> -BitLockerProtectionBaselineLogicalName <String>
 -OperatingSystemDriveConfigurationItemLogicalName <String>
 -FixedDataDriveConfigurationItemLogicalName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetDefault
```
Enable-MbamCMIntegration [-SkipValidation] [-SsrsServer <String>] [-SsrsInstance <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MbamCMIntegration** cmdlet enables the Microsoft BitLocker Administration and Monitoring (MBAM) Microsoft Endpoint Configuration Manager Integration feature.
This feature integrates Configuration Manager with MBAM, and moves the compliance and reporting infrastructure into the Configuration Manager environment.

## EXAMPLES

### Example 1: Enable the Integration feature
```
PS C:\> Enable-MbamCMIntegration
```

This command enables the MBAM Microsoft Endpoint Configuration Manager Integration feature on the local Configuration Manager server.
The MBAM reports are deployed on the default SQL Server Reporting Services instance, MSSQLSERVER.

## PARAMETERS

### -BitLockerProtectionBaselineLogicalName
Specifies the logical name of the BitLocker protection baseline.

```yaml
Type: String
Parameter Sets: ParameterSetCMReportsOnly
Aliases: BaselineLogicalName

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FixedDataDriveConfigurationItemLogicalName
Specifies the logical name of the fixed data drive configuration item.

```yaml
Type: String
Parameter Sets: ParameterSetCMReportsOnly
Aliases: FDDLogicalName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperatingSystemDriveConfigurationItemLogicalName
Specifies the logical name of the operating system drive configuration item.

```yaml
Type: String
Parameter Sets: ParameterSetCMReportsOnly
Aliases: OSDLogicalName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportsCollectionID
Specifies an existing collection ID.
This ID is used by the reports to set the default collection for which the reports display compliance data.

```yaml
Type: String
Parameter Sets: ParameterSetCMReportsOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportsOnly
Indicates that only the Configuration Manager reports are deployed.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetCMReportsOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipValidation
Indicates that this cmdlet bypasses validation of parameter values.
If you specify this parameter, the feature may not function properly after you enable it.

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

### -SsrsInstance
Specifies the SQL Server Reporting Services instance.
This instance hosts the Configuration Manager reports.
This parameter is ignored if the server has Configuration Manager installed.

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

### -SsrsServer
Specifies the server with the SQL Server Reporting Services point role.
This server hosts the Configuration Manager reports.
If you do not specify a server, the Configuration Manager reports are deployed to the local server.

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-MbamCMIntegration](disable-mbamcmintegration.md)

[Get-MbamCMIntegration](get-mbamcmintegration.md)

[Test-MbamCMIntegration](test-mbamcmintegration.md)


