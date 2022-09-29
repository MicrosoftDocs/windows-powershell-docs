---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://learn.microsoft.com/powershell/module/msdtc/set-dtcadvancedsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DtcAdvancedSetting

## SYNOPSIS
Sets DTC instance specific properties in the registry.

## SYNTAX

```
Set-DtcAdvancedSetting [-CimSession <CimSession[]>] [-DtcName <String>] [-Subkey <String>]
 [-ThrottleLimit <Int32>] -Name <String> [-Type] -Value <String>
```

## DESCRIPTION
The **Set-DtcAdvancedSetting** cmdlet sets the Distributed Transaction Coordinator (DTC) instance specific properties in the registry.

## EXAMPLES

### Example 1: Modify a setting for the local DTC
```
PS C:\> Set-DtcAdvancedSetting -Name "AllowOnlySecureRpcCalls" -Type "DWORD" -Value "0" -DtcName "Local"
```

This command disables remote procedure call (RPC) security on the local DTC.

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
Specifies the DTC instance for which to set the DTC instance specific properties.

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
Specifies the name of the property to set.

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
Specifies the subkey name for the property to set.

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

### -Type
Specifies the registry type of the property to store.
The acceptable values for this parameter are:

- SZ
- DWORD

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: String, DWORD

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Specifies the value of the property to store.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcAdvancedSetting](./Get-DtcAdvancedSetting.md)

