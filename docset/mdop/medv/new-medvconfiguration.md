---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Medv.Administration.Commands.Configuration.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: New-MedvConfiguration
---

# New-MedvConfiguration

## SYNOPSIS
Creates an object that contains configuration settings for MED-V.

## SYNTAX

```
New-MedvConfiguration [-DiagEventLogLevel {NONE | ERROR | WARNING | INFORMATION | DEBUG}] [-ForceDefaults [<SwitchParameter>]]
 [-FtsAddUserToAdminGroupEnabled <Boolean>] [-FtsComputerNameMask <String>] [-FtsDeleteVMStateTimeout <Int32>]
 [-FtsDetachVfdTimeout <Int32>] [-FtsDialogUrl <String>] [-FtsExplorerTimeout <Int32>]
 [-FtsFailureDialogMsg <String>] [-FtsLogFilePaths <String[]>] [-FtsMaxPostponeTime <Int32>]
 [-FtsMaxRetryCount <Int32>] [-FtsMode {ATTENDED | UNATTENDED | SILENT}]
 [-FtsNonInteractiveRetryTimeoutInc <Int32>] [-FtsNonInteractiveTimeout <Int32>]
 [-FtsPostponeUtcDateTimeLimit <String>] [-FtsRetryDialogMsg <String>] [-FtsSetComputerNameEnabled <Boolean>]
 [-FtsSetJoinDomainEnabled <Boolean>] [-FtsSetMachineObjectOUEnabled <Boolean>]
 [-FtsSetRegionalSettingsEnabled <Boolean>] [-FtsSetUserDataEnabled <Boolean>] [-FtsStartDialogMsg <String>]
 [-FtsTaskCancelTimeout <Int32>] [-FtsTaskVMTurnOffTimeout <int>] [-FtsUpgradeTimeout <int>]
 [-UxAppPublishingEnabled <Boolean>] [-UxAudioSharingEnabled <Boolean>] [-UxClipboardSharingEnabled <Boolean>]
 [-UxCredentialCacheEnabled <Boolean>] [-UxDialogTimeout <Int32>] [-UxHideVmTimeout <Int32>]
 [-UxLogonStartEnabled <Boolean>] [-UxPrinterSharingEnabled <Boolean>] [-UxRebootAbsoluteDelayTimeout <Int32>]
 [-UxRedirectUrls <string[]>] [-UxShowExit <bool>] [-UxSmartCardLogonEnabled <Boolean>]
 [-UxSmartCardSharingEnabled <Boolean>] [-UxUSBDeviceSharingEnabled <Boolean>]
 [-VmCloseAction {HIBERNATE | SHUTDOWN | TURN-OFF}] [-VmGuestMemFromHostMem <Int32[]>]
 [-VmGuestUpdateDuration <Int32>] [-VmGuestUpdateTime <String>] [-VmHostMemToGuestMem <Int32[]>]
 [-VmHostMemToGuestMemCalcEnabled <Boolean>] [-VmMemory <Int32>] [-VmMultiUserEnabled <Boolean>]
 [-VmNetworkingMode {BRIDGED | NAT}] [-VmTaskTimeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-MedvConfiguration** cmdlet creates an object that contains configuration settings for Microsoft Enterprise Desktop Virtualization (MED-V).
You can use the **Export-MedvConfiguration** cmdlet to save the settings to a registry file that has the .reg file name extension.
That file can be packaged with a MED-V workspace or imported into the registry of a MED-V computer.

This cmdlet creates a **MedvConfiguration** object.
You can modify the settings in that object directly.

If you do not specify a setting, **Export-MedvConfiguration** does not export that setting to the registry file.
When you apply settings to a MED-V client, if a setting is not specified, the client uses the default value.

## EXAMPLES

### Example 1: Create a configuration object
```
C:\PS>New-MedvConfiguration -UxLogonStartEnabled $True -VmCloseAction HIBERNATE
DiagEventLogLevel                   :
FtsAddUserToAdminGroupEnabled       :
FtsComputerNameMask                 :
FtsDeleteVMStateTimeout             :
FtsDetachVfdTimeout                 :
FtsDialogUrl                        :
FtsExplorerTimeout                  :
FtsFailureDialogMsg                 :
FtsLogFilePaths                     :
FtsMaxPostponeTime                  :
FtsMaxRetryCount                    :
FtsMode                             :
FtsNonInteractiveRetryTimeoutInc    :
FtsNonInteractiveTimeout            :
FtsPostponeUtcDateTimeLimit         :
FtsRetryDialogMsg                   :
FtsSetComputerNameEnabled           :
FtsSetJoinDomainEnabled             :
FtsSetMachineObjectOUEnabled        :
FtsSetRegionalSettingsEnabled       :
FtsSetUserDataEnabled               :
FtsStartDialogMsg                   :
FtsTaskCancelTimeout                :
FtsTaskVMTurnOffTimeout             :
FtsUpgradeTimeout                   :
UxAppPublishingEnabled              :
UxAudioSharingEnabled               :
UxClipboardSharingEnabled           :
UxCredentialCacheEnabled            :
UxDialogTimeout                     :
UxHideVmTimeout                     :
UxLogonStartEnabled                 : True
UxPrinterSharingEnabled             :
UxRebootAbsoluteDelayTimeout        :
UxRedirectUrls                      :
UxSmartCardLogonEnabled             :
UxSmartCardSharingEnabled           :
UxShowExit                          :
UxUSBDeviceSharingEnabled           :
VmCloseAction                       : HIBERNATE
VmGuestMemFromHostMem               :
VmGuestUpdateDuration               :
VmGuestUpdateTime                   :
VmHostMemToGuestMem                 :
VmHostMemToGuestMemCalcEnabled      :
VmMemory                            :
VmMultiUserEnabled                  :
VmNetworkingMode                    :
VmTaskTimeout                       :
```

This command creates a **MedvConfiguration** object.
The cmdlet sets **LogonStartEnabled** to $True and sets **CloseAction** to a value of HIBERNATE.

### Example 2: Export new object to a file
```
C:\PS>New-MedvConfiguration -UxLogonStartEnabled $True -VmCloseAction HIBERNATE | Export-MedvConfiguration -Path "c:\temp\medvsettings.reg"
```

This command creates a **MedvConfiguration** object, and then passes that object to the **Export-MedvConfiguration** cmdlet by using the pipeline operator.
That cmdlet saves the object as a .reg file.

### Example 3: Add redirection URLs
```
C:\PS>New-MedvConfiguration -UxRedirectUrls "http://webapp1/contoso.com","http://webapp2/contoso.com" | Export-MedvConfiguration -Path "c:\temp\redirUrls.reg"
```

This command creates a **MedvConfiguration** object that contains redirection for the browser in the guest virtual machine.
The command exports the configuration object to a file.

### Example 4: Add redirection URLs from a file
```
C:\PS>New-MedvConfiguration -UxRedirectUrls (Get-Content "url.txt") | Export-MedvConfiguration -Path "UpdatedUrls.reg"
```

This command gets a list of redirected URLs from the file named url.txt.
The command adds those URLs to a new configuration object, and then saves that object in a .reg file.

## PARAMETERS

### -DiagEventLogLevel
Specifies levels of information to log in the Event Log.
Valid values are: 

- None 
- Error 
- Warning 
- Information
- Debug 

Each warning level includes information from the prior levels.
For example, the Information event level includes both Warning and Error level events.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Log

Required: False
Position: Named
Default value: Warning
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceDefaults
Indicates that this cmdlet sets each setting to its default before it applies other settings.
This is not necessary in most cases because unspecified settings use the default.
If you specify this parameter, the cmdlet applies user-specified settings to the HKLM registry hive that is governed completely by the administrator.

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

### -FtsAddUserToAdminGroupEnabled
Indicates whether to automatically add the user to the Administrator group of the virtual machine.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AddAdmin

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsComputerNameMask
Specifies a mask used to create the computer name for the MED-V workspace.
Specify the `%username%` tag to insert the user name as part of the computer name.
Specify the `%hostname%` tag to insert the name of the host computer.
Capture a specific number of characters from `%hostname%` and `%username%` by using square brackets.
For example `%username%\[3\]` specifies the first three character of the user name.
The cmdlet replaces every `#` character in the mask with a random digit.
The cmdlet replaces a `*` character at the end of the mask by a random alphanumeric character.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CompMask

