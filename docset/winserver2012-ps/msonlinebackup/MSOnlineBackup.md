---
Module Name: MSOnlineBackup
Module Guid: 78C21AAB-6F29-463A-B7F1-1EDCE58C73D3
Download Help Link: http://go.microsoft.com/fwlink/?LinkId=285762
Help Version: 3.2.0.0
Locale: en-US
ms.assetid: 28BAF54D-1B3B-4284-B4AD-537CD44483A5
---

# MSOnlineBackup Module
## Description
{{Manually Enter Description Here}}

## MSOnlineBackup Cmdlets
### [Add-OBFileSpec](./Add-OBFileSpec.md)
Adds the OBFileSpec object, which specifies the items to include or exclude from a backup, to the backup policy (OBPolicy object).

### [Get-OBAllRecoveryPoints](./Get-OBAllRecoveryPoints.md)
Shows the user a list of recovery points for each successful backup that was completed from a specific server.

### [Get-OBAlternateBackupServer](./Get-OBAlternateBackupServer.md)
Gets the array of OBAlternateBackupServer objects.

### [Get-OBCertificateListFromLocalStore](./Get-OBCertificateListFromLocalStore.md)
Gets the list of certificates from the local computer certificate store.

### [Get-OBFileSpec](./Get-OBFileSpec.md)
Gets the list of OBFileSpec objects associated with the specified backup policy (OBPolicy object).

### [Get-OBJob](./Get-OBJob.md)
Gets a list of operations from a server as OBJob objects.

### [Get-OBMachineSetting](./Get-OBMachineSetting.md)
Gets the OBMachineSetting object for the server.

### [Get-OBMachineUsage](./Get-OBMachineUsage.md)
Gets the amount of storage consumed on mob_name_1 by data backed-up from this server.

### [Get-OBNotification](./Get-OBNotification.md)
Gets array of OBNotification objects which are applicable for the server.

### [Get-OBPolicy](./Get-OBPolicy.md)
Gets the current backup policy set for the server.

### [Get-OBPolicyState](./Get-OBPolicyState.md)
Gets the PolicyState of the current backup policy.

### [Get-OBRecoverableItem](./Get-OBRecoverableItem.md)
Gets the array of OBRecoverableItem objects associated with the server.

### [Get-OBRecoverableSource](./Get-OBRecoverableSource.md)
Get the list of datasources recoverable from this server or the specified OBBackupServer object.

### [Get-OBRecoveryService](./Get-OBRecoveryService.md)
Gets the list of available vaults.

### [Get-OBRetentionPolicy](./Get-OBRetentionPolicy.md)
Gets the current retention policy for backups from the backup policy (OBPolicy object).

### [Get-OBSchedule](./Get-OBSchedule.md)
Gets the OBSchedule object, which includes the days of the week and times of day to create daily backups, for the specified OBPolicy object.

### [New-OBFileSpec](./New-OBFileSpec.md)
Creates a new OBFileSpec object based on the parameters that are specified.

### [New-OBPagingContext](./New-OBPagingContext.md)
Creates a new OBPagingContext object that is used in the Get-OBRecoverableItem cmdlet during searching and browsing through paginated recoverable items.

### [New-OBPolicy](./New-OBPolicy.md)
Generates an empty OBPolicy object.

### [New-OBRecoverableItem](./New-OBRecoverableItem.md)
Creates a new OBRecoverableItem for the given path.

### [New-OBRecoveryOption](./New-OBRecoveryOption.md)
Specifies the recovery options that will apply to all the recoverable items during recovery.

### [New-OBRetentionPolicy](./New-OBRetentionPolicy.md)
Creates a new OBRetentionPolicy specifying the number of days that the backup needs to be retained.

### [New-OBSchedule](./New-OBSchedule.md)
Creates a new OBSchedule object based on the days of the week and times of day to create daily backups.

### [Remove-OBFileSpec](./Remove-OBFileSpec.md)
Removes the list of items to include or exclude from a backup, as specified by the OBFileSpec object, from a backup policy (OBPolicy) object.

### [Remove-OBPolicy](./Remove-OBPolicy.md)
Removes the currently set backup policy (OBPolicy object).

### [Rename-OBVolume](./Rename-OBVolume.md)
Maps a backed up volume to its new name after the operating system has been reinstalled on the backed up server.

### [Set-OBMachineSetting](./Set-OBMachineSetting.md)
Sets a OBMachineSetting object for the server.

### [Set-OBPolicy](./Set-OBPolicy.md)
Sets the OBPolicy object as the backup policy that will be used for scheduled backups.

### [Set-OBPolicyState](./Set-OBPolicyState.md)
Sets the PolicyState of the current backup policy object.

### [Set-OBRetentionPolicy](./Set-OBRetentionPolicy.md)
Sets the retention policy for the backup policy (OBPolicy object).

### [Set-OBSchedule](./Set-OBSchedule.md)
Sets the OBSchedule object, which includes the days of the week and times of day to create daily backups, for the backup policy (OBPolicy object).

### [Start-OBBackup](./Start-OBBackup.md)
Starts a one-time backup operation based on the specified OBPolicy.

### [Start-OBRecovery](./Start-OBRecovery.md)
Recovers the array of OBRecoverableItem objects with the specified recovery options in the OBRecoverableOptions object.

### [Start-OBRegistration](./Start-OBRegistration.md)
Registers the current computer to mob_name_1.

### [Stop-OBJob](./Stop-OBJob.md)
Stops the specified backup or recovery job.

