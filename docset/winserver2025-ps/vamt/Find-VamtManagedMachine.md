---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/find-vamtmanagedmachine?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Find-VamtManagedMachine
---

# Find-VamtManagedMachine

## SYNOPSIS
Performs VAMT discovery operations.

## SYNTAX

```
Find-VamtManagedMachine -QueryType <DiscoveryType> -QueryValue <String> [-MachineFilter <String>]
 [-DbConnectionString <String>] [-Username <String>] [-Password <String>] [-DbCommandTimeout <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Find-VamtManagedMachine** cmdlet discovers products either on an individual computer or in a specified domain or workgroup, and then adds them to the dep_nextref_vamt database.
You can use this cmdlet in a script to periodically run product discovery on a domain or workgroup.
You can use this process to determine whether any new computers are present in the domain or workgroup.

## EXAMPLES

### Example 1: Get a computer by computer name
```
PS C:\>Find-VamtManagedMachine -QueryType Manual -QueryValue "MachineName"
```

This command finds a computer by looking for the specified computer name.

### Example 2: Search in a domain
```
PS C:\>Find-VamtManagedMachine -QueryType ActiveDirectory -QueryValue "DomainName" -MachineFilter "labcomp*"
```

This command searches the specified Active Directory domain.
The search results are restricted to the computers that have LabComp in their name.

### Example 3: Search a workgroup
```
PS C:\>Find-VamtManagedMachine -QueryType Workgroup -QueryValue "WorkgroupName" -MachineFilter "labcomp*"
```

This command searches the specified workgroup.
The search results are restricted to the computers that have LabComp in their name.

### Example 4: Search by using an LDAP query
```
PS C:\>Find-VamtManagedMachine -QueryType ldap -QueryValue "ldap://domainname/??sub?(&(objectclass=computer)(name=labcomp*))"
```

This command searches for computers by using an LDAP query.
The search results are restricted to the computers that have LabComp in their name.

### Example 5: Search in a domain and store results in specified database
```
PS C:\>Find-VamtManagedMachine -QueryType ActiveDirectory -QueryValue "DomainName" -MachineFilter "labcomp*" -DbConnectionString "Data Source=localhost\SQLEXPRESS;Initial Catalog=VAMT;Integrated Security=True;MultipleActiveResultSets=True"
```

This command searches the specified Active Directory domain.
The search results are restricted to the computers that have LabComp in their name, and the results are stored in the local SQLEXPRESS instance.

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.

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

### -DbConnectionString
Specifies the database that the discovered products are added to.
If no database connection string is provided, dep_nextref_vamt attempts to use the database that the dep_nextref_vamt user console used on the local computer.
If dep_nextref_vamt does not find a database, it returns an error.
You can find the connection string in the dep_nextref_vamt UI in the Preferences dialog box.
On the menu bar, click View, and then click Preferences to open the Volume Activation Management Tool Preferences dialog box.
The connection string is in the Database Settings section under Current connection string.

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

### -MachineFilter
Restricts the search results when used with the *QueryType* parameter, when the ActiveDirectory value or the WorkGroup value is specified.
Do not use the *MachineFilter* parameter when you specify the Manual value for the *QueryType* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Password
Provides a password if the environment to be checked for products is password-protected.

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

### -QueryType
Defines what kind of query to use to find the computers.
The acceptable values for this parameter are:

- Manual.
When you use this value, you can manually enter a computer IP address or name.
- ActiveDirectory.
When you used this value, dep_nextref_vamt searches the Active Directory domain.
- Workgroup.
When you use this value, dep_nextref_vamt searches the specified workgroup.
- LDAP.
When you use this value, you can supply a Lightweight Directory Access Protocol (LDAP) query to search for computers that the meet specified conditions.
For example, you can use this value in a script to search for new computers that were added to the network in a certain time frame.

```yaml
Type: DiscoveryType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -QueryValue
Specifies a query value.
The *QueryValue* parameter is required if the *QueryType* parameter is declared.
The acceptable values for this parameter are:

- If *QueryType* is Manual, *QueryValue* is the IP address or name of the computer.
- If *QueryType* is ActiveDirectory, *QueryValue* is the name of Active Directory domain.
- If *QueryType* is Workgroup, *QueryValue* is the name of the workgroup.
- If *QueryType* is LDAP, *QueryValue* is an LDAP query to search for computers that meet the specified conditions.
For example, you can use this value in a script to search for new computers that were added to the network in a certain time frame.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Username
Provides a user name if the environment to be checked for products is password-protected.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