Required: False
Position: Named
Default value: MEDV*
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsDeleteVMStateTimeout
Specifies the time-out value, in seconds, when initial setup attempts to delete a virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DeleteTime

Required: False
Position: Named
Default value: 90
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsDetachVfdTimeout
Specifies the time-out value, in seconds, when initial setup attempts to detach the virtual floppy drive from the virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DetachTime

Required: False
Position: Named
Default value: 120
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsDialogUrl
Specifies a custom URL displayed in the initial setup dialog messages.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FtsUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsExplorerTimeout
Specifies the time-out value, in seconds, that the initial setup completion application waits for the Windows Explorer process prior to issuing the command to shut down the virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: MaxExplorerTime

Required: False
Position: Named
Default value: 900
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsFailureDialogMsg
Specifies a customizable message to display when initial setup fails.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FailMsg

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsLogFilePaths
Specifies an array of log files to collect during initial setup.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: SetupLog

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsMaxPostponeTime
Specifies the maximum number of hours that initial setup can be postponed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: MaxPostpone

Required: False
Position: Named
Default value: 120
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsMaxRetryCount
Specifies the maximum number of times initial setup can attempt to run.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: MaxRetry

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsMode
Specifies how initial setup interacts with the user.
Valid values are: 

- Attended.
Shows the virtual machine window during initial setup. 
- Unattended.
Hides the virtual machine windows during initial setup.
- Silent.
Hides all user interaction during initial setup.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Mode

