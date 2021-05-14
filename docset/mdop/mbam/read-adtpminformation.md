---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Read-ADTpmInformation
---

# Read-ADTpmInformation

## SYNOPSIS
Reads Trusted Platform Module (TPM) owner information from Active Directory for one or more computers.

## SYNTAX

```
Read-ADTpmInformation [-After <DateTime>] [-Credential <PSCredential>] [-ResultPageSize <Int32>]
 [-SearchBase <String>] -Server <String> [-Recurse] [<CommonParameters>]
```

## DESCRIPTION
The **Read-ADTpmInformation** cmdlet gets Trusted Platform Module (TPM) owner information from an Active Directory computer object or linked **msTPM-InformationObject** or performs a search to retrieve this data for multiple computers. 
The *Server* parameter is required and specifies the Active Directory Domain Services instance to connect to.
The search is not recursive.
A search for computer objects is performed in the Active Directory path specified by the *SearchBase* parameter.
The default value of the *SearchBase* parameter is the default naming context of the target domain.
You can also set the *SearchBase* parameter to the full path of a single computer object.

## EXAMPLES

### Example 1: Get TmpOwnerInformation records from a specified server
```
PS C:\>$Cred = Get-Credential contoso\adpullreader
PS C:\> Read-ADTpmInformation -Server "Contoso.com" -Credential $Cred -SearchBase "OU=Workstations,OU=Machines,DC=Contoso,DC=com"
Computer                  : User1-pc.Contoso.com
Time                      : 23/09/2014 19:31:22
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com

Computer                  : User2-pc.Contoso.com
Time                      : 21/11/2013 04:38:33
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=User2-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com
```

This command queries for TpmOwnerInformation records corresponding to each computer object in the container "OU=Workstations,OU=Machines,DC=Contoso,DC=com" (not including sub-containers).

The Active Directory query is performed as a user named Contoso.com\adpullreader.

Each returned record is an instance of **PsObject** with name of the computer, the TPM owner authorization string, and the time at which it was backed up to Active Directory (if known).

### Example 2: Get TmpOwnerInformation records from a specified server recursively
```
PS C:\>Read-ADTpmInformation -Server "Contoso.com" -SearchBase "OU=Machines,DC=Contoso,DC=com" -Recurse
Computer                  : user3-pc.Contoso.com
Time                      : 09/23/2014 19:31:22
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=USER3-PC,OU=LAPTOPS,OU=Machines,DC=contoso,DC=com

Computer                  : user1-pc.Contoso.com
Time                      : 11/21/2013 04:38:33
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com
```

This command queries for TpmOwnerInformation records corresponding to each computer object in the container "OU=Workstations,OU=Machines,DC=Contoso,DC=com" and sub-containers.

The Active Directory query is performed under the cmdlet's process credentials.

Each returned record is an instance of **PsObject** with name of the computer, the TPM owner authorization string and the time at which it was backed up to Active Directory (if known).

### Example 3: Get TpmOwnerInformation records for each computer in a specified container after a specified date
```
PS C:\>Read-ADTpmInformation -Server "Contoso.com" -SearchBase "OU=Workstations,OU=Machines,DC=Contoso,DC=com" -After ([datetime]::Parse("09/01/2014 01:00:00"))
Computer                  : user3-pc.Contoso.com
Time                      : 09/23/2014 19:31:22
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=USER3-PC,OU=LAPTOPS,OU=Machines,DC=Contoso,DC=com
```

This command queries for TpmOwnerInformation records corresponding to each computer object in the container "OU=Workstations,OU=Machines,DC=contoso,DC=com" (not including sub-containers). 
The Active Directory query is performed under the cmdlet process's credentials.

Only TPMOwnerInformation that might have been backed up to Active Directory after September 1, 2014 01:00:00 UTC will be retrieved.

Each returned record is an instance of **PsObject** with name of the computer, the TPM owner authorization string and the time at which it was backed up to Active Directory (if known).

### Example 4: Get a TpmOwnerInformation record for a distinguished computer in a specified container
```
PS C:\>Read-ADTpmInformation -Server "Contoso.com" -SearchBase "CN=USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com"
Computer                  : user1-pc.Contoso.com
Time                      : 23/09/2014 19:31:22
TpmOwnerInformation       : System.Security.SecureString
ComputerDistinguishedName : CN=USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com
```

This command queries the TPMOwnerInformation record for the computer object with the distinguished computer name: "CN=USER1-PC,OU=Workstations,OU=Machines,DC=Contoso,DC=com".

The Active Directory query is performed under the cmdlet's process credentials.

The returned record is an instance of **PsObject** with name of the computer, the TPM owner authorization string and the time at which it was backed up to Active Directory (if known).

## PARAMETERS

### -After
Specifies that TPM owner passwords from Active Directory with corresponding timestamps more recent than the specified DateTime be read.

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

### -Recurse
Indicates that the cmdlet retrieves recovery information associated with the computer objects in the specified container and all child containers.

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
If you change the server MaxPageSize to a value less than 1000, that value will take precedence over this parameter.Changing this value can be useful to throttling network bandwidth and reducing the LDAP server memory footprint required to service this query.

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
Specifies an Active Directory path in which this cmdlet searches.

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
Specifies the name of the server in which to search for TPM information.
The value to use for \<server\> in the Lightweight Directory Access Protocol (LDAP) query "LDAP://\<server\>/...".

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

###  
Cmdlet parameters can be read from input by Property Name.

## OUTPUTS

### PsObject
Property Name                   PropertyType
Computer                           String
TpmOwnerInformation      SecureString
Time                                   DateTime

## NOTES

## RELATED LINKS

[Read-ADRecoveryInformation](read-adrecoveryinformation.md)

[Write-MbamTPMInformation](write-mbamtpminformation.md)

[Write-MbamRecoveryInformation](write-mbamrecoveryinformation.md)

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)


