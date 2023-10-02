---
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
Module Name: DirectAccessClientComponents
online version: https://learn.microsoft.com/powershell/module/directaccessclientcomponents/set-daentrypointtableitem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DAEntryPointTableItem

## SYNOPSIS
Modifies the configuration of a DirectAccess entry point stored in a Group Policy object.

## SYNTAX

### ByPolicyStore (Default)
```
Set-DAEntryPointTableItem [-EntryPointName <String[]>] -PolicyStore <String> [-ADSite <String>]
 [-EntryPointRange <String[]>] [-TeredoServerIP <String>] [-EntryPointIPAddress <String>] [-GslbIP <String>]
 [-IPHttpsProfile <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByGpoSession
```
Set-DAEntryPointTableItem [-EntryPointName <String[]>] -GPOSession <String> [-ADSite <String>]
 [-EntryPointRange <String[]>] [-TeredoServerIP <String>] [-EntryPointIPAddress <String>] [-GslbIP <String>]
 [-IPHttpsProfile <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-DAEntryPointTableItem -InputObject <CimInstance[]> [-ADSite <String>] [-EntryPointRange <String[]>]
 [-TeredoServerIP <String>] [-EntryPointIPAddress <String>] [-GslbIP <String>] [-IPHttpsProfile <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Set-DAEntryPointTableItem** modifies an entry point configuration that is stored in a Group Policy object (GPO).
You must specify the name of the GPO in which the DirectAccess entry point configuration is stored.

## EXAMPLES

### Example 1: Modify an entry point
```
PS C:\> Set-DAEntryTableItem -EntryPointName "Paris" -GslbIP 131.107.0.1 -PolicyStore "Contoso\GPO1"
```

This cmdlet modifies the GSLB of the entry point named **Paris**.

### Example 2: Modify an entry point using an input object
```
PS C:\>$x = Set-DAEntryTableItem -EntryPointName "Paris" -PolicyStore "Contoso\GPO1" PS C:\>$x.GslbIP = 131.107.0.1 PS C:\>$x | Set-DAEntryTableItem
```

This cmdlet modifies an entry point named Paris by passing an input object on the pipeline.

## PARAMETERS

### -ADSite
Specifies the Active Directory Domain Services (AD DS) site name associated with the entry point.
When a client computer connects to an entry point, the computer becomes associated with the AD DS site specified.

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

### -EntryPointIPAddress
Specifies the IPv6 address of the entry point to use for connectivity.
The cmdlet fails if the IP address specified is not within the IP address range specified by **EntryPointRange**.

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

### -EntryPointName
Specifies the name of the entry point to modify.
The entry point name is usually the friendly name of the location, such as "Redmond" or "Paris".

Specify the name of the entry point by using double quotes ( " ").

```yaml
Type: String[]
Parameter Sets: ByPolicyStore, ByGpoSession
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntryPointRange
Specifies the IPv6 address range associated with computers connecting through this entry point.
Specify the IPv6 range in classless inter-domain routing (CIDR) notation.

The following is an example of an **EntryPointRange** entry: 
{2001:4898:e0:305d::100:1/128, 2001:4898:e0:305d::100:2/128, 2001:4898:e0:3084::/64}

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

### -GPOSession
Specifies the Group Policy session to send configuration information.
You can use **GPOSession** with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object.

**GPOSession** cannot be used in conjunction with **PolicyStore**.

```yaml
Type: String
Parameter Sets: ByGpoSession
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GslbIP
Specifies the IP address associated with the new entry point, if using DirectAccess in conjunction with global server load balancing (GSLB) site balancing.

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

### -IPHttpsProfile
Specifies the IPHTTPs profile name to be used for connectivity.
You specify the name of the profile in double quotes (" ").
**New-DAEntryPointTableItem** fails if the profile does not already exist in the GPO that contains the configuration.
For more information about IPHTTPs profiles, see the **NetIPHTTPsConfiguration** cmdlets in the **NetworkTransition** module.

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

### -InputObject
Specifies the name of the object which contains the entry point to modify.

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

### -PassThru
Sends items from an interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output.
However, to send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -PolicyStore
Specifies the policy store into which the cmdlet adds the entry point.

To add the entry point to a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To add the entry point information to a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

**PolicyStore** cannot be used in conjunction with **GPOSession**.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TeredoServerIP
Specifies the IP address of the Teredo server for the new entry point.

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

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DASiteTableEntry
This cmdlet returns a CIM object which contains the DA entry point table item.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-DAEntryPointTableItem](./New-DAEntryPointTableItem.md)

[Get-DAEntryPointTableItem](./Get-DAEntryPointTableItem.md)

[Reset-DAEntryPointTableItem](./Reset-DAEntryPointTableItem.md)

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

[Remove-DAEntryPointTableItem](./Remove-DAEntryPointTableItem.md)

