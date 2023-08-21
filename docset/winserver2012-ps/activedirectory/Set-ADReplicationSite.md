---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adreplicationsite?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The Set-ADReplicationSite cmdlet is used to set the properties for an Active Directory site that is being used for replication.
Sites are used in Active Directory to either enable clients to discover network resources (published shares, domain controllers) close to the physical location of a client computer or to reduce network traffic over wide area network (WAN) links.
Sites can also be used to optimize replication between domain controllers.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADReplicationSite NorthAmerica -InterSiteTopologyGenerator corp-DC02 -AutomaticInterSiteTopologyGenerationEnabled $false
```

Description

-----------

Set the properties of the site with name 'NorthAmerica' to prevent its intersite topology generator (ISTG) at 'corp-DC02' from generating connections for intersite replication.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADReplicationSite -Filter * | % {Set-ADReplicationSite $_ -ScheduleHashingEnabled $true}
```

Description

-----------

Returns all the sites in the directory and sets the ScheduleHashingEnabled propertyto spread replication start times randomly across the entire schedule interval rather than just the first quarter of the interval..

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule;
$schedule.ResetSchedule();
$schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty");
Set-ADReplicationSite "Asia" -ReplicationSchedule $schedule
```

Description

-----------

Set the daily replication schedule of the site with name 'Asia'.

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon..
The format for this parameter is

-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}

For example, if you want to remove the value "555-222-2222" and add the values "555-222-1111" and "555-222-3333" to Phone-Office-Other attribute (LDAP display name 'otherTelephone'), and add the value "555-222-9999" to Phone-Mobile-Other (LDAP display name 'otherMobile'), set the Add and Remove parameters as follows.

-Add @{otherTelephone='555-222-1111', '555-222-3333'; otherMobile='555-222-9999' } -Remove @{otherTelephone='555-222-2222'}

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

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
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticInterSiteTopologyGenerationEnabled
Prevents the KCC that functions as the intersite topology generator (ISTG) from generating connections for intersite replication.
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
Specifies an array of object properties that will be cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName

For example, if you want to clear the value for the Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Clear parameter as follows.

-Clear otherTelephone

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

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

Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
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
This parameter sets the value of the Description property for the object.
The LDAP Display Name (ldapDisplayName) for this property is "description".

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

Distinguished Name

Example: CN=NorthAmerica,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

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
The following examples show how to use these two methods to create a new site object.

Method 1: Use an existing site object as a template for a new object.
To retrieve an instance of an existing site object, use a cmdlet such as Get-ADReplicationSite.
Then provide this object to the Instance parameter of the New-ADReplicationSite cmdlet to create a new site object.
You can override property values of the new object by setting the appropriate parameters.

$objectInstance = Get-ADReplicationSite -Identity NorthAmerica

New-ADReplicationSite -Name "SouthAmerica"  -Instance $ObjectInstance

Method 2: Create a new ADReplicationSite and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADReplicationSite cmdlet to create the new Active Directory object.

$objectInstance = new-object Microsoft.ActiveDirectory.Management.ADReplicationSite

$objectInstance.Description = North America"

New-ADReplicationSite -Name "NorthAmerica"  -Instance $ObjectInstance

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
The server acting as the inter-site topology generator for this site.

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
Specifies the user or group that manages the object by providing one of the following property values.
Note: The identifier in parentheses is the LDAP display name for the property.

Distinguished Name

Example:  CN=SaraDavis,OU=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

This parameter sets the Active Directory attribute with an LDAP Display Name of "managedBy".

The following example shows how to specify this parameter.

-ManagedBy ContosoAdmins

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
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter to true.

-ProtectedFromAccidentalDeletion $true

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
Creates redundant connections between sites before a failure takes place.
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
The format for this parameter is

-Remove @{Attribute1LDAPDisplayName=value\[\];   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to add the values blue and green and remove the value pink from a property with a LDAP display name of FavColors, set the Add and Remove parameters as follows.

-Add @{FavColors=Blue,Green} -Remove {FavColors=Pink}

When you use the Add, Remove, Replace and Clear parameters together, the parameters will be applied in the following sequence:

..Remove

..Add

..Replace

..Clear

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
The format for this parameter is

-Replace @{Attribute1LDAPDisplayName=value\[\],   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to replace the value "555-222-2222" with the values "555-222-1111" for Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Replace parameter as follows.

-Replace @{otherTelephone='555-222-2222', '555-222-1111'}

When you use the Add, Remove, Replace  and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

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
Default replication schedule for connections within this site (intra-site replication).

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
Spreads replication start times randomly across the entire schedule interval rather than just the first quarter of the interval.

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
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Powershell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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
When enabled,  this optional parameter prevents the Knowledge Consistency Checker (KCC) from removing connection objects that it does not need.
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
Implements the Windows 2000 Server method of selecting a single bridgehead server per directory partition and transport.

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
When enabled, this parameter implements the Windows 2000 Server method of Intersite Topology Generator (ISTG) selection.
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
Implements Knowledge Consistency Checker (KCC) operation that is consistent with Windows Server 2003 forest functional level.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite
A site object is received by the Identity parameter.

A site object that was retrieved by using the Get-ADReplicationSite cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite

## NOTES

## RELATED LINKS

[Get-ADReplicationSite](./Get-ADReplicationSite.md)

[New-ADReplicationSite](./New-ADReplicationSite.md)

[Remove-ADReplicationSite](./Remove-ADReplicationSite.md)
