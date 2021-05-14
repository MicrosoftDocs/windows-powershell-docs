---
external help file: SyncShare.cdxml-help.xml
Module Name: SyncShare
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/syncshare/set-syncshare?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SyncShare
---

# Set-SyncShare

## SYNOPSIS
Modifies the settings for a sync share.

## SYNTAX

### Query (cdxml) (Default)
```
Set-SyncShare [-Name] <String[]> [-Description <String>] [-User <String[]>] [-InheritParentFolderPermission]
 [-MaxUploadFile <UInt64>] [-RequireEncryption <Boolean>] [-RequirePasswordAutoLock <Boolean>]
 [-FallbackEnterpriseID <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-SyncShare -InputObject <CimInstance[]> [-Description <String>] [-User <String[]>]
 [-InheritParentFolderPermission] [-MaxUploadFile <UInt64>] [-RequireEncryption <Boolean>]
 [-RequirePasswordAutoLock <Boolean>] [-FallbackEnterpriseID <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SyncShare** cmdlet modifies the settings for a sync share.

## EXAMPLES

### Example 1: Modify a sync share to enable inherited permissions
```
PS C:\> Set-SyncShare Share01 -KeepParentFolderPermission
```

This command modifies settings on the share named Share01, and sets **KeepParentFolderPermission** to enable the share to inherit permissions from the parent folder.

### Example 2: Modify the sync share to change the user group
```
PS C:\> Set-SyncShare Share01 -User "ContosoGroup"
```

This command modifies settings on the share named Share01, and sets the user group to ContosoGroup.

### Example 3: Modify a sync share to add a user group
```
PS C:\> $Current = Get-SyncShare Share01
PS C:\> Set-SyncShare Share01 -User $Current.user,"ContosoEngGroup"
PS C:\> Get-SyncShare Share01
ConflictResolutionPolicy : KeepLatest
Description              : 
DevicePolicy             : Share01
Enabled                  : True
ExclusiveAccessToUser    : False
Name                     : Share01
Path                     : K:\Share01
StagingFolder            : K:\EcsStagingArea\Share01
StagingQuota             : 1099511627776
StagingQuotaPerUser      : 10737418240
Type                     : User Data
User                     : {HRGroup, EngGroup}
UserFolderName           : %username%
PSComputerName           :
```

This example modifies settings on the share named Share01, and enables the user group named ContosoEngGroup to access the share.

The first command uses the Get-SyncShare cmdlet to retrieve the sync share for Share01, and assigns the results to the variable $Current.

The second command uses the Set-SyncShare cmdlet to modify the sync share and add the current user and the ContosoEngGroup to the list of users allowed to access the share.

The third command uses the Get-SyncShare cmdlet to verify the results.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

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

### -Description
Specifies a description for a sync share configuration.
The description appears in Server Manager and in Windows PowerShell® but is not visible to end users.
The description can have a maximum of a 150 characters.

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

### -FallbackEnterpriseID
Specifies the fallback Enterprise ID that the sync share uses if it cannot successfully query Active Directory® Domain Services (nextref_adds).
If the server cannot successfully query nextref_adds, the server uses the fully qualified domain name (FQDN) of the sync server as the fallback Enterprise ID unless you specify a different Enterprise ID by using this parameter.
The Enterprise ID is issued by the Work Folders client to encrypt data on the PC or device.

The Enterprise ID is typically constructed by querying nextref_adds for the primary SMTP address of the user, removing the username and ampersand (user@), and sending the remainder to the client as the Enterprise ID.
For example, EvanNarvaez@Contoso.com yields the contoso.com Enterprise ID.

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

### -InheritParentFolderPermission
Indicates that the sync share inherits the permissions of the parent folder.
If you specify this parameter, the user folder inherits permissions from the parent folder of the sync share, and administrators can access the data.
If you do not specify this parameter, by default each user is granted exclusive access to their user folder, and administrators have no access rights.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the SyncShare object to use as input to this cmdlet.
You can use this parameter, or you can use the pipeline operator to pass input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxUploadFile
Specifies the maximum file size, in bytes, that users can upload to the server.
The minimum value that you can specify is 1 MB.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the sync share.
The name that you specify has the following requirements: 

- The name must be unique on the sync server
- The name can have a maximum of 75 characters
- You cannot start or end a name with a space
- You cannot end a name with a period
- You cannot used a reserved name, such as COM1, LPT1, or NUL
- You cannot use the following characters: \<\>:\"/\\\\|?*

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RequireEncryption
Indicates whether the sync server requests that the contents of Work Folders be encrypted on each PC and device that accesses the sync share.

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

### -RequirePasswordAutoLock
Indicates whether the device meet the following policies: 

- Password minimum length of six characters
- Lock screen activates after a maximum of 15 minutes
- User account lockout after a maximum of 10 failed sign-in attempts

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies an array of security groups or users who are allowed to sync data with this sync share.
Add accounts or security groups in Security Accounts Manager (SAM) account format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: AllowedAccount, AllowedUser

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SyncShare
You can pass an array of SyncShare objects to the InputObject parameter by using the pipeline operator.

## OUTPUTS

### SyncShare
If you specify the **PassThru** parameter, this cmdlet outputs an object that represents the modified sync shares.

## NOTES

## RELATED LINKS

[Disable-SyncShare](./Disable-SyncShare.md)

[Enable-SyncShare](./Enable-SyncShare.md)

[Get-SyncShare](./Get-SyncShare.md)

[New-SyncShare](./New-SyncShare.md)

[Remove-SyncShare](./Remove-SyncShare.md)

