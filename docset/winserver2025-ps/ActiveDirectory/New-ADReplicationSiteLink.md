---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adreplicationsitelink?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADReplicationSiteLink
---

# New-ADReplicationSiteLink

## SYNOPSIS
Creates a new Active Directory site link for in managing replication.

## SYNTAX

```
New-ADReplicationSiteLink [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Cost <Int32>]
 [-Credential <PSCredential>] [-Description <String>] [-Instance <ADReplicationSiteLink>]
 [-InterSiteTransportProtocol <ADInterSiteTransportProtocolType>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-ReplicationFrequencyInMinutes <Int32>]
 [-ReplicationSchedule <ActiveDirectorySchedule>] [-Server <String>] [[-SitesIncluded] <ADReplicationSite[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-ADReplicationSiteLink** cmdlet can be used to create a new Active Directory site link.
A site link connects two or more sites.
Site links reflect the administrative policy for how sites are to be interconnected and the methods used to transfer replication traffic.
You must connect sites with site links so that domain controllers at each site can replicate Active Directory changes.

## EXAMPLES

### Example 1: Create a replication site link
```
PS C:\> New-ADReplicationSiteLink -Name "NorthAmerica-Europe" -SitesIncluded NorthAmerica,Europe
```

This command creates a new site link named NorthAmerica-Europe linking the two sites NorthAmerica and Europe.

### Example 2: Create a replication site link and set properties for it
```
PS C:\> New-ADReplicationSiteLink -Name "Europe-Asia" -SitesIncluded Europe,Asia -Cost 100 -ReplicationFrequencyInMinutes 15 -InterSiteTransportProtocol IP
```

This command creates a new site link named Europe-Asia linking two sites Europe and Asia, and set the *Cost*, *ReplicationFrequencyInMinutes*, and *InterSiteTransportProtocol* on the new object.

### Example 3: Create a replication site link and set its replication schedule
```
PS C:\> $Schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule
PS C:\> $Schedule.ResetSchedule()
PS C:\> $Schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty")
PS C:\> New-ADReplicationSiteLink -Name "NorthAmerica-SouthAmerica" -SitesIncluded NorthAmerica,SouthAmerica -ReplicationSchedule $Schedule
```

This example creates a new site link named NorthAmerica-SouthAmerica linking two sites NorthAmerica and SouthAmerica, and set the daily *ReplicationSchedule* from 20:00 to 22:30.

### Example 4: Create a replication site link and enable change notification for it
```
PS C:\> New-ADReplicationSiteLink -Name "Europe-Asia" -SitesIncluded Europe,Asia -OtherAttributes @{'options'=1}
```

This command creates a new site link named Europe-Asia to link two sites, Europe and Asia.
The command also enables change notification on the new object.

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

### -Cost
Specifies the cost to be placed on the site link.
For more information on determining the cost, see [Determining the Cost](https://go.microsoft.com/fwlink/?LinkId=221871) in the TechNet Library: http://go.microsoft.com/fwlink/?LinkId=221871.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies an instance of a site link object to use as a template for a new site link object.

You can use an instance of an existing site link object as a template or you can construct a new site link object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing site link object as a template for a new object.
To retrieve an instance of an existing site link object, use a cmdlet such as **Get-ADReplicationSiteLink**.
Then provide this object to the *Instance* parameter of the **New-ADReplicationSiteLink** cmdlet to create a new Active Directory object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADReplicationSiteLink** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the **New-ADReplicationSiteLink** cmdlet to create the new site link object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set raises an error.

```yaml
Type: ADReplicationSiteLink
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterSiteTransportProtocol
Specifies a valid intersite transport protocol option.
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
Specifies the name of the site link.
This parameter sets the **Name** property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

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
To identify an attribute, specify the LDAPDisplayName (**ldapDisplayName**) defined for it in the Active Directory schema.

Syntax:

To specify a single value for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value}`

To specify multiple values for an attribute

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

### -ReplicationFrequencyInMinutes
Species the frequency, in minutes, for which replication will occur where this site link is in use between sites.
Active Directory preserves bandwidth between sites by minimizing the frequency of replication and by allowing you to schedule the availability of site links for replication.
By default, intersite replication across each site link occurs every 180 minutes (3 hours).
You can adjust this frequency to match your specific needs.
Be aware that increasing this frequency increases the amount of bandwidth used by replication.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicationSchedule
Specifies the default replication schedule for any connections within this site link (intra-site replication).
This allows you to schedule the availability of site links for use by replication.
By default, a site link is available to carry replication traffic 24 hours a day, 7 days a week.
You can limit this schedule to specific days of the week and times of day.
You can, for example, schedule intersite replication so that it only occurs after normal business hours.

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

### -SitesIncluded
Specifies the list of sites included in the site link.

```yaml
Type: ADReplicationSite[]
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

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLink
A site link object that is a template for the new site link object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLink

## NOTES

## RELATED LINKS

[Get-ADReplicationSiteLink](./Get-ADReplicationSiteLink.md)

[Remove-ADReplicationSiteLink](./Remove-ADReplicationSiteLink.md)

[Set-ADReplicationSiteLink](./Set-ADReplicationSiteLink.md)

