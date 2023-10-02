---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsmappingstore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NfsMappingStore

## SYNOPSIS
Modifies configuration settings for an identity mapping store.

## SYNTAX

```
Set-NfsMappingStore [-ADDomainName <String>] [-AsJob] [-CimSession <CimSession[]>] [-EnableADLookup <Boolean>]
 [-EnableLdapLookup <Boolean>] [-EnableUNMLookup <Boolean>] [-InputObject <CimInstance[]>]
 [-LdapNamingContext <String>] [-LdapServer <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-UNMServer <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NfsMappingStore** cmdlet modifies configuration settings for an identity mapping store that a Network File System (NFS) server uses.

You can enable only one mapping store.
Valid values are: Active Directory domain, Lightweight Directory Access Protocol (LDAP) server, and User Name Mapping (UNM) server.
The specified mapping store must be accessible from an NFS server.

Note that you cannot modify password lookup by using the **Set-NfsMappingStore** cmdlet.
Password lookup is automatically enabled when passwd file is located in a folder in the \<system volume\>:\system32\drivers\ path.
You can also enable password mapping to Active Directory, LDAP, or UNM.

## EXAMPLES

### Example 1: Enable an AD DS store
```
PS C:\> Set-NfsMappingStore -EnableADLookup $true -ADDomainName "Contoso.com"
```

This command enables an AD DS store on a local NFS server and sets the AD DS store mapping store to Contoso.com.

### Example 2: Enable the default Active Directory Domain
```
PS C:\>Set-NfsMappingStore -EnableADLookup $true
```

This command enables the default AD DS store on a local NFS server and sets the default domain as the mapping store.
The default domain refers to the domain to which this NFS server belongs.

### Example 3: Enable LDAP Lookup
```
PS C:\>Set-NfsMappingStore -EnableLDAPLookup $true -LdapServer "Contoso-LDAP"
```

This command enables an LDAP mapping lookup on a local NFS server, and sets the LDAP mapping store to Contoso-LDAP.

## PARAMETERS

### -ADDomainName
Specifies the Active Directory domain name that an NFS server uses as an identity mapping store.

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

### -EnableADLookup
Sets Active Directory Domain Services (AD DS) as the mapping store on an NFS server.
If **EnableADLookup** is enabled and **ADDomainName** is not explicitly configured, then the default domain (that is, the domain to which the NFS server is joined) is used as a mapping store.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLdapLookup
Sets an LDAP server or an Active Directory Lightweight Directory Services (AD LDS) server as the mapping store on an NFS server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableUNMLookup
Sets a User Name Mapping (UNM) server as the mapping store on an NFS server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LdapNamingContext
Specifies an LDAP naming context that an NFS server uses when it performs LDAP queries.

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

### -LdapServer
Specifies an LDAP server name or AD LDS server name that stores identity mapping.
This information is used to get identity mapping information when LDAP lookup is enabled by using the **LdapLookup** parameter.

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

### -PassThru
Returns an object that represents the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -UNMServer
Specifies a UNM server.
When UNM lookup is enabled by using the **EnableUNMLookup** parameter, this information is used to get identity mapping information.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsMappingStore

## NOTES

## RELATED LINKS

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

