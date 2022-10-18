---
title: 다음은 통화 시스템 기능입니다.
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '기능, 가용성 및 비즈니스용 Microsoft Phone 시스템을 계획하고 설정하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584789"
---
# <a name="heres-what-you-get-with-phone-system"></a>다음은 통화 시스템 기능입니다.

이 문서에서는 전화 시스템 기능에 대해 설명합니다. 전화 시스템을 PBX(Private Branch Exchange) 교체로 사용하고 PSTN(공중 전화망)에 연결하는 옵션에 대한 자세한 내용은 [전화 시스템란?](what-is-phone-system-in-office-365.md)을 참조하세요.

클라이언트는 PC, Mac 및 모바일에서 사용할 수 있으며, 태블릿 및 휴대폰에서 PC 및 데스크톱 IP 휴대폰에 이르는 디바이스의 기능을 제공합니다. 자세한 내용은 [Microsoft Teams용 클라이언트 가져오기를 참조하세요](get-clients.md).

 > [!Note]
> 다양한 플랫폼의 Teams 전화 시스템에 대한 자세한 내용은 [플랫폼별 Teams 기능을](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 참조하세요.

전화 시스템 기능을 사용하려면 조직에 전화 시스템 라이선스가 있어야 합니다. 라이선싱에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조하세요.

대부분의 기능을 사용하려면 전화 시스템 라이선스를 할당하고 사용자가 "음성 사용"을 사용하도록 설정해야 합니다. 라이선스를 할당하려면 [Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) 을 사용하고 **EnterpriseVoiceEnabled** 매개 변수를 $true 설정합니다. 클라우드 자동 전화 교환과 같은 몇 가지 기능은 사용자가 음성을 사용하도록 설정할 필요가 없습니다. 예외는 아래 표에서 호출됩니다.
  
## <a name="phone-system-features"></a>전화 시스템 기능

전화 시스템은 다음과 같은 기능을 제공합니다.
  
|전화 시스템 기능  |설명 |
|:-----|:-----|
|[클라우드 자동 전화 교환](what-are-phone-system-auto-attendants.md)  |외부 및 내부 호출자가 조직의 회사 사용자 또는 부서에 전화를 찾아서 배치하거나 전송할 수 있도록 하는 메뉴 시스템을 만들 수 있습니다.  <br/> 사용자는 자동 전화 교환 다이얼에서 이름으로 전화를 받고 번호 디렉터리 검색으로 전화를 걸 수 있도록 음성을 사용할 필요가 *없습니다* . *사용자는 자동* 전화 교환 메뉴 옵션에서 전화를 받으려면 음성을 사용하도록 설정해야 합니다. |
|[클라우드 호출 큐](create-a-phone-system-call-queue.md) <br> |조직에서 통화 큐를 관리하는 방법을 구성할 수 있습니다. 예를 들어 인사말 및 음악을 보류 상태로 설정하고, 통화를 처리할 다음 통화 에이전트를 검색하는 등의 작업을 수행할 수 있습니다.  <br/> *통화 큐* 에서 전화를 받으려면 사용자가 음성을 사용하도록 설정해야 합니다.|
|[보류 중인 음악](music-on-hold.md) | PSTN(공중 전화망)의 외부 통화가 보류될 때 테넌트 관리자가 업로드한 서비스 또는 사용자 지정 음악으로 정의된 기본 음악을 재생합니다. 이 기능은 통화 큐에 대한 호출 외에도 일대일 PSTN-Teams 통화에 작동합니다. 이 기능은 다른 플랫폼과 보류 중인 알림 패리티를 제공합니다. |
|통화 응답/시작(이름 및 번호별)   |사용자가 터치로 인바운드 통화에 응답하고 전체 전화 번호로 전화를 걸거나 클라이언트에서 이름을 클릭하여 아웃바운드 전화를 걸 수 있습니다.   |
|[착신 전환 옵션 및 동시 링](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |사용자가 어디서나 통화할 수 있도록 전달 규칙을 설정하거나 동료나 음성 메일로 통화를 전달할 수 있습니다.   |
|[그룹 통화 픽업 및 그룹으로 전달](call-sharing-and-group-call-pickup.md)  | 사용자가 동료와 수신 전화를 공유하여 동료가 사용자를 사용할 수 없는 동안 발생하는 통화에 응답할 수 있도록 합니다. 다른 형태의 통화 공유(예: 착신 전환 또는 동시 벨소리)보다 받는 사람에게 덜 방해가 되는 이유는 사용자가 들어오는 공유 통화에 대한 알림을 받는 방법을 구성할 수 있기 때문입니다. |
|[통화 및 상담 전송 전송](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |사용자가 다른 사람에게 통화를 전송할 수 있습니다. 또는 사무실을 떠나야 하지만 대화를 계속하려면 PC 또는 IP 전화에서 휴대폰으로 통화를 전송할 수 있습니다.  <br/> 사용자가 다른 사용자로부터 전송된 전화를 받기 위해 음성을 사용하도록 설정할 필요가 *없습니다* . |
|[음성 메일 중간 통화로 전송*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 사용자가 통화 중에 음성 메일로 전송할 수 있습니다. |
|[통화 대기 및 검색](call-park-and-retrieve.md)   | 사용자가 클라우드의 Teams 서비스에서 통화를 보류할 수 있습니다. 호출이 대기되면 서비스는 호출 검색을 위한 고유한 코드를 생성합니다. 전화를 대기한 사용자 또는 다른 사용자가 해당 코드와 지원되는 앱 또는 디바이스를 사용하여 통화를 검색할 수 있습니다.  |
|검색에서 전화 번호   | 사용자가 /call 명령을 사용하고 이름 또는 번호를 지정하여 검색 상자에서 전화를 걸 수 있습니다.  |
|[발신자 ID](how-can-caller-id-be-used-in-your-organization.md)   |회사 내부의 통화는 회사 디렉터리에서 정보를 가져오는 자세한 발신자 ID를 표시하며 전화 번호 대신 사진 ID와 직위를 표시합니다. 외부 전화 번호의 통화의 경우 전화 서비스 공급자가 제공한 발신자 ID가 표시됩니다. 외부 전화 번호가 회사 디렉터리의 보조 번호인 경우 회사 디렉터리의 정보가 표시됩니다.   |
|디바이스 전환   |사용자가 Teams에 연결된 다른 HID 장치에서 통화 또는 모임을 재생할 수 있습니다. 예를 들어 PC 스피커에서 헤드셋으로 전환합니다.    |
|현재 상태 기반 호출 라우팅  |현재 상태와의 인바운드 통신을 제어하여 사용자가 특별히 표시된 통신을 제외한 모든 들어오는 통신을 차단할 수 있도록 합니다.   |
|[통합 다이얼 패드](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | 사용자가 검색 창과 다이얼 패드의 어디에서나 이름 또는 숫자로 전화를 걸 수 있으므로 아웃바운드 호출 프로세스를 가속화할 수 있습니다.  |
|페더레이션된 호출   |사용자가 페더레이션된 테넌트에서 사용자와 안전하게 연결, 통신 및 공동 작업할 수 있습니다.   |
|[화상 통화 걸기 및 받기](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | 사용자의 계정이 화상 통화에 사용하도록 설정된 경우 사용자는 대화 상대와 직접 화상 통화를 할 수 있습니다. 카메라, 컴퓨터 스피커, 마이크만 있으면 됩니다. 컴퓨터에 기본 제공 오디오 장치가 없는 경우 사용자는 헤드셋을 사용할 수도 있습니다. |
|[클라우드 음성 메일](set-up-phone-system-voicemail.md)  | 사용자가 음성 메일을 받으면 음성 메일 메시지가 첨부 파일로 포함된 전자 메일로 Exchange 사서함에 배달됩니다. 사용자는 인증된 데스크톱 휴대폰 및 모든 Teams 또는 비즈니스용 Skype 애플리케이션에서 메시지를 들을 수 있습니다. 음성 메일 전사에 대한 지원은 2017년 3월부터 추가되었으며 모든 조직 및 사용자에 대해 기본적으로 사용하도록 설정됩니다. <br> 사용자는 전화 시스템  라이선스가 필요하지 *않으며* 클라우드 음성 사서함 기능을 사용하기 위해 음성을 사용하도록 설정할 필요가 없습니다.    |
|[사용자 설정 클라우드 음성 사서함](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 사용자가 음성 메일 인사말, 통화 응답 규칙 및 외부 인사말을 포함한 인사말 언어에 대한 클라이언트 설정을 구성할 수 있습니다. <br> 사용자는 전화 시스템  라이선스가 필요하지 *않으며* 클라우드 음성 사서함 기능을 사용하기 위해 음성을 사용하도록 설정할 필요가 없습니다.  |
|[보조 벨소리](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | PC에 연결된 스피커 디바이스가 여러 개 있는 사용자는 기본 스피커 외에도 보조 디바이스를 링하도록 설정할 수 있습니다. 예를 들어 PC와 책상 스피커에 연결된 헤드셋을 사용하는 사용자는 통화가 들어오면 헤드셋과 책상 스피커가 모두 울리도록 선택하여 통화를 놓치지 않도록 할 수 있습니다.  |
|[고유한 링 경고](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams만 해당) |사용자가 통화 유형을 구분할 수 있도록 일반 통화, 전달된 통화 및 위임된 통화에 대해 별도의 벨소리를 선택할 수 있습니다.   |
|[회선 공유 기능](shared-line-appearance.md)  | 다른 사용자가 전화를 걸고 대신 전화를 받을 수 있도록 사용자가 전화 회선을 공유할 수 있습니다.|
|[사용 중(](teams-calling-policy.md) Teams만 해당)  | 사용자가 다음과 같은 경우 들어오는 호출을 처리하는 방법을 구성할 수 있는 호출 정책입니다. <ul><li>통화 중 </li><li>회의에서</li><li>에는 보류 중인 호출이 있습니다. </li></ul> 호출자는 다음 응답 중 하나를 받게 됩니다. <ul><li>통화 수신자가 전화를 걸 때 사용 중인 신호 듣기</li> <li>는 사용자의 응답하지 않는 설정에 따라 라우팅됩니다. 한 가지 옵션을 사용하면 호출자가 이미 통화 중인 사용자의 음성 메일을 남길 수 있습니다.</li></ul> 호출 수신자는 부재 중 전화 알림을 받지만 들어오는 통화에 응답할 수 없습니다. 이 기능은 기본적으로 사용하지 않도록 설정되지만 테넌트 관리자가 설정할 수 있습니다.|
|[통화 차단](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 사용자가 차단된 목록에 PSTN(전화 번호)을 추가하여 해당 번호의 다음 통화가 사용자를 울리지 못하도록 차단할 수 있습니다.|
|[공용 영역 전화](set-up-common-area-phones.md)  | 공용 영역 전화는 일반적으로 여러 사람이 사용할 수 있도록 로비 또는 회의실과 같은 영역에 배치됩니다. 공용 영역 전화는 사용자가 아닌 디바이스로 설정되며 네트워크에 자동으로 로그인할 수 있습니다.|
|[미디어 바이패스 지원](direct-routing-plan-media-bypass.md) (Teams 직접 라우팅에만 해당)  | 성능을 향상시키려면 미디어가 전화 시스템을 통해 전송하는 대신 SBC(세션 테두리 컨트롤러)와 클라이언트 간에 유지됩니다. |
|[할당되지 않은 번호 라우팅](routing-calls-to-unassigned-numbers.md) | 할당되지 않은 번호를 사용자, 자동 전화 교환, 통화 큐 또는 사용자 지정 공지 사항으로 라우팅할 수 있습니다. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High 및 DoD 클라우드의 가용성
<a name="bkmk_setup"> </a>

GCC High 및 DoD 클라우드에서는 아직 다음 기능을 사용할 수 없습니다. 

- [보조 벨소리, 음성 메일 및 향상된 위임에 대한 통화 설정](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [음성 메일 중간 통화로 전송](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 검색 창에서 전화 번호
- 보류 중인 음악
- 역방향 숫자 조회 Azure AD

## <a name="related-topics"></a>관련 주제

- [전화 시스템이란?](what-is-phone-system-in-office-365.md)
- [Microsoft Teams의 클라우드 음성](cloud-voice-landing-page.md)
- [전화 시스템 설정](setting-up-your-phone-system.md)
- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 품질 모니터링 및 관리](monitor-call-quality-qos.md)
- [Microsoft Teams 추가 기능 라이선스](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [전화 시스템 가격](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [통화 및 모임이 있는 가상화된 데스크톱 인프라용 Teams](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
