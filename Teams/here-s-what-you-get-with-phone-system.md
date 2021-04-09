---
title: 다음은 통화 시스템 기능입니다.
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '비즈니스용 Microsoft Phone System을 계획하고 설정하는 기능, 가용성 및 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: b26f6d72a92f0012f47d155531be523872e5a08c
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51648137"
---
# <a name="heres-what-you-get-with-phone-system"></a>다음은 통화 시스템 기능입니다.

이 문서에서는 Phone System 기능에 대해 설명합니다. PBX(Private Branch Exchange) 교체로 전화 시스템을 사용하는 경우 및 PSTN(공용 전환 전화 네트워크)에 연결하는 옵션에 대한 자세한 내용은 전화 [시스템란 을 참조하세요.](what-is-phone-system-in-office-365.md)

클라이언트는 PC, Mac 및 모바일에서 사용할 수 있으며, 태블릿 및 휴대폰에서 PC 및 데스크톱 IP 휴대폰에 대한 디바이스의 기능을 제공합니다. 자세한 내용은 [Microsoft Teams에 대한 클라이언트 다운로드를 참조하세요.](get-clients.md)

 > [!Note]
> 다른 플랫폼의 Teams 휴대폰 시스템에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>전화 시스템 기능

Phone System은 다음 기능을 제공합니다. 달리 명시되지 않는 한, 기능은 Teams 및 비즈니스용 Skype Online에서 모두 사용할 수 있습니다.
  
