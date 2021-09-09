---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# New-MaskingSet

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByFriendlyName (Default)
```
New-MaskingSet [-StorageSubSystemFriendlyName] <String[]> [-FriendlyName <String>]
 [-VirtualDiskNames <String[]>] [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>]
 [-DeviceNumbers <String[]>] [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-MaskingSet -StorageSubSystemUniqueId <String[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-MaskingSet -StorageSubSystemName <String[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-MaskingSet -InputObject <CimInstance[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
{{ Fill AsJob Description }}

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
{{ Fill CimSession Description }}

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

### -DeviceAccesses
{{ Fill DeviceAccesses Description }}

```yaml
Type: DeviceAccess[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ReadWrite, ReadOnly, NoAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumbers
{{ Fill DeviceNumbers Description }}

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

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: MaskingSetFriendlyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostType
{{ Fill HostType Description }}

```yaml
Type: HostMode
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorAddresses
{{ Fill InitiatorAddresses Description }}

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
{{ Fill InputObject Description }}

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

### -StorageSubSystemFriendlyName
{{ Fill StorageSubSystemFriendlyName Description }}

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

### -StorageSubSystemName
{{ Fill StorageSubSystemName Description }}

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
{{ Fill StorageSubSystemUniqueId Description }}

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StorageSubsystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPortAddresses
{{ Fill TargetPortAddresses Description }}

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

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

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

### -VirtualDiskNames
{{ Fill VirtualDiskNames Description }}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS
