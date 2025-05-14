---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.BackgroundIntelligentTransfer.Management.dll-Help.xml
Module Name: BitsTransfer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitstransfer/get-bitstransfer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BitsTransfer
---

# Get-BitsTransfer

## SYNOPSIS
Gets the associated BitsJob object for an existing BITS transfer job.

## SYNTAX

### ListJobsByName (Default)
```
Get-BitsTransfer [[-Name] <String[]>] [-AllUsers] [<CommonParameters>]
```

### ListJobsById
```
Get-BitsTransfer [-JobId] <Guid[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-BitsTransfer** cmdlet retrieves a set of Background Intelligent Transfer Service (BITS) transfer jobs.
By default, the cmdlet returns the jobs that are owned by the current user.
However, if you have administrative credentials, you can specify the *AllUsers* parameter so that the command returns jobs that are owned by all users.
The returned jobs can be filtered by name or ID.
The jobs are represented by **BitsJob** objects.

## EXAMPLES

### Example 1: Get all BitsJob objects owned by the current user
```
PS C:\> Get-BitsTransfer

JobId                   DisplayName             TransferType            JobState                OwnerAccount
-----                   -----------             ------------            --------                ------------
07acbe90-7d25-4d05-a... TestJob2                Download                Suspended               DOMAIN01\user01
c0dd3d8c-c3a2-4562-8... TestJob1                Download                Transferred             DOMAIN01\user01
1ef8c549-7a92-4173-b... BitsJobTransfer         Download                Transferred             DOMAIN01\user01
2c8302d5-3f44-4981-8... BitsJobTransfer         Download                Transferred             DOMAIN01\user01
```

This command gets all the **BitsJob** objects that are owned by the current user.

### Example 2: Get the BitsJob object identified by job ID
```
PS C:\> Get-BitsTransfer -JobId C0DD3D8C-C3A2-4562-8324-80B19224879C

JobId                   DisplayName             TransferType            JobState                OwnerAccount
-----                   -----------             ------------            --------                ------------
c0dd3d8c-c3a2-4562-8... TestJob1                Download                Transferred             DOMAIN01\user01
```

This command gets the **BitsJob** object that is identified by the specified job ID.

### Example 3: Get all BitsJob objects with a specific display name
```
PS C:\> Get-BitsTransfer -AllUsers -Name "*Microsoft*", "*Windows*"

JobId                   DisplayName             TransferType            JobState                OwnerAccount
-----                   -----------             ------------            --------                ------------
07acbe90-7d25-4d05-a... MicrosoftTest           Download                Suspended               DOMAIN01\user01
c0dd3d8c-c3a2-4562-8... WindowsTest             Download                Transferred             DOMAIN01\user02
```

This command gets all the **BitsJob** objects, owned by all users, where the **DisplayName** property of the **BitsJob** object contains either Microsoft or Windows.
If the user does not have administrative credentials, this command returns an error because it uses the *AllUsers* parameter.

### Example 4: Get a BitsJob object identified by a specific display name
```
C:\PS>Get-BitsTransfer -Name "TestJob1"

JobId                   DisplayName             TransferType            JobState                OwnerAccount
-----                   -----------             ------------            --------                ------------
c0dd3d8c-c3a2-4562-8... TestJob1                Download                Transferred             DOMAIN01\user01
```

This command gets the **BitsJob** object that is identified by the specified display name.

## PARAMETERS

### -AllUsers
Indicates that this cmdlet gets BITS transfer jobs that are owned by all users.
If this parameter is not specified, only jobs that are owned by the current user are returned.
This parameter requires administrative credentials.

```yaml
Type: SwitchParameter
Parameter Sets: ListJobsByName
Aliases: all

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Specifies an array of BITS jobs by job ID.
Only the BITS jobs that include a job ID in this array are returned.
If **BitsJob** objects are piped to this cmdlet, their job IDs are used as the values of this parameter.

```yaml
Type: Guid[]
Parameter Sets: ListJobsById
Aliases: id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of BITS jobs based on job name.
Only BITS jobs with job names that match a name in this array are returned.
You can use standard wildcard characters  such as the asterisk (*) and the question mark (?).
Or, you can use a range operator such as"\[a-r\]".

For example, you can use any of the following commands:

`Get-BitsTransfer -Name "BITS*"`

`Get-BitsTransfer -Name "BITS Transfer"`

`Get-BitsTransfer -Name "BITS Transfe[a-r]"`

A combination of the wildcard character and range operators is also possible.

```yaml
Type: String[]
Parameter Sets: ListJobsByName
Aliases: n

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet accepts one or more **BitsJob** objects as input that populates the JobId parameter (based on the property name).

## OUTPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet generates the **BitsJob** objects that are associated with the retrieved BITS transfer jobs.

## NOTES

## RELATED LINKS

[Add-BitsFile](./Add-BitsFile.md)

[Complete-BitsTransfer](./Complete-BitsTransfer.md)

[Remove-BitsTransfer](./Remove-BitsTransfer.md)

[Resume-BitsTransfer](./Resume-BitsTransfer.md)

[Set-BitsTransfer](./Set-BitsTransfer.md)

[Start-BitsTransfer](./Start-BitsTransfer.md)

[Suspend-BitsTransfer](./Suspend-BitsTransfer.md)

