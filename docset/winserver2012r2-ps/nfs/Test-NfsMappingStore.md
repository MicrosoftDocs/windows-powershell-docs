---
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Test-NfsMappingStore
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E4F5B4D8-B6B7-4EF0-9A70-DF830000D0BD
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Test-NfsMappingStore

## SYNOPSIS
Verifies that an identity mapping store is configured correctly.

## SYNTAX

```
Test-NfsMappingStore [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Test-NfsMappingStore** cmdlet verifies that you correctly set up and configured an identity mapping store.
You can use **Get-NfsMappingStore** to get the mapping configuration of an NFS server.

For an Active Directory Lightweight Directory Services (AD LDS) store or any other Lightweight Directory Access Protocol (LDAP) mapping store, the **Test-NfsMappingStore** cmdlet verifies that a Network File System (NFS) server can reach a configured AD LDS server and that the identity mapping schema is applied.

For an Active Directory mapping store, the **Test-NfsMappingStore** cmdlet verifies that an NFS server can reach the relevant domain controller, and that the domain functional level is Windows Server 2003 R2 or later

## EXAMPLES

### Example 1: Test the configuration of an identity mapping store
```
PS C:\> Test-NfsMappingStore
```

This command tests the configuration of an identity mapping store on a local NFS server.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

