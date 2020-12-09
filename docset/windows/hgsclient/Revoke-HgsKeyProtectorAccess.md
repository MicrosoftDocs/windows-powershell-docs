---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsClient
ms.assetid: C46B9A7D-A0EF-49EA-95FD-3A2E94973357
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Revoke-HgsKeyProtectorAccess
ms.reviewer:
---

# Revoke-HgsKeyProtectorAccess

## SYNOPSIS
Revokes access for a guardian to a key protector.

## SYNTAX

### InputObject
```
Revoke-HgsKeyProtectorAccess -KeyProtector <CimInstance> -Guardian <CimInstance> [<CommonParameters>]
```

### FriendlyName
```
Revoke-HgsKeyProtectorAccess -KeyProtector <CimInstance> -GuardianFriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-HgsKeyProtectorAccess** cmdlet revokes access for a Host Guardian Service guardian to a key protector.
This operation requires access to private signing key of the owner.

## EXAMPLES

### Example 1: Revoke access for a guardian
```
PS C:\> $Owner = Get-HgsGuardian -Name "Guardian11" 
PS C:\> $GuardianA = Get-HgsGuardian -Name "GuardianA" 
PS C:\> $GuardianB = Get-HgsGuardian -Name "GuardianB"
PS C:\> New-HgsKeyProtector -Owner $Owner -Guardians @($GuardianA, $GuardianB)
PS C:\> $Guardian04 = Get-HgsGuardian -Name "GuardianA"
PS C:\> Revoke-HgsKeyProtectorAccess -KeyProtector $KeyProtector -Guardian $Guardian04
```

The first command gets the guardian object named Guardian11 by using the **Get-HgsGuardian** cmdlet, and then stores that object in the **$Owner** variable.

The second and third commands get two guardians named GuardianA and GuardianB.
These commands store the guardians in the **$GuardianA** and **$GuardianB** variables.

The fifth command gets the guardian object named GuardianA, and then stores that object in the **$Guardian04** variable.

The final command revokes access for the guardian stored in **$Guardian04** for the key protector.

## PARAMETERS

### -Guardian
Specifies a guardian from which to revoke access to the key.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GuardianFriendlyName
Specifies a friendly name for a guardian.

```yaml
Type: String
Parameter Sets: FriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyProtector
Specifies the key protector for which to revoke access.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#MSFT_HgsKeyProtector
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Grant-HgsKeyProtectorAccess](./Grant-HgsKeyProtectorAccess.md)

[New-HgsKeyProtector](./New-HgsKeyProtector.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)

