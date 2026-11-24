---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/test-adfsfarmbehaviorlevelraise?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-AdfsFarmBehaviorLevelRaise
---

# Test-AdfsFarmBehaviorLevelRaise

## SYNOPSIS
Tests whether you can raise the behavior level of a farm.

## SYNTAX

### AdfsUpgradeServiceAccount (Default)
```
Test-AdfsFarmBehaviorLevelRaise [-Member <String[]>] [-Credential <PSCredential>]
 [-ServiceAccountCredential <PSCredential>] [-Force] [<CommonParameters>]
```

### AdfsUpgradeGmsaAccount
```
Test-AdfsFarmBehaviorLevelRaise [-Member <String[]>] [-Credential <PSCredential>]
 [-GroupServiceAccountIdentifier <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Test-AdfsFarmBehaviorLevelRaise** cmdlet tests whether the **Invoke-AdfsFarmBehaviorLevelRaise** cmdlet can raise the behavior level of an Active Directory Federation Services (AD FS) farm to enable the new features that are available in later versions of the Windows operating system.

To test raising the behavior level of a farm that uses SQL Server as the policy database, specify the *Credential* parameter.

## EXAMPLES

### Example 1: Test raising the farm behavior level
```
PS C:\> Test-AdfsFarmBehaviorLevelRaise
```

This command tests whether you can raise the farm behavior level.

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

### -GroupServiceAccountIdentifier
Specifies the ID of a group Managed Service Account.

```yaml
Type: String
Parameter Sets: AdfsUpgradeGmsaAccount
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

### -ServiceAccountCredential
Specifies credentials for a service account.

```yaml
Type: PSCredential
Parameter Sets: AdfsUpgradeServiceAccount
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

[Test-AdfsFarmBehaviorLevelRestore](./Test-AdfsFarmBehaviorLevelRestore.md)

