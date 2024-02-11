---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adreplicationsite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADReplicationSite
---

# Set-ADReplicationSite

## SYNOPSIS
Sets the replication properties for an Active Directory site.

## SYNTAX

### Identity
```
Set-ADReplicationSite [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>]
 [-AutomaticInterSiteTopologyGenerationEnabled <Boolean>] [-AutomaticTopologyGenerationEnabled <Boolean>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Description <String>] [-Identity] <ADReplicationSite>
 [-InterSiteTopologyGenerator <ADDirectoryServer>] [-ManagedBy <ADPrincipal>] [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-RedundantServerTopologyEnabled <Boolean>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-ReplicationSchedule <ActiveDirectorySchedule>] [-ScheduleHashingEnabled <Boolean>]
 [-Server <String>] [-TopologyCleanupEnabled <Boolean>] [-TopologyDetectStaleEnabled <Boolean>]
 [-TopologyMinimumHopsEnabled <Boolean>] [-UniversalGroupCachingEnabled <Boolean>]
 [-UniversalGroupCachingRefreshSite <ADReplicationSite>]
 [-WindowsServer2000BridgeheadSelectionMethodEnabled <Boolean>]
 [-WindowsServer2000KCCISTGSelectionBehaviorEnabled <Boolean>] [-WindowsServer2003KCCBehaviorEnabled <Boolean>]
 [-WindowsServer2003KCCIgnoreScheduleEnabled <Boolean>]
 [-WindowsServer2003KCCSiteLinkBridgingEnabled <Boolean>] [<CommonParameters>]
```

### Instance
```
Set-ADReplicationSite [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADReplicationSite> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADReplicationSite** cmdlet is used to set the properties for an Active Directory site that is being used for replication.
Sites are used in Active Directory to either enable clients to discover network resources (published shares, domain controllers) close to the physical location of a client computer or to reduce network traffic over wide area network (WAN) links.
Sites can also be used to optimize replication between domain controllers.

## EXAMPLES

### Example 1: Set the replication site to prevent connections
```
PS C:\> Set-ADReplicationSite -Identity NorthAmerica -InterSiteTopologyGenerator corp-DC02 -AutomaticInterSiteTopologyGenerationEnabled $False
```

The command sets the properties of the site with name NorthAmerica to prevent its intersite topology generator (ISTG) at corp-DC02 from generating connections for intersite replication.

### Example 2: Set replication start times for a filtered list of sites
```
PS C:\> Get-ADReplicationSite -Filter * | % {Set-ADReplicationSite $_ -ScheduleHashingEnabled $True}
```

This command returns all the sites in the directory and sets the **ScheduleHashingEnabled** property to spread replication start times randomly across the entire schedule interval rather than just the first quarter of the interval.

### Example 3: Set the replication schedule for a site
```
PS C:\> $Schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule
PS C:\> $Schedule.ResetSchedule()
PS C:\> $Schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty")
PS C:\> Set-ADReplicationSite -Identity "Asia" -ReplicationSchedule $Schedule
```

This example sets the daily replication schedule of the site with name Asia.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AutomaticInterSiteTopologyGenerationEnabled
Indicates whether the cmdlet prevents the Knowledge Consistency Checker (KCC) that functions as the intersite topology generator (ISTG) from generating connections for intersite replication.
Use this option when you want to create manual intersite connections (disable the ISTG) but retain the KCC to generate intrasite connections.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticTopologyGenerationEnabled
Indicates whether to enable automatic topology generation.
When enabled, prevents the KCC from generating intrasite connections on all servers in the site.
Disable this option if you use manual connections and do not want the KCC to build connections automatically.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Clear
Specifies an array of object properties that are cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

`-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: String[]
Parameter Sets: Identity
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.

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
The LDAP Display Name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A connection name
- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADReplicationSite
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a site object to use as a template for a new site object.

You can use an instance of an existing site object as a template or you can construct a new site object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing site object as a template for a new object.
To retrieve an instance of an existing site object, use a cmdlet such as **Get-ADReplicationSite**.
Then provide this object to the Instance parameter of the **New-ADReplicationSite** cmdlet to create a new site object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADReplicationSite** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADReplicationSite** cmdlet to create the new Active Directory object.

Note:  Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADReplicationSite
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterSiteTopologyGenerator
Specifies the server acting as the inter-site topology generator for this site.

