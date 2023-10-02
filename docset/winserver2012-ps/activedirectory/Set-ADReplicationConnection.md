---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adreplicationconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADReplicationConnection

## SYNOPSIS
Sets properties on Active Directory replication connections.

## SYNTAX

### Identity
```
Set-ADReplicationConnection [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Identity] <ADReplicationConnection> [-PassThru]
 [-Remove <Hashtable>] [-Replace <Hashtable>] [-ReplicateFromDirectoryServer <ADDirectoryServer>]
 [-ReplicationSchedule <ActiveDirectorySchedule>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADReplicationConnection [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] -Instance <ADReplicationConnection> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-ADReplicationConnection cmdlet sets properties on Active Directory replication connections. 
Connections are used to enable domain controllers to replicate with each other.
A connection defines a one-way, inbound route from one domain controller, the source, to another domain controller, the destination.
The Kerberos consistency checker (KCC) reuses existing connections where it can, deletes unused connections, and creates new connections if none exist that meet the current need.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADReplicationConnection "5f98e288-19e0-47a0-9677-57f05ed54f6b" -ReplicateFromDirectoryServer corp-DC01
```

Description

-----------

Set the replication connection with name '5f98e288-19e0-47a0-9677-57f05ed54f6b' to replicate from corp-DC01.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule;
$schedule.ResetSchedule();
$schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty");
Get-ADReplicationConnection -Filter "ReplicateFromDirectoryServer -eq 'corp-DC01'" -Properties ReplicationSchedule | % {Set-ADReplicationConnection $_ - ReplicationSchedule $schedule}
```

Description

-----------

Get all the replication connections in the directory that replicate from corp-DC01.
Set the daily replication schedule on these connection objects.

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

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=saradavis,OU=users,OU=asia,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADGroup

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy

Microsoft.ActiveDirectory.Management.ADDomain

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADReplicationConnection
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of an Active Directory object to use as a template for a new Active Directory object.

You can use an instance of an existing Active Directory object as a template or you can construct a new Active Directory object by using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create a new Active Directory object.

Method 1: Use an existing Active Directory object as a template for a new object.
To retrieve an instance of an existing Active Directory object, use a cmdlet such as Get-ADObject.
Then provide this object to the Instance parameter of the New-ADObject cmdlet to create a new Active Directory object.
You can override property values of the new object by setting the appropriate parameters.

$objectInstance = Get-ADObject -Identity saraDavisDesktop

New-ADObject -Name "ellenAdamsDesktop"  -Instance $ObjectInstance -Type "computer"

Method 2: Create a new ADObject and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADObject cmdlet to create the new Active Directory object.

$objectInstance = new-object Microsoft.ActiveDirectory.Management.ADObject $objectInstance.Description = "Ellen Adams New Computer" New-ADObject -Name ellenAdamsDesktop  -Instance $ObjectInstance -Type computer

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADReplicationConnection
Parameter Sets: Instance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ReplicateFromDirectoryServer
Specifies the domain controller to use as a source for this replication connection.

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

### -ReplicationSchedule
Specifies the schedule on which the source server is available for replication.

Replication occurs at intervals that administrators can schedule so that use of expensive WAN links is managed.
Use this parameter to specify the replication intervals.
For more information on how replication topology works, go to http://go.microsoft.com/fwlink/?LinkId=223932.

To specify the replication schedule,

1. Create a new Active Directory schedule object.

   Example:

   `$schedule = New-Object -TypeName System.DirectoryServices.ActiveDirectory.ActiveDirectorySchedule;`

2. Edit the schedule on the Active Directory schedule object.

   Example:

   `$schedule.ResetSchedule();`

   `$schedule.SetDailySchedule("Twenty","Zero","TwentyTwo","Thirty");`

3. Using the Active Directory schedule object, set the replication schedule of the connection

   `Set-ADReplicationConnection "5f98e288-19e0-47a0-9677-57f05ed54f6b" -ReplicationSchedule $schedule`

For more information on the ActiveDirectorySchedule class, go to http://go.microsoft.com/fwlink/?LinkId=223933.

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

### None or Microsoft.ActiveDirectory.Management.ADReplicationConnection
A connection object is received by the Identity parameter.

A connection object that was retrieved by using the Get-ADReplicationConnection cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationConnection

## NOTES

## RELATED LINKS

[Get-ADReplicationConnection](./Get-ADReplicationConnection.md)