|||
|:-----|:-----|
|**전화 시스템 기능** <br/> |**설명** <br/> |
|[클라우드 자동 참석자](what-are-phone-system-auto-attendants.md) <br/> |외부 및 내부 발신자는 조직의 회사 사용자 또는 부서에 전화를 찾고 배치하거나 전송할 수 있는 메뉴 시스템을 만들 수 있습니다.  <br/> |
|[클라우드 호출 큐](create-a-phone-system-call-queue.md) <br/> |예를 들어 인사말 및 음악을 보류 중으로 설정하고, 통화를 처리하기 위해 사용할 수 있는 다음 통화 에이전트를 검색하는 등 조직에 대해 통화 큐를 관리하는 방법을 구성할 수 있습니다.  <br/> |
|음악 보류 중 | PSTN(공용 전환 전화 네트워크)의 외부 통화가 보류 중일 때 서비스에 의해 정의된 기본 음악을 재생합니다. 이 기능은 통화 큐에 대한 호출 외에도 일대일 PSTN-Teams 호출에 작동합니다. 이 기능은 다른 플랫폼과의 보류 알림 패리티를 제공합니다. 이 기능은 관리자가 구성할 수 있지만 현재 [PowerShell을 통해서만 구성할 수 있습니다.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 음악 보류는 PSTN 호출의 상담 전송에서도 지원되지 않습니다.|
|통화 응답/시작(이름 및 번호)  <br/> |사용자가 터치로 인바운드 통화에 응답하고 전체 전화 번호에 전화를 걸거나 클라이언트의 이름을 클릭하여 아웃바운드 호출을 할 수 있습니다.  <br/> |
|[통화 전달 옵션 및 동시 링](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |사용자가 통화를 어디에서나 사용할 수 있도록 전달 규칙을 설정할 수 있습니다. 또는 통화를 동료나 음성메일로 전달할 수 있습니다.  <br/> |
|[그룹 호출 픽업 및 그룹 전달](call-sharing-and-group-call-pickup.md) <br/> | 사용자가 사용자를 사용할 수 없는 동안 발생하는 호출에 응답할 수 있도록 사용자가 동료와 들어오는 통화를 공유할 수 있습니다. 사용자가 들어오는 공유 호출에 대해 알림을 받는 방법을 구성할 수 있기 때문에 다른 형태의 통화 공유(예: 통화 전달 또는 동시 벨소리)보다 받는 사람에게 덜 방해가 됩니다. |
|[통화 및 상담 전송 전송](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |사용자가 다른 사용자에게 전화를 전송할 수 있습니다. 또는 사무실에서 나가야 하지만 대화를 계속하려면 PC 또는 IP 휴대폰에서 휴대폰으로 전화를 전송할 수 있습니다.  <br/> |
|[음성메일 중간 통화로 전송](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | 사용자가 통화 중에 음성메일로 전송할 수 있습니다. |
|[통화 대기 및 검색](call-park-and-retrieve.md)  <br/> | 사용자가 클라우드의 Teams 서비스에서 통화 보류를 할 수 있습니다. 호출이 검색된 경우 서비스는 호출 검색을 위한 고유한 코드를 생성합니다. 통화를 저장한 사용자 또는 다른 사용자가 해당 코드와 지원되는 앱 또는 디바이스를 사용하여 통화를 검색할 수 있습니다. <br/> |
|검색에서 전화 번호  <br/> | 사용자가 /call 명령을 사용하고 이름 또는 번호를 지정하여 검색 상자에서 전화를 걸 수 있습니다. <br/> |
|[발신자 ID](how-can-caller-id-be-used-in-your-organization.md)  <br/> |회사 내부의 통화는 회사 디렉터리에서 정보를 끌어오는 자세한 발신자 ID를 표시하여 전화 번호 대신 그림 ID 및 직위를 표시합니다. 외부 전화 번호의 통화의 경우 전화 서비스 공급자가 제공한 발신자 ID가 표시됩니다. 외부 전화 번호가 회사 디렉터리의 보조 번호인 경우 회사 디렉터리의 정보가 표시됩니다.  <br/> |
|디바이스 전환  <br/> |사용자가 Teams에 연결된 다른 HID 장치에서 통화 또는 모임을 재생할 수 있습니다. 예를 들어, PC 스피커에서 헤드셋으로 전환합니다.   <br/> |
|현재 상태 기반 호출 라우팅 <br/> |인바운드 통신을 현재 상태로 제어하여 사용자가 특별히 표시된 통신을 제외한 들어오는 모든 통신을 차단할 수 있습니다.  <br/> |
|[통합 다이얼 패드](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | 사용자가 검색 표시줄과 다이얼 패드의 아무 곳이나 이름이나 번호로 전화를 걸 수 있어 아웃바운드 호출 프로세스를 빠르게 진행할 수 있습니다. <br/> |
|페더리드 호출  <br/> |사용자가 페더리드 테넌트의 사용자와 안전하게 연결, 통신 및 공동 작업을 할 수 있습니다.  <br/> |
|[화상 통화 만들기 및 수신](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | 사용자의 계정이 화상 통화에 사용하도록 설정되어 있는 경우 사용자는 해당 연락처를 사용하여 대면 화상 통화를 할 수 있습니다. 필요한 것은 카메라, 컴퓨터의 스피커 및 마이크입니다. 컴퓨터에 기본 제공 오디오 장치가 없는 경우 헤드셋을 사용할 수 있습니다.<br/> |
|[클라우드 음성메일](set-up-phone-system-voicemail.md) <br/> | 사용자가 음성 메일을 받으면 해당 Exchange 사서함에 음성 메일 메시지가 첨부 파일로 전송됩니다. 사용자는 인증된 데스크톱 휴대폰 및 모든 Teams 또는 비즈니스용 Skype 애플리케이션에서 메시지를 들을 수 있습니다. 음성메일 전사에 대한 지원은 2017년 3월 현재 추가되어 모든 조직 및 사용자에 대해 기본적으로 사용하도록 설정되어 있습니다.   <br/> |
|[클라우드 음성메일 사용자 설정](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 사용자가 부재 중 인사말을 포함하여 음성메일 인사말, 전화 응답 규칙 및 인사말 언어에 대한 클라이언트 설정을 구성할 수 있습니다.   |
|[보조 벨소리](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | PC에 연결된 여러 스피커 디바이스를 사용하는 사용자는 기본 스피커 외에도 보조 디바이스를 벨소리로 설정할 수 있습니다. 예를 들어 PC 및 책상 스피커에 헤드셋이 연결된 사용자는 통화가 올 때 헤드셋과 책상 스피커가 모두 울리게 하여 통화를 놓치지 않습니다.  |
|[독특한 링](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) 경고(Teams만 해당)<br/> |사용자가 일반 통화, 전달된 통화 및 위임된 호출에 대해 별도의 벨소리를 선택할 수 있으므로 통화 유형을 구분할 수 있습니다.  <br/> |
|[회선 공유 기능](shared-line-appearance.md) <br/> | 사용자가 자신의 전화줄을 공유하여 다른 사용자가 전화를 걸고 받을 수 있도록 할 수 있습니다.|
|[사용 중(Teams만](teams-calling-policy.md) 해당) <br/> | 사용자가 이미 통화 또는 회의에 참석 중이거나 통화가 보류된 경우 수신 통화가 처리되는 방법을 구성할 수 있는 호출 정책입니다. 발신자는 통화가 이미 전화에 있을 때 사용 중 신호가 들리거나 사용자의 지원되지 않은 설정에 따라 라우팅됩니다. 즉, 발신자는 이미 통화 중인 사용자에게 음성 메일로 남길 수 있습니다. 발신자에 부재 중 전화 알림이 표시되지만 들어오는 호출에 응답할 수 없습니다. 이 기능은 기본적으로 사용하지 않도록 설정되지만 테넌트 관리자가 설정할 수 있습니다.|
|[통화 차단](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 사용자가 차단된 목록에 PSTN(전화 번호)을 추가하여 해당 번호의 다음 호출이 사용자를 벨소리로 차단할 수 있습니다.|
|[공용 영역 전화](set-up-common-area-phones.md) <br/> | 공용 영역 전화는 일반적으로 로비 또는 회의실과 같은 영역에 배치하여 여러 사용자가 사용할 수 있습니다. 공용 영역 휴대폰은 사용자가 아닌 디바이스로 설정되며 네트워크에 자동으로 로그인할 수 있습니다.|
|[미디어 우회 지원(Teams](direct-routing-plan-media-bypass.md) 직접 라우팅 전용) <br/> | 더 나은 성능을 위해 Microsoft Phone System을 통해 전송하는 대신 SBC(세션 테두리 컨트롤러)와 클라이언트 간에 미디어가 유지됩니다. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High 및 DoD 클라우드의 가용성
<a name="bkmk_setup"> </a>

GCC High 및 DoD Clouds에서는 다음 기능을 아직 사용할 수 없습니다. 
- [보조 벨소리, 음성메일 및 향상된 위임에 대한 통화 설정](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [음성메일 중간 통화로 전송](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 검색 표시줄에서 전화 번호
- 음악 보류 중
- Azure AD 역방향 번호 보기

## <a name="related-topics"></a>관련 항목

- [전화 시스템이란?](what-is-phone-system-in-office-365.md)
- [Microsoft Teams의 클라우드 음성](cloud-voice-landing-page.md)
- [전화 시스템 설정](setting-up-your-phone-system.md)
- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [전화 시스템 직접 라우팅](direct-routing-landing-page.md)
- [통화 품질 모니터링 및 관리](monitor-call-quality-qos.md)
- [Microsoft Teams 추가 기능 라이선스](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [전화 시스템 가격](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [호출 및 모임을 사용하여 가상화된 데스크톱 인프라에 대한 팀](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
