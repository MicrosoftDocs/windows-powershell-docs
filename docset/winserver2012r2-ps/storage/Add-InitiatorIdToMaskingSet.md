---
external help file: MaskingSet.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/storage/add-initiatoridtomaskingset?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-InitiatorIdToMaskingSet
---

# Add-InitiatorIdToMaskingSet

## SYNOPSIS
Adds an initiator ID to an existing masking set, granting the host associated with the initiator ID access to the virtual disk and target port resources defined in the masking set.

## SYNTAX

### ByFriendlyName (Default)
```
Add-InitiatorIdToMaskingSet [-MaskingSetFriendlyName] <String[]> [-InitiatorIds <String[]>]
 [-HostType <HostType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
Add-InitiatorIdToMaskingSet -MaskingSetUniqueId <String[]> [-InitiatorIds <String[]>] [-HostType <HostType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Add-InitiatorIdToMaskingSet -InputObject <CimInstance[]> [-InitiatorIds <String[]>] [-HostType <HostType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-InitiatorIdToMaskingSet** cmdlet adds an initiator ID to an existing masking set, granting the host associated with the initiator ID access to the virtual disk and target port resources defined in the masking set.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Adding an InitiatorID to a masking set by masking set object
```
PS C:\> $fcPorts = Get-InitiatorPort -CimSession Srv1 -ConnectionType FibreChannel
PS C:\> $maskingSet = Get-MaskingSet Cluster1MaskingSet
PS C:\> $fcPorts.NodeAddress 2000001b328d33cd2001001b32ad33cd
PS C:\> $maskingSet | Add-InitiatorIdToMaskingSet -InitiatorIds $fcPorts.NodeAddress
```

This example shows getting Fibre Channel initiator ports from the Srv1 computer, then getting the masking set object for the Cluster1MaskingSet, then enabling Srv1 access to all virtual disks defined in the masking set.

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

### -HostType
Specifies the host operating system or other host environmental factors that may influence the behavior that the storage system should have when showing a virtual disk to an initiator.

```yaml
Type: HostType
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorIds
Specifies one or more initiator IDs on which this cmdlet acts.
The initiator IDs will be added to this masking set.
Note: The initiator IDs do not need to be displayed in the output of the Get-InitiatorId cmdlet to be added to a masking set.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts a MaskingSet object from the pipeline as input.

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

### -MaskingSetFriendlyName
Specifies the friendly name of the masking set to which you want to add an initiator ID.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSetUniqueId
Specifies the unique ID of the masking set to which you want to add an initiator ID.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the masking set to which it added an initiator ID.
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe one or more MSFT_MaskingSet objects to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
If you specify the **Passthru** parameter, this cmdlet outputs an object that represents the masking set to which you added an initiator ID.

## NOTES

## RELATED LINKS

[Get-InitiatorID](./Get-InitiatorId.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

