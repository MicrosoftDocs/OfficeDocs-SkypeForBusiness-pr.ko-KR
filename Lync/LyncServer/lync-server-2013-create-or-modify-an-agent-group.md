---
title: 'Lync Server 2013: 에이전트 그룹 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Lync Server 2013에서 에이전트 그룹 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

다음 절차 중 하나를 사용 하 여 에이전트 그룹을 만들거나 수정 합니다.

<div>


> [!NOTE]  
> 관리자 (예: CsVoiceAdministrator)는 사용자가 에이전트 그룹에 할당할 수 있으려면 먼저 Enterprise Voice 및 Lync Server 사용자를 사용 하도록 설정 해야 합니다. 관리 되는 워크플로에 대 한 위임 된 응답 그룹 관리자 중 하나에 해당 하는 경우 에이전트 그룹을 만들고 관리 하는 워크플로에서 에이전트 그룹을 사용할 수 있습니다.



</div>

<div>


> [!IMPORTANT]  
> 사용자를 응답 그룹 에이전트로 지정 하는 경우 개인 정보 모드를 사용 하도록 설정한 경우 "RGS 현재 감시자" 연락처를 검색 하 여 해당 연락처 목록에 추가 해야 한다는 것을 알립니다. 개인 정보 모드를 사용 하도록 설정 했지만 대화 상대 목록에 "RGS 현재 상태 감시자"가 없는 에이전트는 응답 그룹에 대 한 통화를 받을 수 없습니다. 개인 정보 모드를 사용할 수 없는 에이전트는 영향을 받지 않습니다.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Lync Server 제어판을 사용 하 여 에이전트 그룹을 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 되는 워크플로에 대해 위임 된 응답 그룹 관리자 중 하나인 경우 그룹을 만들어 관리 하는 워크플로에서 사용할 수 있습니다.

    
    </div>

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **그룹**을 클릭 합니다.

4.  **그룹** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 새 에이전트 그룹을 만들려면 **새로**만들기를 클릭 합니다. 서비스 검색 **선택** 필드에서 그룹을 추가할 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 기존 에이전트 그룹을 수정 하려면 검색 필드에 에이전트 그룹 이름의 전부 또는 일부를 입력 합니다. 결과 목록에서 원하는 그룹을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **이름**에 에이전트 그룹의 식별 이름을 입력 합니다.

6.  **설명**에 그룹에 대 한 설명을 입력 합니다.

7.  **참가 정책**에서 다음 중 하나를 선택 하 여 그룹에 대 한 로그인 동작을 설정 합니다.
    
      - **비공식** 를 선택 하 여 그룹에 있는 에이전트가 그룹에 로그인 하거나 로그 아웃할 필요가 없도록 지정 합니다. 에이전트는 Lync Server 2013에 로그인 할 때 그룹에 자동으로 로그인 됩니다.
    
      - 그룹의 에이전트가 그룹에 로그인 하 고 로그 아웃 해야 하는 경우에는 **공식** 을 선택 하세요. 이 옵션을 선택 하면, 상담원은 Lync에서 메뉴 항목을 클릭 하 여 Internet Explorer를 열고 그룹 로그인 및 로그 아웃을 위한 웹 페이지 콘솔을 표시 합니다.

8.  **알림 시간 (초)** 에서 사용 가능한 다음 에이전트 (기본값은 20 초)에 대 한 호출을 제공 하기 전에 에이전트를 연결 하는 시간 (초)을 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 에이전트 알림 시간 설정은 180 초를 초과할 수 없습니다. 에이전트 경고 시간이 180 초를 초과 하는 경우 SIP 트랜잭션 타이머가 최대 대기 시간에 도달 하기 때문에 클라이언트 응용 프로그램에서 호출을 거부 합니다.

    
    </div>

9.  **라우팅 방법**에서 다음과 같이 그룹의 에이전트로 호출을 라우팅하는 방법을 선택 합니다.
    
      - 가장 오랫동안 유휴 상태 였던 에이전트 (Lync 서버에서 가장 오래 되었거나 **사용할 수** 없거나 **비활성** 상태인 경우)에 대해 먼저 새 통화를 제공 하려면 **가장 긴 유휴**상태를 클릭 합니다.
    
      - 사용 가능한 모든 에이전트에 동시에 새 통화를 제공 하려면, Parallel ( **병렬**)을 클릭 합니다. 전화를 수락하는 첫 번째 에이전트에게 전화가 전송됩니다.
    
      - 각 상담원에 대 한 새로운 통화를 차례로 제공 하려면 **라운드 로빈**을 클릭 합니다.
    
      - **에이전트** 목록에 나열 된 순서 대로 항상 에이전트에 대 한 새 통화를 제공 하려면 **Serial**을 클릭 합니다.
    
      - 현재 현재 상태에 관계 없이 Lync Server 2013 및 응답 그룹 응용 프로그램에 로그인 한 모든 에이전트에 새 통화를 제공 하려면 **전화 교환을**클릭 합니다. Lync 2010 수행자 에이전트로 구성 된 사용자는 대기 중인 모든 통화를 표시 하 고 모든 순서에 따라 대기 통화에 응답할 수 있습니다. 다른 Lync 2010 수행자 사용자에 게 더 이상 통화가 표시 되지 않는 이후 통화가 수락 된 첫 번째 상담원에 게 전화가 전송 됩니다.

