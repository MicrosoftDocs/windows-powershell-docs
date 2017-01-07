---
author: brianlic-msft
description: 
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-AdfsFarmBehaviorLevelRestore
ms.assetid: B2B0D2DB-24E7-4B87-80F1-FF36097ADB13
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
The **Test-AdfsFarmBehaviorLevelRestore** cmdlet tests whether the Restore-AdfsFarmBehaviorLevel cmdlet can restore an Active Directory Federation Services (AD FS) farm to a previous behavior level.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Credential
Specifies credentials necessary to run this cmdlet for an AD FS farm that uses SQL Server as the policy database.
The credentials provided must be an administrator on each AD FS server.
To obtain a **PSCredential** object, use the Get-Credential cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Invoke-AdfsFarmBehaviorLevelRaise](./Invoke-AdfsFarmBehaviorLevelRaise.md)

[Restore-AdfsFarmBehaviorLevel](./Restore-AdfsFarmBehaviorLevel.md)

[Test-AdfsFarmBehaviorLevelRaise](./Test-AdfsFarmBehaviorLevelRaise.md)

