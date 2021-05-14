---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://docs.microsoft.com/powershell/module/msmq/resume-msmqoutgoingqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Resume-MsmqOutgoingQueue

## SYNOPSIS
Resumes specified outgoing queues.

## SYNTAX

```
Resume-MsmqOutgoingQueue [-InputObject <OutgoingQueue[]>]
```

## DESCRIPTION
The **Resume-MsmqOutgoingQueue** cmdlet resumes all outgoing queues that are represented by the supplied **MsmqOutgoingQueue** objects.
This cmdlet returns the resumed **MsmqOutgoingQueue** objects.

## EXAMPLES

### Example 1: Resume an outgoing queue
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Resume-MsmqOutgoingQueue
```

This command resumes the outgoing queues that have wildcard named Order*.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects that represent the outgoing queues to be resumed.
This parameter accepts pipelined input.

```yaml
Type: OutgoingQueue[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MsmqOutgoingQueue.md)

[Get-MsmqOutgoingQueue](./Get-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