10. **에이전트**에서 에이전트 목록을 만드는 방법을 지정 합니다.
    
      - 에이전트의 사용자 지정 목록을 사용 하려면 **에이전트의 사용자 지정 그룹 정의**를 클릭 하 고 다음 중 하나를 수행 합니다.
        
          - 에이전트 그룹에 사용자를 추가 하려면 **선택을**클릭 한 다음 **에이전트 검색 선택** 필드에이 그룹에 추가 하려는 사용자의 이름 전체 또는 일부를 입력 하 고 **찾기를**클릭 합니다. 결과 에이전트 목록에서 사용자를 클릭 한 다음 **확인**을 클릭 합니다.
        
          - 에이전트 그룹에서 사용자를 제거 하려면 에이전트 목록에서 제거 하려는 사용자를 클릭 한 다음 **제거**를 클릭 합니다.
        
          - 라운드 로빈 라우팅 또는 직렬 라우팅 중 하나를 사용 하는 그룹에서 에이전트가 제공 하는 호출 순서를 변경 하려면 에이전트 목록에서 사용자를 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.
    
      - Microsoft Exchange Server 배포 목록을 에이전트 그룹으로 사용 하려면 **기존 전자 메일 그룹 사용**을 클릭 한 다음 **메일 그룹 주소**에 메일 그룹의 전자 메일 주소를 입력 합니다 (예: NetworkSupport@contoso.com).
        
        전자 메일 그룹을 사용 하는 경우에는 다음과 같은 제약 조건이 적용 됩니다.
        
          - 에이전트 그룹에 대해 여러 메일 그룹을 선택할 수는 없습니다. 각 그룹은 하나의 메일 목록만 지원 합니다.
        
          - 메일 그룹에 하나 이상의 메일 그룹이 포함 된 경우에는 중첩 된 메일 그룹의 구성원이 에이전트 목록에 추가 되지 않습니다.
        
          - 직렬 또는 라운드 로빈 라우팅이 선택 되어 있으면 서버는 라우팅 메서드에 따라 적절 한 에이전트에 대 한 수신 전화를 제공 하 고 배포 목록에 에이전트가 나열 되는 순서에 따라 연결 합니다.
        
          - 메일 그룹에 Lync Server 2010을 사용할 수 있는 사용자가 포함 되어 있지만 Enterprise Voice가 설정 되어 있지 않으면 에이전트 그룹에 dysfunctional 에이전트로 추가 됩니다. 메일 그룹의 모든 구성원에 게 해당 사용자 계정에 대 한 Enterprise Voice가 설정 되어 있는지 확인 합니다.
        
        <div>
        

        > [!IMPORTANT]  
        > 전자 메일 그룹을 사용 하는 경우 숨겨진 구성원 또는 숨겨진 목록이 응답 그룹 관리자 또는 사용자에 게 표시 될 수 있습니다.

        
        </div>
        
        숨겨진 멤버 자격 또는 숨겨진 목록은 다음과 같이 표시 될 수 있습니다.
        
          - 구성원 자격이 숨겨지고 응답 그룹 관리자가 배포 목록을 에이전트 목록에 지정 하도록 메일 그룹을 구성한 경우 사용자가 해당 구성원을 확인할 수 있습니다.
        
          - 메일 그룹이 Exchange 전체 주소 목록에서 숨겨지도록 구성 되어 있는 경우 응답 그룹 관리자가 배포 목록을 보고 해당 사용자 권한이 있는 경우이를 에이전트 목록에 할당할 수 있습니다. 관리자에 게 적절 한 사용자 권한 및 사용 권한이 없는 경우에도 사용 권한이 필요 합니다.

11. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Windows PowerShell을 사용 하 여 에이전트 그룹을 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  New **-CsRgsAgentGroup** 를 사용 하 여 새 에이전트 그룹을 만듭니다. **Set-CsRgsAgentGroup** 를 사용 하 여 기존 에이전트 그룹을 수정 합니다. 명령줄에서 다음을 실행 합니다.
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    예를 들면 다음과 같습니다.
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > 에이전트 알림 시간 설정은 180 초를 초과할 수 없습니다. 에이전트 알림 시간이 180 초 보다 크면 SIP 트랜잭션 타이머가 최대 대기 시간에 도달 하기 때문에 클라이언트 응용 프로그램이 호출을 거부 합니다.

    
    </div>

4.  에이전트 그룹이 생성 되었는지 확인 합니다. 런
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 에이전트 그룹 삭제](lync-server-2013-delete-an-agent-group.md)  


[Lync Server 2013에서 응답 그룹 에이전트 그룹 관리](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[새로운 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

