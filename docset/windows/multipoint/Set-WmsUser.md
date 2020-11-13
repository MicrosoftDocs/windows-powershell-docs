---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-WmsUser
ms.reviewer:
ms.assetid: 36EA3998-AC6D-4269-98D4-5E73C37BB8A8
---

# Set-WmsUser

## SYNOPSIS
Modifies a Windows MultiPoint Server user account.

## SYNTAX

### UseUserName
```
Set-WmsUser [-Name] <String> [-FullName <String>] [-Description <String>] [-UserType <UserTypePS>]
 [-Server <String>] [<CommonParameters>]
```

### UseCreds
```
Set-WmsUser [-Credential] <PSCredential> [-FullName <String>] [-Description <String>] [-UserType <UserTypePS>]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsUser** cmdlet updates a local user on the current Windows MultiPoint Server system.

## EXAMPLES

### Example 1
```
PS C:\> Set-WmsUser -Name "Student01" -Description "New Student" -FullName "Patti Fuller"
```

This command updates a user account with the description New Student, the name as Student01, and the full name as Patti Fuller.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object. Use the **Get-Credential** cmdlet to get a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: UseCreds
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description.

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

### -FullName
Specifies the full name of the user.

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

### -Name
Specifies a name for the user.

```yaml
Type: String
Parameter Sets: UseUserName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command. The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserType
Specifies the user type. The acceptable values for this parameter are:

 - Administrator
 - Standard
 - DashboardUser

```yaml
Type: UserTypePS
Parameter Sets: (All)
Aliases: 
Accepted values: Administrator, Standard, DashboardUser

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WmsUser]()

[New-WmsUser]()

[Remove-WmsUser]()

