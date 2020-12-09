---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 98A8D393-21D4-46B7-AD43-926BFDD9FCC9
manager: dansimp
---

# Set-NfsMappedIdentity

## SYNOPSIS
Modifies a mapped identity.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NfsMappedIdentity [-GroupIdentifier <Int32>] [-UserIdentifier <Int32>] -NfsServer <String>
 -NfsServerPassword <SecureString> -NfsServerUser <String> -UserName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NfsMappedIdentity -GroupIdentifier <Int32> -GroupName <String> -NfsServer <String>
 -NfsServerPassword <SecureString> -NfsServerUser <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NfsMappedIdentity [-LdapNamingContext <String>] [-MappingStore] [-NfsServer <String>]
 [-NfsServerPassword <SecureString>] [-NfsServerUser <String>] [-Server <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NfsMappedIdentity** cmdlet modifies a mapped identity that is stored in the Network File System (NFS) server mapping store.
The cmdlet also updates the group membership of the Windows user account to match its assigned group identifier (GID).

## EXAMPLES

### Example 1: Modify a mapped identity that is stored in an AD LDS instance
```
PS C:\> Set-NfsMappedIdentity -MappingStore "LDAP" -GroupName "Administrators" -GroupIdentifier 600
```

This command modifies a mapped identity that is stored in a configured AD LDS instance and that corresponds to the Windows group account Administrators.
The command resets the associated group identifier to 600.

### Example 2: Modify a mapped identity that is stored in an Active Directory domain
```
PS C:\> Set-NfsMappedIdentity -Store "AD" -Server "Contoso"-UserName "JCool" -UserIdentifier 501 -GroupIdentifier 600
```

This command modifies a mapped identity that is stored in a specified Active Directory domain and that corresponds to the user account JCool.
The command sets the user identifier to 501 and the group identifier to 600, and it updates the group membership of the user account JCool to make it a member of a group account that has GID 600.

### Example 3: Modify a mapped identity that is stored in a configured LDAP store
```
PS C:\> Set-NfsMappedIdentity -Store "LDAP" -UserName "JCool" -UserIdentifier 501 -GroupIdentifier 600 -Server "MyLdapServer:389" -LdapNamingContext "CN=NFS,DC=NFS"
```

This command modifies a mapped identity that is stored in the LDAP store on a specified server that is named MyLdapServer and that corresponds to the user account Contoso\JCool.
It sets the user identifier to 501 and the group identifier to 600.
The command also adds the user account JCool to GID 600.

## PARAMETERS

### -GroupIdentifier
Specifies the group identifier of a mapped identity.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies the SAMAccountName of a Windows group account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context (directory partition) of an NFS identity mapping store.
You can use this parameter to search for mapped identities in the specified naming context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: DefaultNamingContext
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingStore
Specifies the type of identity mapping store in which the **Set-NfsMappedIdentity** cmdlet updates a mapped identity.
When this parameter is not specified, the **Set-NfsMappedIdentity** cmdlet gets the store configuration settings from the NFS server.
Valid values are **AD** and **LDAP**.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 
Accepted values: Ad, Ldap, Mapfiles

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP server name of a store that NFS server uses.
This can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the cmdlet tries to connect to either the LDAP store on the local computer at port 389 when **MappingStore** is LDAP, or the Active Directory domain of the computer when **MappingStore** is Active Directory.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: Localhost:389
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies a UID to assign to a user account that the **UserName** parameter specifies.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the SAMAccountName of a user account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NfsServer
Specifies the name of the NFS server where the Windows user account is to be created, when the mapped identity store is Ldap.

This parameter is only applicable when the value of the **MappingStore** parameter is set to **Ldap**.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -NfsServerUser
Specifies the user name to use to authenticate against the NFS server specified by the **NfsServer** parameter.

This parameter is only applicable when the value of the **MappingStore** parameter is set to **Ldap**.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -NfsServerPassword
Specifies the password to use to authenticate against the NFS server specified by the **NfsServer** parameter.

This parameter is only applicable when the value of the **MappingStore** parameter is set to **Ldap**.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

