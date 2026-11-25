---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/get-smscutoverstages?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmsCutoverStages
---

# Get-SmsCutoverStages

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Get-SmsCutoverStages [-ComputerName <String>] [-Type <EndpointType>] [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Type
{{ Fill Type Description }}

```yaml
Type: Microsoft.StorageMigration.Service.Contracts.EndpointType
Parameter Sets: (All)
Aliases: EPT
Accepted values: None, Smb, Nfs, RawBlock, iSCSI, NDMP, RootVolume, MountedVolume, DFSN, DFSR, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
