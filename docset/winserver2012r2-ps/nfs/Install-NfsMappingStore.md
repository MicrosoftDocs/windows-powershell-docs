---
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Install-NfsMappingStore
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C627F113-DEC4-4AA1-9DA5-0A0BD1AF0209
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Install-NfsMappingStore

## SYNOPSIS
Installs and initializes an AD LDS instance as an identity mapping store.

## SYNTAX

```
Install-NfsMappingStore [-InstanceName <String>] [-LdapPort <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Install-NfaMappingStore** cmdlet installs the Active Directory Lightweight Directory Services (AD LDS) role on a local computer.
It then initializes an AD LDS instance as an identity mapping store.

## EXAMPLES

### Example 1: Install AD LDS and create an AD LDS instance as an identity mapping store
```
PS C:\> Install-NfsMappingStore -InstanceName "NFSMappingStore" -LdapPort 389
Successfully created ADLDS instance named NFSMappingStore on server NfsServer01. The instance is running on port 389 and the partition is CN=nfs,DC=nfs.
```

This command installs the AD LDS role on a local computer and creates the AD LDS instance NFSMappingStore, which runs on port 389.
It also creates the partition CN=nfs,DC=nfs and sets the default naming context to CN=nfs,DC=nfs.

## PARAMETERS

### -InstanceName
Specifies the name for the for the new AD LDS instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: instance

Required: False
Position: Named
Default value: NFSInstance
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapPort
Specifies the LDAP port number for the new AD LDS instance.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: port

Required: False
Position: Named
Default value: 389
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Nothing

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

