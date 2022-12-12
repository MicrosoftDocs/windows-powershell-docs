---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://learn.microsoft.com/powershell/module/nfs/install-nfsmappingstore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-NfsMappingStore

## SYNOPSIS
Installs and initializes an AD LDS instance as an identity mapping store.

## SYNTAX

```
Install-NfsMappingStore [-InstanceName <String>] [-LdapPort <Int32>]
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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: 389
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

