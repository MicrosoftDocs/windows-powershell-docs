---
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
ms.assetid: E47810FF-1046-4C1D-BD9B-692667C9B996
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
online version: 
schema: 2.0.0
---

# Get-DAEntryPointTableItem

## SYNOPSIS
Retrieves the list of entry points that have been configured for DirectAccess.

## SYNTAX

### ByPolicyStore (Default)
```
Get-DAEntryPointTableItem [-EntryPointName <String[]>] [-State <State[]>] [-PolicyStore <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByGpoSession
```
Get-DAEntryPointTableItem [-EntryPointName <String[]>] [-State <State[]>] [-GPOSession <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
**Get-DAEntryPointTableItem** retrieves the list of entry points that have been configured for DirectAccess. 
Entry points contain information about the IP addresses to use for connectivity, the IP-HTTPs profile, and other elements that enable connectivity for multisite DirectAccess.

You can use **Get-DAEntryPointTableItem** to retrieve the list from Group Policy Objects or the local computer's active store.

## EXAMPLES

### Example: Retrieve a list of entry points that are not active
```
PS C:\> Get-DAEntryPointTableItem -PolicyStore -ActiveStore -EntryPointName "Redmond" -State "NotSelected"
```

This cmdlet retrieves a list of entry points from the active store and filters the list to only display the entry points that are not active.

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

### -EntryPointName
Specifies the name of the entry point.
The entry point name is usually the friendly name of the location, such as "Redmond" or "Paris".

Specify the name of the entry point by using double quotes ( " ").

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GPOSession
Specifies the Group Policy session to send configuration information.
You can use **GPOSession** with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object.

**GPOSession** cannot be used in conjunction with **PolicyStore**.

```yaml
Type: String
Parameter Sets: ByGpoSession
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store into which the cmdlet adds the entry point.

To add the entry point to a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To add the entry point information to a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

**PolicyStore** cannot be used in conjunction with **GPOSession**.

The default value for **PolicyStore** is ActiveStore.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
This parameter is deprecated.

```yaml
Type: State[]
Parameter Sets: (All)
Aliases: 
Accepted values: NotSelected, AutomaticallySelected, ManuallySelected

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DASiteTableEntry
This cmdlet returns a CIM object that contains the DA entry point table item.

## NOTES

## RELATED LINKS

[New-DAEntryPointTableItem](./New-DAEntryPointTableItem.md)

[Set-DAEntryPointTableItem](./Set-DAEntryPointTableItem.md)

[Reset-DAEntryPointTableItem](./Reset-DAEntryPointTableItem.md)

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

[Remove-DAEntryPointTableItem](./Remove-DAEntryPointTableItem.md)

