---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Read-ADRecoveryInformation
---

# Read-ADRecoveryInformation

## SYNOPSIS
Reads the BitLocker volume recovery information from an Active Directory for one or more computer volumes.

## SYNTAX

```
Read-ADRecoveryInformation [-IgnoreVolumeRecoveryPackage] [-After <DateTime>] [-Credential <PSCredential>]
 [-ResultPageSize <Int32>] [-SearchBase <String>] -Server <String> [-Recurse] [<CommonParameters>]
```

## DESCRIPTION
The **Read-ADRecoveryInformation** cmdlet gets BitLocker volume recovery data from an Active Directory computer object and child **msFVE-RecoveryInformation** objects or performs a search to retrieve this data from multiple computer objects.
The *Server* parameter is required and specifies the server hosting a Lightweight Directory Access Protocol (LDAP) service for the target domain.
The search for computer objects is not recursive.
A search is performed in the Active Directory path specified by the *SearchBase* parameter.
The default value of the *SearchBase* parameter is the default naming context of the target domain.
You can also use the *SearchBase* parameter to set the full path of a single computer object.

## EXAMPLES

### Example 1: Get RecoveryInformation records for each computer object
```
PS C:\>$Cred = Get-Credential Contoso\adpullreader
PS C:\> Read-ADRecoveryInformation -Server "Contoso.com" -Credential $Cred -SearchBase "OU=Workstations,OU=Machines,DC=contoso,DC=com"
Computer                  : User1-pc.contoso.com
Time                      : 03/31/2015 20:42:45
VolumeID                  : a750976a-1d28-4180-a164-b2315f97bde1
RecoveryPasswordID        : 808d0925-8044-4533-8f8c-411d6c020039
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN= USER1-PC,OU=Workstations,OU=Machines,DC=contoso,DC=com

Computer                  : User2-pc.contoso.com
Time                      : 11/21/2013 04:38:33
VolumeID                  : a750976a-1d28-4180-a164-b2315f97bde1
RecoveryPasswordID        : 808d0925-8044-4533-8f8c-411d6c020039
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN=USER2-PC,OU=Workstations,OU=Machines,DC=contoso,DC=com
```

This command queries for RecoveryInformation records corresponding to each computer object in the container "OU=Workstations,OU=Machines,DC=contoso,DC=com" (not including sub-containers).

The Active Directory query is performed as the user Contoso.com\adpullreader.

Each returned record is an instance of **PsObject** with name of the computer, the volume's id, recovery password id, recovery password, recovery package and the time at which it was backed up to Active Directory (if known).

### Example 2: Get RecoveryInformation records for computer objects in a specified container recursively
```
PS C:\>Read-ADRecoveryInformation -Server "Contoso.com" -SearchBase "OU=Machines,DC=contoso,DC=com" -Recurse
Computer                  : User3-pc.contoso.com
Time                      : 03/31/2015 20:42:45
VolumeID                  : 14b2bc13-8061-4e82-a8e7-497fedebd978
RecoveryPasswordID        : 83a2c59b-5673-4dfc-930f-3dcbacab1cbc
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN=USER3-PC,OU=LAPTOPS,OU=Machines,DC=contoso,DC=com

Computer                  : User1-pc.contoso.com
Time                      : 04/31/2015 20:40:30
VolumeID                  : a750976a-1d28-4180-a164-b2315f97bde1
RecoveryPasswordID        : 808d0925-8044-4533-8f8c-411d6c020039
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN= USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com
```

This command queries for RecoveryInformation records for each computer object in the container "OU=Machines,DC=contoso,DC=com" and child containers recursively.

The Active Directory query is performed under the cmdlet's process credentials.

Each returned record is an instance of **PsObject** with name of the computer, the volume's id, recovery password id, recovery password, recovery package and the time at which it was backed up to Active Directory (if known).

### Example 3: Get RecoveryInformation records for computer objects in a specified container after a specified date
```
PS C:\>Read-ADRecoveryInformation -Server Contoso.com -SearchBase "OU=Workstations,OU=Machines,DC=Contoso,DC=com" -After ([datetime]::Parse("09/01/2014 01:00:00"))
Computer                  : User3-pc.contoso.com
Time                      : 03/31/2015 20:42:45
VolumeID                  : 14b2bc13-8061-4e82-a8e7-497fedebd978
RecoveryPasswordID        : 83a2c59b-5673-4dfc-930f-3dcbacab1cbc
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN=USER3-PC,OU=LAPTOPS,OU=Machines,DC=Contoso,DC=com
```

