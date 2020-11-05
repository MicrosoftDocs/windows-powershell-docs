---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E4F5B4D8-B6B7-4EF0-9A70-DF830000D0BD
manager: dansimp
---

# Test-NfsMappingStore

## SYNOPSIS
Verifies that an identity mapping store is configured correctly.

## SYNTAX

```
Test-NfsMappingStore [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
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
Aliases: 

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

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

