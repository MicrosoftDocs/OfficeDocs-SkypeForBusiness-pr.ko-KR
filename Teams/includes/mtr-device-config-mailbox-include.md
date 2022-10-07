
리소스 계정이 모임 초대에 응답하는 방식과 처리 방식을 사용자 지정하여 Teams 룸 모임 환경을 개선할 수 있습니다. Exchange Online PowerShell을 사용하여 다음 리소스 계정 속성을 설정할 수 있습니다.

- **AutomateProcessing: `AutoAccept`** 모임 이끌이는 사람의 개입 없이 회의실 예약 결정을 직접 받습니다.

- **AddOrganizerToSubject: `$false`** 모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.

- **DeleteComments: `$false`** 들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다. 이는 외부 Teams 및 타사 모임을 처리하여 One Touch Join 환경을 제공하는 데 필요합니다.

- **DeleteSubject: `$false`** 들어오는 모임 요청의 제목을 유지합니다.

- **ProcessExternalMeetingMessages: `$true`** Exchange 조직 외부에서 발생하는 모임 요청을 처리할지 여부를 지정합니다. 외부 Teams 모임 및 [타사 모임에](/microsoftteams/rooms/third-party-join) 필요합니다.

- **RemovePrivateProperty: `$false`** 원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 대로 유지되도록 합니다.

- **AddAdditionalResponse: `$true`** AdditionalResponse 매개 변수로 지정된 텍스트가 모임 요청에 추가됩니다.

- **AdditionalResponse: "Microsoft Teams 회의실입니다!"** 모임 수락 응답에 추가할 추가 텍스트입니다.

이러한 속성을 구성하려면 Exchange Online PowerShell에 연결해야 합니다. 자세한 내용은 [Exchange Online PowerShell에 연결을](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true) 참조하세요.

Exchange Online PowerShell에 연결한 후 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing) cmdlet을 사용하여 리소스 계정에서 사서함 속성을 구성할 수 있습니다.

다음 예제에서는 리소스 계정에 대한 `ConferenceRoom01` 속성을 설정합니다.

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