Required: False
Position: Named
Default value: UnAttended
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsNonInteractiveRetryTimeoutInc
Specifies the amount of time, in minutes, by which to increase the **NonInteractive Timeout** value for each retry of the initial setup in Unattended or Silent mode.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: FtsTimeoutInc

Required: False
Position: Named
Default value: 15
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsNonInteractiveTimeout
Specifies the time-out value, in minutes, on the first attempt to perform initial setup in Unattended or Silent mode.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: FtsTimeout

Required: False
Position: Named
Default value: 45
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsPostponeUtcDateTimeLimit
Specifies the date and time, in UTC **DateTime** format, that initial setup can be postponed.
Specify this parameter in the format yyyy-mm-dd hh:mm with hours in 24 hour-clock format.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PostponeDate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsRetryDialogMsg
Specifies a message to display when initial setup fails and must retry.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RetryMsg

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsSetComputerNameEnabled
Indicates whether to update the **ComputerName** setting under the **\[UserData\]** section of the Sysprep.Inf file in the MED-V workspace according to the configured **ComputerNameMask**.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SetCompName

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsSetJoinDomainEnabled
Specifies whether to update the **JoinDomain** setting under the **\[Identification\]** section of the Sysprep.Inf file in the MED-V workspace should to match the settings on the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: JoinDomain

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsSetMachineObjectOUEnabled
Specifies whether to update the **MachineObjectOU** setting under the **\[Identification\]** section of the Sysprep.Inf file in the MED-V workspace to match the host computer.
If the value of **FtsSetJoinDomainEnabled** is not ENABLED, this parameter has no effect.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: MachineOU

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsSetRegionalSettingsEnabled
Specifies whether to update the settings under the **\[RegionalSettings\]** section and the **TimeZone** setting under the **\[GuiUnattended\]** section of the Sysprep.Inf file in the MED-V workspace to match the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SetRegion

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsSetUserDataEnabled
Specifies whether to update the **FullName** and the **OrgName** settings under the **\[UserData\]** section of the Sysprep.Inf file in the MED-V workspace to match the settings on the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SetUserData

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsStartDialogMsg
Specifies the message to display when initial setup is ready to start.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StartMsg

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsTaskCancelTimeout
Specifies the time-out value, in seconds, that initial setup waits for the virtual machine to respond to a cancel operation.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: CancelTime

Required: False
Position: Named
Default value: 30
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsTaskVMTurnOffTimeout
Specifies the time-out value, in seconds, that initial setup waits for the virtual machine to shut down.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: TurnOffTime

Required: False
Position: Named
Default value: 60
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtsUpgradeTimeout
Specifies the time-out value, in minutes, to use when trying to upgrade the MED-V agent software in a virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: UpgradeTime

Required: False
Position: Named
Default value: 15
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxAppPublishingEnabled
Indicates whether to enable application publishing from the MED-V workspace to the host computer.
If application publishing is enabled, applications in the MED-V workspace are published in the Start menu of the host.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AppPub

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxAudioSharingEnabled
Indicates whether to enable sharing of the audio I/O device between the MED-V workspace and the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Audio

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxClipboardSharingEnabled
Indicates whether to enable sharing of the clipboard between the MED-V workspace and the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Clipboard

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxCredentialCacheEnabled
Indicates whether to cache end user credentials.
If *UxSmartCardLogonEnabled* and *UxCredentialCacheEnabled* are both enabled, *UxSmartCardLogonEnabled* overrides *UxCredentialCacheEnabled*.

The end user domain credential is stored in a reversible format in the Windows Credential Manager.
As a result, an attacker could write a program that retrieves the password and could gain access to the user credentials.
You can lessen the risk to user credentials by disabling the storing of end-user credentials.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Cred

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxDialogTimeout
Specifies the amount of time, in seconds, for dialogs that prompt a user to postpone an action.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DialogTime

Required: False
Position: Named
Default value: 300
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxHideVmTimeout
Specifies time-out value, in minutes, that the full screen virtual machine window is hidden from the end user during a long login attempt.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: HideTime

