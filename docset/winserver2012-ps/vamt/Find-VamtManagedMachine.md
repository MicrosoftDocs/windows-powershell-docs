---
external help file: VAMT_Cmdlets.xml
Module Name: VAMT
online version: https://learn.microsoft.com/powershell/module/vamt/find-vamtmanagedmachine?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Find-VamtManagedMachine

## SYNOPSIS
Performs VAMT discovery operations.

## SYNTAX

```
Find-VamtManagedMachine [-QueryType] <DiscoveryType> [-QueryValue] <String> [[-MachineFilter] <String>]
 [[-Username] <String>] [[-Password] <String>] [-DbCommandTimeout <Int32>] [-DbConnectionString <String>]
```

## DESCRIPTION
The **Find-VamtManagedMachine** cmdlet discovers products either on an individual computer or in a specified domain or workgroup, and then adds them to the dep_nextref_vamt database.
You can use this cmdlet in a script to periodically run product discovery on a domain or workgroup.
You can use this process to determine whether any new computers are present in the domain or workgroup.

## EXAMPLES

### Example 1
```
PS C:\>find-vamtmanagedmachine -querytype manual -queryvalue machinename
```

This command finds a computer by looking for the specified computer name.

### Example 2
```
PS C:\>find-vamtmanagedmachine -querytype activedirectory -queryvalue domainname -machinefilter labcomp*
```

This command searches the specified Active Directory domain.
The search results are restricted to the computers with LabComp in their name.

### Example 3
```
PS C:\>find-vamtmanagedmachine -querytype workgroup -queryvalue workgroupname -machinefilter labcomp*
```

This command searches the specified workgroup.
The search results are restricted to the computers with LabComp in their name.

### Example 4
```
PS C:\>find-vamtmanagedmachine -querytype ldap -queryvalue "ldap://domainname/??sub?(&(objectclass=computer)(name=labcomp*))"
```

This command searches for computers by using an LDAP query.
The search results are restricted to the computers with LabComp in their name.

## PARAMETERS

### -DbCommandTimeout
Indicates how long dep_nextref_vamt waits for a response from the database before timing out.
The default value is 30 seconds.
You can use the **DbCommandTimeout** parameter to change the timeout value.

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
Restricts the search results when used with the **QueryType** parameter, when the ActiveDirectory value or the WorkGroup value is specified.
Do not use the **MachineFilter** parameter when you specify the Manual value for the **QueryType** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Password
Provides a password if the environment to be checked for products is password-protected.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueryType
Defines what kind of query to use to find the computers.
The following values apply to the **QueryType** parameter:

-- Manual: When you use this value, you can manually enter a computer IP address or name.
-- ActiveDirectory: When you used this value, dep_nextref_vamt searches the Active Directory domain.
-- Workgroup: When you use this value, dep_nextref_vamt searches the specified workgroup.
-- LDAP: When you use this value, you can supply a Lightweight Directory Access Protocol (LDAP) query to search for computers that the meet specified conditions. For example, you can use this value in a script to search for new computers that were added to the network within a certain time frame.

```yaml
Type: DiscoveryType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -QueryValue
The **QueryValue** parameter is required when the **QueryType** parameter is declared.
The **QueryValue** parameter supplies the following values for the specified QueryType:

-- If QueryType is Manual, QueryValue is the IP address or name of the computer.
-- If QueryType is ActiveDirectory, QueryValue is the name of Active Directory domain.
-- If QueryType is Workgroup, QueryValue is the name of the workgroup.
-- If QueryType is LDAP, QueryValue is an LDAP query to search for computers that meet the specified conditions. For example, you can use this value in a script to search for new computers that were added to the network within a certain time frame.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Username
Provides a user name if the environment to be checked for products is password-protected.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

