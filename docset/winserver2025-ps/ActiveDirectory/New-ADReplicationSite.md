---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adreplicationsite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADReplicationSite
---

# New-ADReplicationSite

## SYNOPSIS
Creates an Active Directory replication site in the directory.

## SYNTAX

```
New-ADReplicationSite [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-AutomaticInterSiteTopologyGenerationEnabled <Boolean>] [-AutomaticTopologyGenerationEnabled <Boolean>]
 [-Credential <PSCredential>] [-Description <String>] [-Instance <ADReplicationSite>]
 [-InterSiteTopologyGenerator <ADDirectoryServer>] [-ManagedBy <ADPrincipal>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-RedundantServerTopologyEnabled <Boolean>] [-ReplicationSchedule <ActiveDirectorySchedule>]
 [-ScheduleHashingEnabled <Boolean>] [-Server <String>] [-TopologyCleanupEnabled <Boolean>]
 [-TopologyDetectStaleEnabled <Boolean>] [-TopologyMinimumHopsEnabled <Boolean>]
 [-UniversalGroupCachingEnabled <Boolean>] [-UniversalGroupCachingRefreshSite <ADReplicationSite>]
 [-WindowsServer2000BridgeheadSelectionMethodEnabled <Boolean>]
 [-WindowsServer2000KCCISTGSelectionBehaviorEnabled <Boolean>] [-WindowsServer2003KCCBehaviorEnabled <Boolean>]
 [-WindowsServer2003KCCIgnoreScheduleEnabled <Boolean>]
 [-WindowsServer2003KCCSiteLinkBridgingEnabled <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ADReplicationSite** cmdlet is used to create sites in Active Directory replication.
Sites are used in Active Directory to either enable clients to discover network resources (published shares, domain controllers) close to the physical location of a client computer, or to reduce network traffic over wide area network (WAN) links.
Sites can also be used to optimize replication between domain controllers.

## EXAMPLES

### Example 1: Create a replication site
```powershell
PS C:\> New-ADReplicationSite -Name "NorthAmerica"
```

This command creates a new site named NorthAmerica.

### Example 2: Create a replication site and set a property for it
```powershell
PS C:\> New-ADReplicationSite -Name "Europe" -AutomaticInterSiteTopologyGenerationEnabled $FALSE
```

This command creates a new site named Europe, and sets the **AutomaticInterSiteTopologyGenerationEnabled** property on the new object.

### Example 3: Create a replication site and set its replication schedule
```powershell
PS C:\> $Schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule
PS C:\> $Schedule.ResetSchedule()
PS C:\> $Schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty");
PS C:\> New-ADReplicationSite -Name "Asia" -ReplicationSchedule $schedule
```

This example creates a new site named Asia, and sets the daily *ReplicationSchedule* from 20:00 to 22:30.

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

### -AutomaticInterSiteTopologyGenerationEnabled
Indicates whether the cmdlet prevents the Knowledge Consistency Checker (KCC) that functions as the intersite topology generator (ISTG) from generating connections for intersite replication.
Use this option when you want to create manual intersite connections (disable the ISTG) but retain the KCC to generate intrasite connections.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutomaticTopologyGenerationEnabled
Indicates whether to enable automatic topology generation.
When enabled, prevents the KCC from generating intrasite connections on all servers in the site.
Disable this option if you use manual connections and do not want the KCC to build connections automatically.

```yaml
Type: Boolean
Parameter Sets: (All)
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
Specifies an instance of a site object to use as a template for a new site object.

You can use an instance of an existing site object as a template or you can construct a new site object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing site object as a template for a new object.
To retrieve an instance of an existing site object, use the **Get-ADReplicationSite** cmdlet.
Then provide this site object to the *Instance* parameter of the **New-ADReplicationSite** cmdlet to create a new site object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADReplicationSite** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADReplicationSite** cmdlet to create the new site object.

Note:
Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADReplicationSite
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterSiteTopologyGenerator
Specifies the server acting as the inter-site topology generator for this site.

```yaml
Type: ADDirectoryServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedBy
Specifies the user or group that manages the object by providing one of the following property values:

- Distinguished name
- GUID (objectGUID)
- Security identifier (objectSid)
- SAM account name (sAMAccountName)

Note:
The identifier in parentheses is the LDAP display name for the property.

This parameter sets the Active Directory attribute with an LDAP display name of managedBy.

```yaml
Type: ADPrincipal
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the replication site object.

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

### -ProtectedFromAccidentalDeletion
Specifies whether to prevent the object from being deleted.
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedundantServerTopologyEnabled
Indicates whether the cmdlet creates redundant connections between sites before a failure takes place.
When enabled, disables the Knowledge Consistency Checker (KCC) failover.
Requires that automatic detection of failed connections also be disabled (+IS_TOPL_DETECT_STALE_DISABLED).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicationSchedule
Specifies the default replication schedule for connections within this site (intra-site replication).

```yaml
Type: ActiveDirectorySchedule
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleHashingEnabled
Indicates whether the cmdlet spreads replication start times randomly across the entire schedule interval rather than just the first quarter of the interval.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

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
When enabled, prevents the KCC from removing connection objects that it does not need.
Disable this option if you want to take responsibility for removing old redundant connections.
Alternatively, to control or augment the topology, you can use manual connections, which the KCC does not delete.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopologyDetectStaleEnabled
Indicates whether the cmdlet enables topology detect stale.
Prevents the KCC from excluding servers that are unreachable from the topology; that is, the KCC does use an alternate server to reroute replication.
Use this option only if network communication is very unstable and brief outages are expected.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopologyMinimumHopsEnabled
Indicates whether the cmdlet enables topology minimum hops.
When enabled, prevents the KCC from generating optimizing connections in the ring topology of intrasite replication.
Optimizing connections reduce the replication latency in the site and disabling them is not recommended.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UniversalGroupCachingEnabled
Indicates whether the cmdlet enables universal group caching.
If this parameter is true, it indicates this site caches universal groups, which are those groups cached on global catalog (GC) servers.
It can be useful in sites with no GC servers available locally.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UniversalGroupCachingRefreshSite
Specifies the name of a site from which the cache is pulled if universal group caching is enabled.

```yaml
Type: ADReplicationSite
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -WindowsServer2000BridgeheadSelectionMethodEnabled
Implements the Windows 2000 Server method of selecting a single bridgehead server per directory partition and transport.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsServer2000KCCISTGSelectionBehaviorEnabled
Indicates whether the cmdlet implements the Windows 2000 Server method of ISTG selection.
Off by default.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsServer2003KCCBehaviorEnabled
Implements KCC operation that is consistent with Windows Server 2003 forest functional level.
This option can be set if all domain controllers in the site are running Windows Server 2003.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsServer2003KCCIgnoreScheduleEnabled
Indicates whether to ignore schedules.
When the forest functional level Windows Server 2003 or Windows Server 2003 interim is in effect, provides KCC control of the ability to ignore schedules (replication occurs at the designated intervals and is always available).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsServer2003KCCSiteLinkBridgingEnabled
Indicates whether the cmdlet enables site link bridging.
When the forest functional level Windows Server 2003 or Windows Server 2003 interim is in effect, provides KCC control of the ability to enable or disable site link bridging.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite
A site object that is a template for the new site object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite

## NOTES

## RELATED LINKS

[Get-ADReplicationSite](./Get-ADReplicationSite.md)

[Remove-ADReplicationSite](./Remove-ADReplicationSite.md)

[Set-ADReplicationSite](./Set-ADReplicationSite.md)