Required: False
Position: Named
Default value: 30
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxLogonStartEnabled
Specifies whether to start the MED-V workspace when the user logs on to the host computer.
If you specify a value of $False, the MED-V workspace is started when the first MED-V workspace application is launched.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Logon

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxPrinterSharingEnabled
Indicates whether to enable sharing of printers between the MED-V workspace and the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Print

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxRebootAbsoluteDelayTimeout
Specifies the time-out value, in minutes, before MED-V restarts.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Reboot

Required: False
Position: Named
Default value: 1440
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxRedirectUrls
Specifies an array of URLs to redirect to the MED-V workspace.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Urls

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxShowExit
Indicates whether to show the Exit menu in the MED-V Host Agent tray icon.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ShowExit

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxSmartCardLogonEnabled
Indicates whether smart cards can be used to authenticate users to MED-V.
If *UxSmartCardLogonEnabled* and *UxCredentialCacheEnabled* are both enabled, *UxSmartCardLogonEnabled* overrides *UxCredentialCacheEnabled*.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SmartCardLogon

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxSmartCardSharingEnabled
Indicates whether to share smart cards between the MED-V workspace and the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SmartCard

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UxUSBDeviceSharingEnabled
Specifies whether to share USB devices between the MED-V workspace and the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: USB

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmCloseAction
Specifies the action of the virtual machine when the last MED-V application is closed.
Valid values are: 

- HIBERNATE 
- SHUTDOWN
- TURN-OFF 

If the **LogonStart** is enabled, the value of this parameter has no effect.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Close

Required: False
Position: Named
Default value: HIBERNATE
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmGuestMemFromHostMem
Specifies the amount of memory, in megabytes, for the MED-V workspace that sets the amount of random access memory (RAM) available to the MED-V workspace.
Valid values are: integers from 128 MB to 2048 MB.

Combined with **HostMemToGuestMem**, a lookup table is created to determine how much RAM to allocate on the MED-V workspace virtual machine.
The amount of RAM on the host computer is read to determine the nearest value, rounded down, in **HostMemToGuestMem**.
The cmdlet indexes this array at the same location to determine the RAM value of the virtual machine.

If **HostMemToVmMemCalcEnabled** is not enabled, the value that you specify for this parameter has no effect.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases: GuestMem

Required: False
Position: Named
Default value: 378 512 1024 1536 2048
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmGuestUpdateDuration
Specifies the number of minutes that MED-V should keep the MED-V workspace awake for updating, starting at the time contained in **GuestUpdateTime**.
Specify a value of zero to disable this feature.
Valid values are: 0 to 1440 minutes.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: UpdateDuration

Required: False
Position: Named
Default value: 240
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmGuestUpdateTime
Specifies the hour and minute when the MED-V workspace should wake up for updating.
Specify a time in the format hh:mm using 24-hour clock time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: UpdateTime

Required: False
Position: Named
Default value: 00:00
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmHostMemToGuestMem
Specifies an array of values, in megabtyes, for the MED-V workspace determined by the amount of RAM available on the host computer.
Combined with **GuestMemFromHostMem**, a lookup table is created to determine how much RAM to allocate on the MED-V workspace virtual machine.
Valid values are: integers from 1024 MB to 16384 MB.
The amount of RAM on the host computer is read and the nearest value in this list is used to index the **GuestMemFromHostMem** list.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases: HostMem

Required: False
Position: Named
Default value: 1024 2048 4096 8192 16384
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmHostMemToGuestMemCalcEnabled
Indicates whether to calculate the amount of memory allocated for the MED-V workspace from the amount of memory present on the host computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: MemCalc

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmMemory
Specifies the amount of RAM, in megabytes, allocated for the MED-V virtual machine.
Valid values are: integers from 128 MB to 2048 MB.
If **HostMemToVmMemCalc** is enabled, the value that you specify for this parameter has no effect.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Mem

Required: False
Position: Named
Default value: 512
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmMultiUserEnabled
Indicates whether multiple users share a single MED-V workspace.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: MultiUser

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmNetworkingMode
Specifies the type of network connection that the MED-V workspace uses.
Valid values are: NAT and BRIDGED.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Net

Required: False
Position: Named
Default value: NAT
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmTaskTimeout
Specifies a general time-out value, in seconds, that MED-V waits for a task such as shutdown to complete.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: TaskTime

Required: False
Position: Named
Default value: 600
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Medv.Administration.Commands.MedvConfiguration
This cmdlet generates a **MedvConfiguration** object that contains configuration settings.

## NOTES

## RELATED LINKS

[Export-MedvConfiguration](./Export-MedvConfiguration.md)


