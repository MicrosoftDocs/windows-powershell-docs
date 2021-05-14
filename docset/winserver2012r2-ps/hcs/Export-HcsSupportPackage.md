---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/export-hcssupportpackage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HcsSupportPackage
---

# Export-HcsSupportPackage

## SYNOPSIS
Bundles logs into a single .zip file.

## SYNTAX

```
Export-HcsSupportPackage -EncryptionPassphrase <SecureString> [-Path] <String> [-Credential <PSCredential>]
 [-PackageTag <String>] [-Include <ElementFlag>] [-IncludeArchived] [-MinimumTimestamp <DateTime>]
 [-MaximumTimestamp <DateTime>] [-Scope <ClusterScope>] [-NoSplit] [-SplitSizeBytes <Int64>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-HcsSupportPackage** cmdlet bundles the logs of each controller device into a .zip file.
This cmdlet creates one .zip file per controller.
Microsoft Customer Service and Support uses these logs to help troubleshoot the device.

This cmdlet uses an encryption passphrase to encrypt the package.
Share this passphrase with Customer Service and Support.

## EXAMPLES

### Example 1: Store bundled logs in a location
```
PS C:\> Export-HcsSupportPackage -Path "\\10.111.172.250\public" -Include Rttdump -Scope Controller 
cmdlet Export-HcsSupportPackage at command pipeline position 1
Supply values for the following parameters: 
EncryptionPassphrase: ****
Confirm EncryptionPassphrase: ****
3/3/2014 2:46:04 PM Connecting to '\\10.111.172.250\public'
3/3/2014 2:46:04 PM Gathering Rttdump
3/3/2014 2:46:04 PM Copying controller support package 'contoso-SIU0983164L5CHY-Controller0-2014-03-03-14-46-03' to its
final location
\\10.111.172.250\public\engtest-SIU0983164L5CHY-2014-03-03-14-46-03
```

This command gathers logs into a support package, and then stores that package in the specified path.
The cmdlet gathers only the logs defined by the **Include** parameter.
The command specifies a value of Controller for the **Scope** parameter, so the command gets logs from the local node only.

### Example 2: Store bundled logs in a location that requires credentials
```
PS C:\>Export-HcsSupportPackage -Path "\\10.111.172.250\restricted\davidchew" -Credential "contoso\dchew" -Include Rttdump -Scope Controller
cmdlet Export-HcsSupportPackage at command pipeline position 1
Supply values for the following parameters: 
EncryptionPassphrase: ****
Confirm EncryptionPassphrase: ****
3/3/2014 2:51:29 PM Connecting to '\\10.111.172.250\restricted\dchew'
3/3/2014 2:51:29 PM Gathering Rttdump
3/3/2014 2:51:30 PM Copying controller support package 'contoso-SIU0983164L5CHY-Controller0-2014-03-03-14-51-29' to its final location
\\10.111.172.250\restricted\dchew\contoso-SIU0983164L5CHY-2014-03-03-14-51-29
```

This command gathers logs into a support package, and then stores that package in the specified path.
The path requires you to supply credentials in order to save the file there.
Like the previous example, this command specifies the **Include** and **Scope** parameters.

When you run this command, a dialog prompts you for your password.
After you enter your password, the console displays output.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object.
Specify a credential that has write permission for the location that the **Path** parameter specifies.
To obtain a **PSCredential** object, use the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
For more information, type `Get-Help Get-Credential`.

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

### -EncryptionPassphrase
Specifies a passphrase, as a secure string.
The cmdlet encrypts the support package by using the passphrase.
For Customer Service and Support staff to read the file, you must provide them with the passphrase.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet does not prompt you for confirmation of the encryption passphrase.

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

### -Include
Specifies an element flag.
This parameter determines which logs to include in the support package.

```yaml
Type: ElementFlag
Parameter Sets: (All)
Aliases: 
Accepted values: None, RegistryKeys, EtwLogs, PeriodicEtwLogs, LogFiles, DumpLog, StackDumps, FullDumps, MiniDumps, ClusterManagementLog, XutilDdump, XutilLogdump, BmcLogs, Rttdump, ClusterLog, UpdateLogs, CbsLogs, StorageCmdlets, ClusterCmdlets, ConfigurationCmdlets, KernelDump, Performance, MdsAgentLogs, NetworkCmdlets, NetworkCmds, MgmtSvcLogs, PeriodicMgmtSvcLogs, Default, NonDefault, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeArchived
Indicates that the cmdlet includes archived logs.

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

### -MaximumTimestamp
{{Fill MaximumTimestamp Description}}

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTimestamp
Specifies the earliest time to include as a **DateTime** object.
To obtain a **DateTime** object, use the Get-Datehttp://go.microsoft.com/fwlink/?LinkID=293966 cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSplit
{{Fill NoSplit Description}}

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

### -PackageTag
Specifies the folder of the support package.
The cmdlet adds the folder in the folder that the **Path** parameter specifies.
If you do not specify this parameter, the cmdlet uses the default value of \[appliance name\]-\[current date and time:yyyy-MM-dd-HH-mm-ss\].

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

### -Path
Specifies the network location where the cmdlet stores the support package.

If you have trouble accessing a network share by specifying a name (for example, \\\\mysharehost\temp\\), try accessing it by IP address instead (for example, \\\\192.168.0.25\temp\\).
Because this device is not joined to a domain, accessing network shares by name does not always work, depending on the configuration of your network.
The device cannot communicate over IPSEC enabled networks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope
Specifies the scope.
The acceptable values for this parameter are:

- Cluster.
Generate a support package for both nodes.
This is the default. 
- Controller.
Generate a support package for the local node only.

```yaml
Type: ClusterScope
Parameter Sets: (All)
Aliases: 
Accepted values: Cluster, Controller

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SplitSizeBytes
{{Fill SplitSizeBytes Description}}

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291)

[Get-Date](https://go.microsoft.com/fwlink/?LinkID=293966)

[Enable-HcsSupportAccess](./Enable-HcsSupportAccess.md)

