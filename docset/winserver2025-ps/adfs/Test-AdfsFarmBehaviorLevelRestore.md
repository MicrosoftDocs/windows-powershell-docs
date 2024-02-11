---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/test-adfsfarmbehaviorlevelrestore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-AdfsFarmBehaviorLevelRestore
---

# Test-AdfsFarmBehaviorLevelRestore

## SYNOPSIS
Tests whether you can restore an AD FS farm to a previous behavior level.

## SYNTAX

```
Test-AdfsFarmBehaviorLevelRestore [-Member <String[]>] [-Credential <PSCredential>] -FarmBehavior <Int32>
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Test-AdfsFarmBehaviorLevelRestore** cmdlet tests whether the **Restore-AdfsFarmBehaviorLevel** cmdlet can restore an Active Directory Federation Services (AD FS) farm to a previous behavior level.

## EXAMPLES

## PARAMETERS

### -Credential
Specifies credentials necessary to run this cmdlet for an AD FS farm that uses SQL Server as the policy database.
The credentials provided must be an administrator on each AD FS server.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FarmBehavior
Specifies the farm behavior.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -Member
Specifies an array of members.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Invoke-AdfsFarmBehaviorLevelRaise](./Invoke-AdfsFarmBehaviorLevelRaise.md)

[Restore-AdfsFarmBehaviorLevel](./Restore-AdfsFarmBehaviorLevel.md)

[Test-AdfsFarmBehaviorLevelRaise](./Test-AdfsFarmBehaviorLevelRaise.md)