```yaml
Type: ADDirectoryServer
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedBy
Specifies the user or group that manages the object by providing one of the following property values:

- Distinguished name
- GUID (objectGUID)
- Security identifier (objectSid)
- SAM account name (sAMAccountName)

 Note: The identifier in parentheses is the LDAP display name for the property.

This parameter sets the Active Directory attribute with an LDAP display name of managedBy.

```yaml
Type: ADPrincipal
Parameter Sets: Identity
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

### -ProtectedFromAccidentalDeletion
Specifies whether to prevent the object from being deleted.
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedundantServerTopologyEnabled
Indicates whether the cmdlet creates redundant connections between sites before a failure takes place.
When enabled, disables KCC failover.
Requires that automatic detection of failed connections also be disabled (+IS_TOPL_DETECT_STALE_DISABLED).

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Specifies that the cmdlet remove values of an object property.
Use this parameter to remove one or more values of a property that cannot be modified using a cmdlet parameter.
To remove an object property, you must use the LDAP display name.
You can remove more than one property by specifying a semicolon-separated list.
The format for this parameter is:

`-Remove @{Attribute1LDAPDisplayName=value[];   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the parameters are applied in the following sequence:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace
Specifies values for an object property that will replace the current values.
Use this parameter to replace one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is:

`-Replace @{Attribute1LDAPDisplayName=value[],   Attribute2LDAPDisplayName=value[]}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the parameters are applied in the following sequence:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationSchedule
Specifies the default replication schedule for connections within this site (intra-site replication).

```yaml
Type: ActiveDirectorySchedule
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleHashingEnabled
Indicates whether the cmdlet spreads replication start times randomly across the entire schedule interval rather than just the first quarter of the interval.

```yaml
Type: Boolean
Parameter Sets: Identity
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

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -TopologyCleanupEnabled
Indicates whether the cmdlet enables topology cleanup.
When enabled,  this optional parameter prevents the Knowledge Consistency Checker(KCC) from removing connection objects that it does not need.
Disable this option if you want to take responsibility for removing old redundant connections.
Alternatively, to control or augment the topology, you can use manual connections, which the KCC does not delete.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopologyDetectStaleEnabled
Indicates whether the cmdlet enables topology detect stale.
This parameter option prevents the Knowledge Consistency Checker (KCC) from excluding servers that are unreachable from the topology; that is, the KCC does use an alternate server to reroute replication.
Use this option only if network communication is very unstable and brief outages are expected.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopologyMinimumHopsEnabled
Indicates whether the cmdlet enables topology minimum hops.
When enabled, this parameter prevents the Knowledge Consistency Checker (KCC) from generating optimizing connections in the ring topology of intrasite replication.
Optimizing connections reduce the replication latency in the site and disabling them is not recommended.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniversalGroupCachingEnabled
Indicates whether the cmdlet enables universal group caching.
If this parameter is true, it indicates this site caches universal groups, which are those groups cached on global catalog (GC) servers.
It can be useful in sites with no GC servers available locally.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniversalGroupCachingRefreshSite
Specifies the name of a site.
If universal group caching is enabled, this parameter sets the name of the site from which the cache is pulled.

```yaml
Type: ADReplicationSite
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -WindowsServer2000BridgeheadSelectionMethodEnabled
Indicates whether the cmdlet implements the Windows 2000 Server method of selecting a single bridgehead server per directory partition and transport.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsServer2000KCCISTGSelectionBehaviorEnabled
Indicates whether the cmdlet implements the Windows 2000 Server method of Intersite Topology Generator (ISTG) selection.
By default, it is disabled.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsServer2003KCCBehaviorEnabled
Indicates whether the cmdlet implements Knowledge Consistency Checker (KCC) operation that is consistent with Windows Server 2003 forest functional level.
This option can be set if all domain controllers in the site are running Windows Server 2003.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsServer2003KCCIgnoreScheduleEnabled
Indicates whether to ignore schedules.
When the forest functional level Windows Server 2003 or Windows Server 2003 interim is in effect, provides KCC control of the ability to ignore schedules (replication occurs at the designated intervals and is always available).

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsServer2003KCCSiteLinkBridgingEnabled
Indicates whether the cmdlet enables site link bridging.
When the forest functional level Windows Server 2003 or Windows Server 2003 interim is in effect, provides Knowledge Consistency Checker (KCC) control of the ability to enable or disable site link bridging.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite
A site object is received by the *Identity* parameter.

A site object that was retrieved by using the **Get-ADReplicationSite** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite

## NOTES

## RELATED LINKS

[Get-ADReplicationSite](./Get-ADReplicationSite.md)

[New-ADReplicationSite](./New-ADReplicationSite.md)

[Remove-ADReplicationSite](./Remove-ADReplicationSite.md)

