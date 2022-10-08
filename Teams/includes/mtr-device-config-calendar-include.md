
사용자가 Teams 룸에서 모임을 보다 쉽게 예약할 수 있도록 Exchange Online 회의실 목록과 장소를 만들 수 있습니다. 

Exchange 회의실 목록 및 Outlook 위치는 Outlook의 회의실 찾기에 표시되는 리소스 계정(및 연결된 Teams 룸)을 제어하는 데 사용됩니다. 회의실 찾기는 사용자가 가까운 회의실을 찾고, 예약할 수 있으며, 디스플레이 가용성과 같은 다른 기준을 충족하는 데 도움이 되는 Outlook 기능입니다.

회의실 목록은 의미 있는 방식으로 리소스 계정(따라서 연결된 Teams 룸)을 그룹화할 수 있는 특별한 유형의 Exchange 메일 그룹입니다. 예를 들어 캠퍼스의 각 건물에 있는 모든 회의실에 대한 회의실 목록을 만들 수 있습니다.

Outlook Places를 사용하면 리소스 계정 및 해당 Teams 룸에 대한 특정 특성을 설정할 수 있습니다. 설정할 수 있는 몇 가지 특성은 다음과 같습니다.

- 건물
- 도시
- 용량
- 위치가 휠체어에 액세스할 수 있는지 여부
- 오디오, 비디오 및 표시 이름

사용자가 선택한 회의실 목록과 장소 특성의 조합을 사용하여 Outlook의 회의실 찾기에는 예약에 사용할 수 있는 회의실 목록이 표시됩니다. 회의실 목록 및 장소를 최대한 활용하려면 건물과 같은 장소 특성에 따라 회의실 목록을 만듭니다. 예를 들어 각 자원 계정에 대한 도시 및 건물 위치 특성을 설정한 다음 각 자원 계정을 건물 회의실 목록에 추가합니다. 사용자가 예약할 회의실을 선택하려고 하면 Outlook에는 각 도시에서 사용할 수 있는 도시 목록과 회의실 목록이 표시됩니다.

> [!IMPORTANT]
> 각 리소스 계정에는 해당 위치 특성이 설정되어 있어야 합니다. 이러한 특성, 특히 도시, 건물 및 용량이 설정되지 않은 경우 해당 객실은 객실 목록에 포함되더라도 예약에 사용할 수 있는 옵션으로 표시되지 않습니다.

회의실 목록을 만들려면 [회의실 만들기 목록](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list)의 지침을 따릅니다.

리소스 계정에 대한 위치 특성을 구성하려면 [Set-Place](/powershell/module/exchange/set-place)를 참조하세요.