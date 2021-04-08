---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/new-adreplicationsitelink?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The New-ADReplicationSiteLink cmdlet can be used to create a new Active Directory site link. 
A site link connects two or more sites.
Site links reflect the administrative policy for how sites are to be interconnected and the methods used to transfer replication traffic.
You must connect sites with site links so that domain controllers at each site can replicate Active Directory changes.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADReplicationSiteLink "NorthAmerica-Europe" -SitesIncluded NorthAmerica,Europe
```

Description

-----------

Create a new site link named 'NorthAmerica-Europe' linking the two sites 'NorthAmerica' and 'Europe'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>New-ADReplicationSiteLink "Europe-Asia" -SitesIncluded Europe,Asia -Cost 100 -ReplicationFrequencyInMinutes 15 -InterSiteTransportProtocol IP
```

Description

-----------

Create a new site link named 'Europe-Asia' linking two sites 'Europe' and 'Asia', and set the Cost, ReplicationFrequencyInMinutes and InterSiteTransportProtocol on the new object.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule;
$schedule.ResetSchedule();
$schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty");
New-ADReplicationSiteLink "NorthAmerica-SouthAmerica" -SitesIncluded NorthAmerica,SouthAmerica -ReplicationSchedule $schedule
```

Description

-----------

Create a new site link named 'NorthAmerica-SouthAmerica' linking two sites 'NorthAmerica' and 'SouthAmerica', and set the daily ReplicationSchedule from 20:00 to 22:30.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>New-ADReplicationSiteLink "Europe-Asia" -SitesIncluded Europe,Asia -OtherAttributes @{'options'=1}
```

Description

-----------

Create a new site link named 'Europe-Asia' linking two sites 'Europe' and 'Asia', and enable change notification on the new object.

## PARAMETERS

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
For more information on determining the cost, see the following topic called "Determining the Cost" in the TechNet Library: http://go.microsoft.com/fwlink/?LinkId=221871

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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

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
The following examples show how to use these two methods to create a new site link object.

Method 1: Use an existing site link object as a template for a new object.
To retrieve an instance of an existing site link object, use a cmdlet such as Get-ADReplicationSiteLink.
Then provide this object to the Instance parameter of the New-ADReplicationSiteLink cmdlet to create a new Active Directory object.
You can override property values of the new object by setting the appropriate parameters.

$objectInstance = Get-ADReplicationSiteLink -Identity "NorthAmerica-SouthAmerica"

New-ADReplicationSiteLink -Name "Europe-Asia"  -Instance $ObjectInstance

Method 2: Create a new ADReplicationSiteLink and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADReplicationSiteLink cmdlet to create the new site link object.

$objectInstance = new-object Microsoft.ActiveDirectory.Management.ADReplicationSiteLink

$objectInstance.Description = "Between North America and South America."

New-ADReplicationSiteLink -Name "NorthAmerica-SouthAmerica" -Instance $ObjectInstance

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

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
Supported protocol options for the New-ADReplicationSiteLink cmdlet include the following:  IP, SMTP.

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
This parameter sets the Name property of the Active Directory object.
The LDAP Display Name (ldapDisplayName) of this property is "name".

The following example shows how to set this parameter to a name string.

-Name "Europe-NorthAmerica"

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
To identify an attribute, specify the LDAPDisplayName (ldapDisplayName) defined for it in the Active Directory schema.

Syntax:

To specify a single value for an attribute:

-OtherAttributes @{'AttributeLDAPDisplayName'=value}

To specify multiple values for an attribute

-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}

You can specify values for more than one attribute by using semicolons to separate attributes. 
The following syntax shows how to set values for multiple attributes:

-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}

The following examples show how to use this parameter.

To set the value of a custom attribute called favColors that takes a set of Unicode strings, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"}

To set values for favColors and dateOfBirth simultaneously, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"; 'dateOfBirth'=" 01/01/1960"}

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

### -ReplicationFrequencyInMinutes
Species the frequency (in minutes) for which replication will occur where this site link is in use between sites.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLink
A site link object that is a template for the new site link object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSiteLink

## NOTES

## RELATED LINKS

[Get-ADReplicationSiteLink](./Get-ADReplicationSiteLink.md)

[Remove-ADReplicationSiteLink](./Remove-ADReplicationSiteLink.md)

[Set-ADReplicationSiteLink](./Set-ADReplicationSiteLink.md)

