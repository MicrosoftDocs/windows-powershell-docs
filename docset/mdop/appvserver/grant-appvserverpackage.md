---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Grant-AppvServerPackage
---

# Grant-AppvServerPackage

## SYNOPSIS
Grants an entitlement to a package.

## SYNTAX

### ByObject
```
Grant-AppvServerPackage [-AppvServerPackage] <PackageVersion> [-Groups] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### By GUID
```
Grant-AppvServerPackage [-Groups] <String[]> [-PackageID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByName
```
Grant-AppvServerPackage [-Groups] <String[]> [-Name] <String> [[-Version] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Grant-AppvServerPackage** cmdlet grants an Active Directory entitlement to an existing package.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AppvServerPackage
Specifies an array of **AppVServerPackage** objects.

```yaml
Type: PackageVersion
Parameter Sets: ByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Groups
Specifies an array of names of Active Directory groups.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the package given when the package was created.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PackageID
Specifies a GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the Microsoft Application Virtualization (App-V) sequencer.
The package GUID is shared by all versions of a specific package.

```yaml
Type: Guid
Parameter Sets: By GUID
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Version
Specifies the version of an App-V package in one specific lineage.
If you do not specify a version, the cmdlet acts on all versions saved on computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VersionID
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

```yaml
Type: Guid
Parameter Sets: By GUID
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

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
The cmdlet is not run.Shows what would happen if the cmdlet runs.
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

### AppvServer.AppvServerPackage

## OUTPUTS

## NOTES
* If the cmdlet cannot find the specified package, the cmdlet returns the following error: The specified package could not be found on the system. The cmdlet fails the operation.
* If you specify an invalid group, the cmdlet return the following error: The provided entitlements are not valid. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet takes action on all available versions of the package.
* If the *Groups* parameter is set to $Null, this cmdlet ignores the *Confirm* parameter. Specify the *Force* parameter to perform the action without confirming.

  The release documented in KB 3139245 implements this change.
It applies to subsequent releases of Microsoft Application Virtualization 5.1.
For more information, see Hotfix Package 2 for Microsoft Application Virtualization 5.1 and Hotfix Package 3 for Microsoft Application Virtualization 5.0 SP3https://support.microsoft.com/en-us/kb/3139245 (https://support.microsoft.com/kb/3139245) in the Microsoft Support Library.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Import-AppvServerPackage](./Import-AppvServerPackage.md)

[Publish-AppvServerPackage](./Publish-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Set-AppvServerPackage](./Set-AppvServerPackage.md)

[Unpublish-AppvServerPackage](./Unpublish-AppvServerPackage.md)


