---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrmembership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrMembership
---

# Get-DfsrMembership

## SYNOPSIS
Gets membership settings for members of replication groups.

## SYNTAX

```
Get-DfsrMembership [[-GroupName] <String[]>] [[-ComputerName] <String[]>] [[-DomainName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrMembership** cmdlet gets membership settings for members of replication groups.
Members of a replication group host replicated folders.
Use the **Add-DfsrMember** cmdlet to add a member to a group.
Adding a member creates a membership that contains default values.
You can use the current cmdlet to view settings for a membership, and use the Set-DfsrMembership to modify membership settings.

## EXAMPLES

### Example 1: Get all members of all groups
```
PS C:\> Get-DfsrMembership -GroupName * -ComputerName *
GroupName                   : RG01
ComputerName                : SRV01
FolderName                  : RF01
GroupDomainName             : corp.contoso.com
ComputerDomainName          : corp.contoso.com
Identifier                  : 9931c757-b252-4f04-8347-53575610c423
DistinguishedName           : CN=72c0c2bc-8a4e-4984-a23c-2efadc238724,CN=957751c2-15f0-429b-8688-44c22044226d,CN=DFSR-L
                              ocalSettings,CN=SRV01,OU=Domain Controllers,DC=corp,DC=contoso,DC=com
ContentPath                 : c:\rf01
PrimaryMember               : False
StagingPath                 : c:\rf01\DfsrPrivate\Staging
StagingPathQuotaInMB        : 4096
MinimumStagingFileSize      : Size256KB
ConflictAndDeletedPath      : c:\rf01\DfsrPrivate\ConflictAndDeleted
ConflictAndDeletedQuotaInMB : 660
ReadOnly                    : False
RemoveDeletedFiles          : False
Enabled                     : True
DfsnPath                    :
State                       : Normal

GroupName                   : RG01
ComputerName                : SRV02
FolderName                  : RF01
GroupDomainName             : corp.contoso.com
ComputerDomainName          : corp.contoso.com
Identifier                  : 6afad5e2-366c-4210-ae0f-e94a03b2b628
DistinguishedName           : CN=72c0c2bc-8a4e-4984-a23c-2efadc238724,CN=ce80cd1c-40dd-4e43-89fa-f3ad78988f9a,CN=DFSR-L
                              ocalSettings,CN=SRV02,OU=Domain Controllers,DC=corp,DC=contoso,DC=com
ContentPath                 : c:\rf01
PrimaryMember               : False
StagingPath                 : c:\rf01\DfsrPrivate\Staging
StagingPathQuotaInMB        : 4096
MinimumStagingFileSize      : Size256KB
ConflictAndDeletedPath      : c:\rf01\DfsrPrivate\ConflictAndDeleted
ConflictAndDeletedQuotaInMB : 660
ReadOnly                    : False
RemoveDeletedFiles          : False
Enabled                     : True
DfsnPath                    :
State                       : Normal
```

This command gets all member computers in all replication groups.
The console displays **DfsrMembership** objects for two member computers, named SRV01 and SRV02.
These two computers belong to the same group, named RG01.

## PARAMETERS

### -ComputerName
Specifies an array of names of replication member computers.
The cmdlet modifies membership settings for these member computers.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the domain of the current user.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet applies to all participating replication groups.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrMembership

## NOTES

## RELATED LINKS

[Set-DfsrMembership](./Set-DfsrMembership.md)

[Add-DfsrMember](./Add-DfsrMember.md)

