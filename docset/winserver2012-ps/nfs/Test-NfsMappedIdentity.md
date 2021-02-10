---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 59A2473C-C672-403A-9DF1-A831247D6022
manager: dansimp
---

# Test-NfsMappedIdentity

## SYNOPSIS
Verifies that a mapped identity is correctly configured.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Test-NfsMappedIdentity [-MappingStore]
```

### UNNAMED_PARAMETER_SET_2
```
Test-NfsMappedIdentity [-AccountName <String>] [-AccountType] [-GroupIdentifier <Int32>]
 [-SupplementaryGroups <String>] [-UserIdentifier <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Test-NfsMappedIdentity [-LdapNamingContext <String>] [-Server <String>] [-MappingStore]
```

### UNNAMED_PARAMETER_SET_4
```
Test-NfsMappedIdentity [-MapFilesPath <String>] [-MappingStore]
```

## DESCRIPTION
The **Test-NfsMappedIdentity** cmdlet verifies a mapped identity and confirms that it is configured correctly.
The **Test-NfsMappedIdentity** cmdlet checks a mapped identity for duplicate user identifiers (UIDs) or group identifiers (GIDs).
It also validates that the user accounts are members of the correct group account according to the GIDs that are assigned to them.

## EXAMPLES

### Example 1: Verify a mapped identity that is stored in a configured AD LDS instance
```
PS C:\> Test-NfsMappedIdentity -MappingStore "LDAP" -AccountName "JCool" -AccountType "User" -Verbose
VERBOSE: No errors found.
```

This command verifies a mapped identity that is stored in a AD LDS instance on a server where this command is run..

## PARAMETERS

### -AccountName
Specifies the SAMAccountNam of the Windows user account or group account of a mapped identity.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountType
Specifies the Windows account type of a mapped identity.
Supported values are: User and Group.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 
Accepted values: User, Group

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupIdentifier
Specifies the group identifier of a mapped identity.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of an NFS identity mapping store.
You can use this parameter to search for mapped identities in a specified naming context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MapFilesPath
Specifies the path of the passwd and group map files from which the **Test-NfsMappedIdentity** cmdlet obtains a mapped identity.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingStore
Specifies the type of identity mapping store from which the **Test-NfsMappedIdentity** cmdlet gets a mapped identity.
When this parameter is not specified, the **Test-NfsMappedIdentity** cmdlet obtains the store configuration settings from the NFS server configuration.
Valid values are: **AD**, **LDAP**, and **MapFiles**.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 
Accepted values: Ad, Ldap, Mapfiles

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 
Accepted values: Ad, Ldap, Mapfiles

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP server name of the store that NFS server uses.
This can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the **Test-NfsMappedIdentity** cmdlet tries to connect to either the LDAP store on the local computer at port 389 when **MappingStore** is LDAP, or the Active Directory domain of the computer when **MappingStore** is Active Directory.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SupplementaryGroups
Specifies a comma-separated list of group names to verify the group membership of an account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies the user identifier of a UNIX user account from which the **Test-NfsMappedIdentity** cmdlet obtains a mapped identity.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