This command queries for RecoveryInformation records corresponding to each computer object in the container "OU=Workstations,OU=Machines,DC=contoso,DC=com" (not including sub-containers).

Only RecoveryInformation data that might have been backed up to Active Directory after September 1, 2014 01:00:00 UTC will be retrieved.

The Active Directory query is performed under the cmdlet's process credentials.

Each returned record is an instance of PsObject with name of the computer, the volume's id, recovery password id, recovery password, recovery package and the time at which it was backed up to Active Directory (if known).

### Example 4: Get RecoveryInformation records for a distinguished computer in a specified container
```
PS C:\>Read-ADRecoveryInformation -Server "Contoso.com" -SearchBase "CN=USER1-PC,OU=Workstations,OU=Machines,DC=contoso,DC=com"
Computer                  : User1-pc.contoso.com
Time                      : 31/03/2015 20:42:45
VolumeID                  : a750976a-1d28-4180-a164-b2315f97bde1
RecoveryPasswordID        : 808d0925-8044-4533-8f8c-411d6c020039
RecoveryPassword          : System.Security.SecureString
RecoveryPackage           : {188, 1, 0, 0...} 
ComputerDistinguishedName : CN=USER1-PC,OU=Workstations,OU=Machines,DC=contoso,DC=com
```

This command queries the RecoveryInformation records for the computer object with the distinguished name: "CN= USER1-PC,OU=Workstations,OU=Machines,DC=contoso,DC=com"

The Active Directory query is performed under the cmdlet's process credentials.

Each returned record is an instance of PsObject with name of the computer, the volume's id, recovery password id, recovery password, recovery package, and the time at which it was backed up to Active Directory (if known).

### Example 5: Migrate Bitlocker volume recovery information from Active Directory to the MBAM databases in a specified domain
```
PS C:\>Read-ADRecoveryInformation -Server "Contoso.com" -Recurse | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

This command migrates all of the Bitlocker volume recovery information data from Active Directory to the MBAM databases in the contoso.com domain.

The write to MBAM is performed through the Hardware and Recovery service located on the mbam.contoso.com server machine.

The Active Directory query and the write to MBAM is performed under the credentials of the hosting cmdlet process.

## PARAMETERS

### -After
Specifies that the cmdlet reads volume recovery information from Active Directory with corresponding timestamps more recent than the specified data and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the domain account credentials in which this cmdlet operates.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IgnoreVolumeRecoveryPackage
Indicates that this cmdlet ignores the volume recovery package.

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

### -Recurse
Indicates that the cmdlet retrieves recovery information associated with the computer objects in the specified container and in all child containers.

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

### -ResultPageSize
Specifies the maximum number of objects the server should return in a single page of results.
The default is 1000, which is the default server MaxPageSize limit.
If you change the server MaxPageSize to a value less than 1000, that value will take precedence over this parameter.Changing this value can be useful to throttling network bandwidth and reducing the Lightweight Directory Access Protocol (LDAP) server memory footprint required to service this query.

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

### -SearchBase
Specifies the Active Directory path under which to perform a one level search for computer objects or the full path to a specific computer object. 
The default value of this parameter is the default naming context of the target domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: base

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: 
- Active Directory Lightweight Domain Services
- Active Directory Domain Services
- Active Directory Snapshot instance

You can specify the Active Directory Domain Services instance in one of the following ways: 
 Domain name values: 
- Fully qualified domain name
- NetBIOS name
Directory server values:  
- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PsObject
PropertyName               PropertyType      Example Value
Computer                      String                   "Server01.NA.Contoso.com"
VolumeID                      Guid
RecoveryPasswordID    Guid
RecoveryPassword        SecureString                  "111111-111111-111111-111111-111111-111111-111111-111111"
RecoveryPackage          byte\[\]
Time                              DateTime

## NOTES
* All arguments can be retrieved from input by property name.

## RELATED LINKS

[Read-ADTpmInformation](read-adtpminformation.md)

[Microsoft BitLocker Administration and Monitoring](/microsoft-desktop-optimization-pack/mbam-v25/)
