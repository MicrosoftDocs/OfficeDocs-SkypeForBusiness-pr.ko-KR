---
title: 비즈니스용 Skype에서 에이전트 그룹 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 응답 그룹의 비즈니스용 Skype 서버에서 에이전트 그룹을 만들거나 수정하는 Enterprise Voice.
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837098"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>비즈니스용 Skype에서 에이전트 그룹 만들기 또는 수정
 
응답 그룹의 비즈니스용 Skype 서버에서 에이전트 그룹을 만들거나 수정하는 Enterprise Voice.
  
에이전트 그룹을 만들 때 그룹에 할당되는 에이전트를 선택하고 라우팅 방법 및 에이전트가 그룹에 로그인하고 그룹에서 로그아웃할 수 있는지 여부와 같은 추가 그룹 설정을 지정합니다. 
  
비즈니스용 Skype에 로그인하거나 그룹에서 로그인 및 아웃해야 하는 에이전트를 공식 에이전트라고 합니다. 공식 에이전트는 그룹에 로그인해야 그룹에 라우팅된 통화를 수신할 수 있습니다. 이 기능은 비상근직으로 그룹의 호출에 응답하는 에이전트에 유용할 수 있습니다. 공식 에이전트는 비즈니스용 Skype에서 메뉴 항목을 클릭하여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시하여 그룹에 로그인 및 그룹에서 로그인 및 아웃합니다.
  
그룹에 로그인하거나 그룹에서 로그아웃하지 않는 에이전트를 비공식 에이전트라고 합니다. 비공식 에이전트는 비즈니스용 Skype에 로그인할 때 그룹에 자동으로 로그인되며 그룹에서 로그인할 수 없습니다.
  
온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.
  
다음 절차 중 하나를 사용하여 에이전트 그룹을 만들거나 수정합니다.
  
> [!IMPORTANT]
> 사용자를 응답 그룹 에이전트로 할당할 때 해당 사용자가 개인 정보 보호 모드를 사용하도록 설정한 경우 "RGS Presence Watcher" 대화 상대를 검색하여 대화 상대 목록에 추가해야 합니다. 개인 정보 보호 모드를 사용하도록 설정한 에이전트의 대화 상대 목록에 "RGS Presence Watcher"가 없으면 응답 그룹으로 걸려 온 전화를 받을 수 없습니다. 개인 정보 보호 모드를 사용하도록 설정하지 않은 에이전트는 영향을 받지 않습니다. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>비즈니스용 Skype 서버 제어판을 사용하여 에이전트 그룹을 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
    > [!NOTE]
    > 관리되는 워크플로에 대해 위임된 응답 그룹 관리자 중 하나인 경우 그룹을 만들어 관리하는 워크플로에서 사용할 수 있습니다. 
  
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
3. 왼쪽 탐색 모음에서 **응답 그룹** 을 클릭한 다음 **그룹** 을 클릭합니다.
    
4. 그룹 **페이지에서** 다음 중 하나를 선택합니다.
    
   - 새 에이전트 그룹을 만들려면 새로 만들기를 **클릭합니다.** 서비스 **선택** 검색 필드에 그룹을 추가할 **ApplicationServer** 서비스의 이름 전체 또는 일부를 입력합니다. 서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인** 을 클릭합니다.
    
   - 기존 에이전트 그룹을 수정하려면 검색 필드에 에이전트 그룹의 이름을 전체 또는 일부분 입력합니다. 결과 목록에서 원하는 그룹을 클릭하고 편집을 **클릭한** 다음 세부 정보 **표시를 클릭합니다.**
    
5. **이름에** 에이전트 그룹의 식별 이름을 입력합니다.
    
6. **설명** 에 그룹에 대한 설명을 입력합니다.
    
7. **참가 정책** 에서 다음 중 하나를 선택하여 그룹의 로그인 동작을 설정합니다.
    
   - 그룹의 에이전트가 그룹에 로그인 및 로그아웃할 필요가 없도록 지정하려면 **비공식** 을 선택합니다. 에이전트는 비즈니스용 Skype에 로그인할 때 그룹에 자동으로 로그인됩니다.
    
   - 그룹의 에이전트가 그룹에 로그인 및 로그아웃해야 하도록 지정하려면 **공식** 을 선택합니다. 이 옵션을 선택하면 에이전트가 비즈니스용 Skype에서 메뉴 항목을 클릭하여 Internet Explorer 열고 그룹에 로그인 및 그룹에서 로그인하기 위한 웹 페이지 콘솔을 표시합니다.
    
8. **알림 시간(초)** 에 사용 가능한 다음 에이전트에 통화를 전달하기 전에 현재 에이전트에 신호음을 울릴 시간(초)을 지정합니다(기본값은 20초).
    
    > [!IMPORTANT]
    > 에이전트 경고 시간 설정은 180초를 초과할 수 없습니다. 에이전트 알림 시간이 180초를 초과하면 SIP 트랜잭션 시간이 최대 대기 시간에 도달하기 때문에 클라이언트 응용 프로그램에서 통화를 거부합니다. 
  
