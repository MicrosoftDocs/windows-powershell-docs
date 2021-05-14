---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Test-MbamCMIntegration
---

# Test-MbamCMIntegration

## SYNOPSIS
Checks server prerequisites and validates parameters.

## SYNTAX

### ParameterSetCMReportsOnly
```
Test-MbamCMIntegration [-Detailed] [-SsrsServer <String>] [-SsrsInstance <String>] [-ReportsOnly]
 -ReportsCollectionID <String> -BitLockerProtectionBaselineLogicalName <String>
 -OperatingSystemDriveConfigurationItemLogicalName <String>
 -FixedDataDriveConfigurationItemLogicalName <String> [<CommonParameters>]
```

### ParameterSetDefault
```
Test-MbamCMIntegration [-Detailed] [-SsrsServer <String>] [-SsrsInstance <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-MbamCMIntegration** cmdlet checks the server prerequisites and validates the parameters for the Microsoft BitLocker Administration and Monitoring (MBAM) Microsoft Endpoint Configuration Manager Integration feature.

## EXAMPLES

### Example 1: Check prerequisites to enable integration
```
PS C:\> Test-MbamCMIntegration
```

This command tests the prerequisites for enabling the MBAM Microsoft Endpoint Configuration Manager Integration on the local Configuration Manager server.
The MBAM reports are deployed on the default SQL Server Reporting Services instance, MSSQLSERVER.

### Example 2: Check prerequisites to enable integration with detailed output
```
PS C:\> Test-MbamCMIntegration -Detailed


ID             Type  Message
--             ----  -------
CmInstallation Error This feature can be installed only on a server that is running Microsoft Endpoint Configuration Manager.
```

This command checks the prerequisites to enable the MBAM Microsoft Endpoint Configuration Manager Integration feature on the local Configuration Manager server with detailed output.

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

### -Detailed
Indicates that the cmdlet displays detailed information about the prerequisite check and parameter validation failures.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### bool

## NOTES

## RELATED LINKS

[Disable-MbamCMIntegration](disable-mbamcmintegration.md)

[Enable-MbamCMIntegration](enable-mbamcmintegration.md)

[Get-MbamCMIntegration](get-mbamcmintegration.md)


