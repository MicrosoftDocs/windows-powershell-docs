---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adreplicationsitelinkbridge?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADReplicationSiteLinkBridge
---

# New-ADReplicationSiteLinkBridge

## SYNOPSIS
Creates a site link bridge in Active Directory for replication.

## SYNTAX

```
New-ADReplicationSiteLinkBridge [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Description <String>] [-Instance <ADReplicationSiteLinkBridge>]
 [-InterSiteTransportProtocol <ADInterSiteTransportProtocolType>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-Server <String>] [[-SiteLinksIncluded] <ADReplicationSiteLink[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-ADReplicationSiteLinkBridge** cmdlet creates a site link bridge in Active Directory for use in replication.
A site link bridge connects two or more site links and enables transitivity between site links.
Each site link in a bridge must have a site in common with another site link in the bridge.

## EXAMPLES

### Example 1: Create a site link bridge
```
PS C:\> New-ADReplicationSiteLinkBridge -Name "NorthAmerica-Asia" -SiteLinksIncluded "NorthAmerica-Europe","Europe-Asia"
```

This command creates a site link bridge named NorthAmerica-Asia that bridges the site links NorthAmerica-Europe and Europe-Asia.

### Example 2: Create a site link bridge and set the intersite transport protocol
```
PS C:\> New-ADReplicationSiteLinkBridge -Name "NorthAmerica-Asia" -SiteLinksIncluded "NorthAmerica-Europe","Europe-Asia" -InterSiteTransportProtocol IP
```

This command creates a site link bridge named NorthAmerica-Asia that bridges the site links NorthAmerica-Europe and Europe-Asia, and sets the *InterSiteTransportProtocol* value on the new object.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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

### -Description
Specifies a description of the object.
This parameter sets the value of the **Description** property for the object.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a site link bridge object to use as a template for a new site link bridge object.

You can use an instance of an existing site link bridge object as a template or you can construct a new site link bridge object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing site link bridge object as a template for a new object.
To retrieve an instance of an existing Active Directory object, use the Get-ADReplicationSiteLinkBridge cmdlet.
Then provide this object to the Instance parameter of the **New-ADReplicationSiteLinkBridge** cmdlet to create a new site link bridge object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADReplicationSiteLinkBridge** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADReplicationSiteLinkBridge** cmdlet to create the new site link bridge object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set raises an error.

```yaml
Type: ADReplicationSiteLinkBridge
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterSiteTransportProtocol
Specifies the intersite transport protocol for this site link bridge.
The acceptable values for this parameter are:

- IP
- SMTP

```yaml
Type: ADInterSiteTransportProtocolType
Parameter Sets: (All)
Aliases:
Accepted values: IP, SMTP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication site link bridge object.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAP display name (**ldapDisplayName**) defined for it in the Active Directory schema.

To specify a single value for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value}`

To specify multiple values for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}`

You can specify values for more than one attribute by using semicolons to separate attributes.
The following syntax shows how to set values for multiple attributes:

`-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}`

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
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

### -Server
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- FQDN
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### -SiteLinksIncluded
Specifies an array of site links that are included in this site link bridge.
Accepted values for this parameter are the distinguished name, a GUID, or the name of a site link.
This parameter must contain two sites upon creation or else the *Instance* parameter must be included and used.

```yaml
Type: ADReplicationSiteLink[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLinkBridge
A site link bridge object that is a template for the new site link bridge object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLinkBridge

## NOTES
* By default, all site links are bridged (transitive), and creating a site link design is not required. We recommend that you keep transitivity enabled by not changing this default. However, you must disable bridging for all site links and complete a site link bridge design if either of the following is true:

- Your IP network is not fully routed.
- You need to control the replication flow of the changes made in Active Directory Domain Services (AD DS).

## RELATED LINKS

[Get-ADReplicationSiteLinkBridge](./Get-ADReplicationSiteLinkBridge.md)

[Remove-ADReplicationSiteLinkBridge](./Remove-ADReplicationSiteLinkBridge.md)

[Set-ADReplicationSiteLinkBridge](./Set-ADReplicationSiteLinkBridge.md)

