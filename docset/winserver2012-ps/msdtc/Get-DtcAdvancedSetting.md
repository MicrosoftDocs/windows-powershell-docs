---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/get-dtcadvancedsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DtcAdvancedSetting

## SYNOPSIS
Queries the advanced setting for MSDTC in the registry.

## SYNTAX

```
Get-DtcAdvancedSetting [-CimSession <CimSession[]>] [-DtcName <String>] [-Subkey <String>]
 [-ThrottleLimit <Int32>] -Name <String>
```

## DESCRIPTION
The **Get-DtcAdvancedSetting** cmdlet gets the advanced setting for Microsoft Distributed Transaction Coordinator (MSDTC).
Use this cmdlet to query the advanced setting information stored in the registry.
You can query only one registry value at one time.
Specify a DTC instance by using the **DtcName** parameter.
If you do not specify an instance, the default value is Local.
The default registry location for advanced settings is HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDTC.

## EXAMPLES

### Example 1: Query an advanced setting
```
PS C:\>Get-DtcAdvancedSetting -Name "AccountName" -DtcName "Local" -Subkey "Security" 

NT AUTHORITY\NetworkService
```

This command gets the account name used by the local MSDTC instance.

## PARAMETERS

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

### -DtcName
Specifies the DTC instance for which to retrieve the DTC instance specific properties.

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

### -Name
Specifies the name of the property to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subkey
Specifies the subkey name for the property to get.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-DtcAdvancedSetting](./Set-DtcAdvancedSetting.md)