9. **라우팅 방법** 에서 그룹의 에이전트에 통화가 라우팅되는 방법을 다음과 같이 지정합니다.
    
   - 유휴 시간이 가장 길거나 비즈니스용 Skype에서 사용 가능한 상태 또는  비활성 상태인 에이전트에게 새 통화를 먼저 제공하려면 가장 긴 유휴 시간(가장 긴 유휴 상태)을 **클릭합니다.**  
    
   - 대화 가능한 모든 에이전트에 동시에 새 통화를 제공하려면 **병렬** 을 클릭합니다. 통화를 수락하는 첫 번째 에이전트에 통화가 전송됩니다.
    
   - 각 에이전트에 차례로 새 통화를 제공하려면 **라운드 로빈** 을 클릭합니다. 
    
   - 항상 **에이전트** 목록에 나열된 순서대로 에이전트에 새 통화를 제공하려면 **직렬** 을 클릭합니다. 
    
   - 현재 상태와 관계없이 비즈니스용 Skype 및 응답 그룹 응용 프로그램에 동시에 로그인한 모든 에이전트에게 새 통화를 제공하려면 **Attendant를 클릭합니다.** 에이전트로 구성된 사용자는 대기 중이던 모든 통화를 보고 순서에 따라 대기 통화에 응답할 수 있습니다. 통화를 수락하는 첫 번째 에이전트에게 통화가 전송된 후 다른 에이전트가 더 이상 통화를 볼 수 없습니다.
    
10. **에이전트에서** 에이전트 목록을 만들 방법을 지정합니다.
    
    - 사용자 지정 에이전트 목록을 사용하려면 사용자 지정 에이전트 그룹 **정의를** 클릭하고 다음 중 하나를 선택합니다.
    
    - 에이전트 그룹에 사용자를 추가하려면 선택을 클릭한 다음  에이전트 선택 검색 필드에 이 그룹에 추가할 사용자의 이름 전체 또는 일부를 입력한 다음 찾기를 **클릭합니다.**  결과 에이전트 목록에서 사용자를 클릭한 다음 확인을 **클릭합니다.**
    
    - 에이전트 그룹에서 사용자를 제거하려면 에이전트 목록에서 제거할 사용자를 클릭한 다음 제거를 **클릭합니다.**
    
    - 라운드 로빈 라우팅 또는 직렬 라우팅을 사용하는 그룹에서 에이전트가 통화를 제공하는 순서를 변경하려면 에이전트 목록에서 사용자를 클릭한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다. 
    
    - Microsoft Exchange Server 메일 그룹을 에이전트 그룹으로 사용하려면 기존 전자 메일 그룹 사용을 클릭한 다음 메일 그룹 주소에 메일 그룹의 전자 메일 주소(예: NetworkSupport@contoso.com)를 입력합니다.
    
      전자 메일 그룹을 사용하는 경우 다음과 같은 제약 조건이 적용됩니다.
    
      - 에이전트 그룹에 대해 메일 그룹을 여러 개 선택할 수는 없습니다. 각 그룹이 하나의 메일 그룹만 지원합니다.
    
      - 메일 그룹에 하나 이상의 메일 그룹이 포함되어 있는 경우 중첩된 메일 그룹의 구성원은 에이전트 목록에 추가되지 않습니다.
    
      - 직렬 또는 라운드 로빈 라우팅이 선택된 경우 서버는 라우팅 방법 및 에이전트가 메일 목록에 나열되는 순서에 따라 적절한 에이전트에게 수신 전화를 제공합니다.
    
      - 메일 그룹에 Lync Server 2010을 사용할 수 있지만 Lync Server 2010을 사용할 Enterprise Voice 없는 사용자는 에이전트 그룹에 기능 장애 에이전트로 추가됩니다. 메일 목록의 모든 구성원이 사용자 계정에 대해 Enterprise Voice 사용하도록 설정되어 있는지 확인합니다.
    
    > [!IMPORTANT]
    > 전자 메일 그룹을 사용하는 경우 숨겨진 구성원 자격 또는 숨겨진 목록이 응답 그룹 관리자 또는 사용자에게 표시될 수 있습니다. 
  
    숨겨진 구성원 또는 숨겨진 목록은 다음과 같이 표시될 수 있습니다.
    
     - 구성원 자격이 숨겨져 있으며 응답 그룹 관리자가 메일 그룹을 에이전트 목록에 할당하도록 메일 그룹이 구성된 경우 사용자는 그룹에 전화를 걸고 구성원을 찾을 수 있습니다. 
    
     - 메일 그룹이 Exchange 전체 주소 목록에 숨겨지도록 구성된 경우 응답 그룹 관리자는 적절한 사용자 권한 및 사용 권한이 없는 경우에도 응답 그룹 프로세스에 적절한 사용자 권한이 있는 경우 메일 그룹을 보고 에이전트 목록에 할당할 수 있습니다.
    
11. **커밋** 을 클릭합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 에이전트 그룹을 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. **New-CsRgsAgentGroup을** 사용하여 새 에이전트 그룹을 만들 수 있습니다. **Set-CsRgsAgentGroup을** 사용하여 기존 에이전트 그룹을 수정합니다. 명령줄에서 다음을 실행합니다.
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > 에이전트 경고 시간 설정은 180초를 초과할 수 없습니다. 에이전트 알림 시간이 180초보다 크면 SIP 트랜잭션 Timer이 최대 대기 시간에 도달하기 때문에 클라이언트 응용 프로그램에서 통화를 거부합니다. 
  
4. 에이전트 그룹이 만들어졌습니다. 실행:
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>참고 항목

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
