---
title: Microsoft 팀의 음성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Microsoft 전화 시스템 및 PSTN 연결 옵션 (예를 들어, 호출 계획 및 직접 라우팅 포함)에 대해 자세히 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 513525448112fbb9b2b0bf4beacfec46bfb1d76a
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308362"
---
# <a name="plan-your-teams-voice-solution"></a>팀 음성 솔루션 계획 

이 문서에서는 조직에 적합 한 Microsoft 음성 솔루션을 결정 하는 데 도움이 되는 정보를 안내 합니다. 이 문서에서는 선택한 솔루션을 구현 하는 데 사용할 수 있는 콘텐츠 로드맵을 제공 하기로 결정 했습니다. 

가장 간단한 솔루션 전화 시스템에는 통화 요금제를 사용 하는 것이 좋습니다 &mdash; . 다음 다이어그램과 같이 PBX (개인 브랜치 교환) 기능 및 PSTN (공개 교환 전화 네트워크)에 대 한 통화를 제공 하는 클라우드 솔루션입니다. 이 솔루션을 사용 하는 경우 Microsoft는 PSTN 통신 회사입니다.

![다이어그램 1 통화 요금제가 포함 되어 있는 전화 시스템 표시](media/msft-voice-solutions-1.png)

다음으로 질문에 대답 하는 경우에는 통화 요금제가 있는 전화 시스템을 적절 하 게 해결 하는 것이 좋습니다.

- 전화 요금제는 해당 지역에서 사용할 수 있습니다.
- 현재 PSTN 통신 회사를 유지할 필요는 없습니다.
- PSTN에 대 한 Microsoft 관리 액세스를 사용 하려고 합니다.

그러나 상황이 복잡 해질 수 있습니다. 예를 들어 전화 요금제를 사용할 수 없는 위치에 사무실이 있을 수 있습니다. 또는 다양 한 지리적 위치에 대 한 요구 사항이 서로 다른 복잡 한 국내 배포를 지 원하는 조합 솔루션이 필요할 수 있습니다. Microsoft는 다음과 같은 솔루션의 조합을 지원 합니다. 

- 통화 요금제가 포함 되어 있는 전화 시스템
- 직접 라우팅이 있는 고유한 PSTN 캐리어가 있는 전화 시스템
- 전화 시스템을 함께 사용 하 여 다이렉트 라우팅이 있는 통화 요금제와 전화 시스템을 사용한 조합 솔루션

## <a name="what-do-you-need-to-read"></a>읽어야 할 사항

**모두에 필요 합니다.** 이 문서의 일부 섹션에서는 모든 조직과 관련 되어 있습니다. 예를 들어, 모든 사람이 전화 시스템에 대해 읽고 PSTN (공개 교환 전화 네트워크)에 연결 하는 옵션을 이해 해야 합니다. 


| 모두에 필요 함 | 설명 |
| :------------|:-------|
| [**전화 시스템**](#phone-system) | Microsoft 팀에서 microsoft 365 클라우드의 통화 제어 및 PBX (개인 브랜치 교환) 기능을 사용 하도록 설정 하기 위한 microsoft의 기술입니다. |
| [**PSTN (공개 통신 네트워크) 연결 옵션**](#public-switched-telephone-network-connectivity-options) | 전화 통신 회사로 Microsoft를 사용 하거나 직접 라우팅을 사용 하 여 Microsoft 팀에 고유한 전화 통신 회사를 연결 하는 것 중에서 선택 합니다. 휴대폰 시스템과 결합 하 여 PSTN 연결 옵션을 통해 사용자는 전세계의 전화 통화를 할 수 있습니다.|

**요구 사항에 따라** 이 문서의 일부 섹션은 기존 배포 및 요구 사항에 따라 관련이 있습니다. 예를 들어 위치 기반 라우팅은 유료 바이패스를 허용 하지 않는 지리적 위치에서 직접 라우팅 고객에 게 필요 합니다.


| 요구 사항에 따라 | 설명 |
| :------------|:-------|
| [**Microsoft의 전화 번호**](#phone-numbers-from-microsoft) | Microsoft에서 전화 번호를 가져오고 관리 하는 방법과 기존 번호를 Microsoft로 전송 하는 방법을 설명 합니다. Microsoft 통화 요금제에 대 한 전화 번호를 얻고, 기존 번호를 전송 하 고, 서비스 번호를 얻어야 하는 등의 방법을 읽어 보세요. |
| [**다이얼 플랜 및 통화 회람**](#dial-plans-and-call-routing) | 전화 접속 전화 번호를 대체 형식 (일반적으로 E. \ 164 형식)으로 변환 하는 다이얼 플랜을 구성 하 고 관리 하 여 통화 승인 및 통화 라우팅을 할 수 있습니다. 다이얼 플랜을 파악 하 고 조직의 다이얼 플랜을 지정 해야 하는지 여부를 확인 하려면 다음을 읽어 보세요.|
| [**비상 전화**](#emergency-calling) | PSTN 연결 옵션에 따라 응급 통화를 관리 하 고 구성 하는 방법을 설명 &mdash; 합니다. Microsoft 통화 계획 또는 직접 라우팅을 사용 중이 고 조직의 긴급 통화를 관리 하는 방법을 이해 해야 하는 경우이 섹션을 읽어 보세요. |
| [**직접 라우팅에 대 한 위치 기반 라우팅**](#location-based-routing-for-direct-routing) |LBR (위치 기반 라우팅)를 사용 하 여 Microsoft 팀 사용자가 지리적 위치를 기준으로 하는 유료 바이패스를 제한 하는 방법을 설명 합니다. 조직에서 수신자 부담을 허용 하지 않는 위치에서 직접 라우팅을 사용 하는 경우이 섹션을 읽으십시오.
| [**클라우드 음성 기능에 대 한 네트워크 토폴로지**](#network-topology-for-voice-features) | 조직에서 직접 라우팅 또는 동적 비상 전화에 대 한 LBR (위치 기반 라우팅)를 배포 하는 경우 Microsoft 팀에서 이러한 기능을 사용할 수 있도록 네트워크 설정을 구성 해야 합니다. 직접 라우팅에 대 한 LBR을 구현 하는 경우 또는 호출 계획 또는 직접 라우팅과 함께 동적 비상 전화를 구현 하는 경우이 섹션을 참조 하세요. |
| [**기존 음성 솔루션 마이그레이션**](#migrate-your-existing-voice-solution-to-teams) | 음성 솔루션을 팀으로 마이그레이션할 때 고려해 야 할 사항  기존 음성 솔루션에서 팀으로 마이그레이션하는 경우이 섹션을 참조 하세요. 



> [!Important]
> 이 문서에서는 Microsoft 팀과의 음성 솔루션에 대해 중점적으로 설명 합니다. 비즈니스용 Skype Online을 사용 하는 솔루션도 계속 사용할 수 있지만 ( [Microsoft 전화 통신 솔루션](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)에서 설명한 대로) 비즈니스용 skype online은 2021 년 7 월 31 일에 만료 된다는 것을 이해 하는 것이 중요 합니다.  이 날짜 이후에는 비즈니스용 Skype Online 서비스에 더 이상 액세스할 수 없게 됩니다. 또한 비즈니스용 &mdash; Skype Server 또는 클라우드 커넥터 버전 및 비즈니스용 Skype Online을 통해 온-프레미스 환경 간의 PSTN 연결이 &mdash; 더 이상 지원 되지 않습니다. 이 문서에서는 팀 음성 솔루션을 소개 하 고, 필요한 경우 직접 라우팅을 사용 하 여 온-프레미스 전화 통신 네트워크를 팀에 연결 하는 방법에 대해 설명 합니다.


## <a name="phone-system"></a>전화 시스템

전화 시스템은 microsoft 팀에서 microsoft 365 또는 Office 365 클라우드의 통화 제어 및 개인 브랜치 교환 (PBX) 기능을 사용 하도록 설정 하기 위한 Microsoft의 기술입니다.

전화 시스템은 팀 또는 비즈니스용 Skype 클라이언트와 인증 된 장치에서 작동 합니다. 전화 시스템을 사용 하면 기존 PBX 시스템을 Microsoft 365 또는 Office 365에서 직접 제공 되는 기능 집합으로 바꿀 수 있습니다. 

조직의 사용자 간 통화는 전화 시스템 내에서 내부적으로 처리 되며 PSTN (공개 전환 통신 네트워크)로 이동 하지 않습니다. 이는 조직의 사용자 간 여러 지리적 영역에 해당 하는 통화에 적용 되며, 이러한 내부 통화에 대 한 장거리 비용을 제거 합니다.

이 문서에서는 다음과 같은 휴대폰 시스템의 주요 기능과 기능을 소개 하 고, 고려해 야 할 배포 결정 사항에 대해 설명 합니다.

- [자동 전화 교환 및 통화 큐](#auto-attendants-and-call-queues)
- [클라우드 음성 메일](#cloud-voicemail)
- [통화 id](#calling-identity)

모든 전화 시스템 기능 및 전화 시스템을 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)
- [조직에서 전화 시스템 설정](setting-up-your-phone-system.md)<br>
  전화 시스템 라이선스를 구입 및 할당 하 고, 전화 번호를 관리 하 고, 무료 전화에 대 한 통신 크레딧을 설정 하는 방법을 설명 합니다. 

지원 되는 장치를 관리 하는 방법에 대 한 자세한 내용은 Microsoft 팀 및 [팀 마켓플레이스에서](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) [장치 관리](devices/device-management.md) 를 참조 하세요.


### <a name="auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 대기열

자동 전화 교환을 통해 발신자 입력에 따라 통화를 라우팅하기 위한 메뉴 옵션을 설정할 수 있습니다. 통화 큐는 호출자의 대기 영역입니다. 자동 전화 교환 및 통화 대기열을 함께 사용 하면 조직의 해당 사용자 또는 부서로 쉽게 호출자를 라우팅할 수 있습니다.

자동 전화 교환 및 통화 대기열에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [팀 자동 전화 교환 및 통화 대기열에 대 한 계획](plan-auto-attendant-call-queue.md)
- [자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)
- [통화 대기열 만들기](create-a-phone-system-call-queue.md) 
- [Contoso 사례 연구: 자동 전화 교환 및 통화 대기열](voice-case-study-call-queues.md)<br>
  비즈니스용 기업, Contoso, 자동 전화 교환 및 음성 솔루션에 대 한 통화 대기열을 구현 하는 방법에 대해 설명 합니다.

### <a name="cloud-voicemail"></a>클라우드 음성 메일

Azure 보이스 메일 서비스에서 제공 하는 클라우드 보이스 메일은 Exchange 사서함에 대 한 보이스 메일 저축과 지원 합니다. 타사 전자 메일 시스템은 지원 되지 않습니다. 

클라우드 보이스 메일에는 조직의 모든 사용자가 기본적으로 사용 하도록 설정 된 음성 메일의 내용이 포함 됩니다. 비즈니스 요구에 따라 특정 사용자 또는 조직 전체에 대 한 보이스 메일을 사용 하지 않도록 설정 해야 할 수 있습니다.

온라인 전용 사용자의 경우 클라우드 보이스 메일은 사용자에 게 전화 시스템 라이선스가 할당 된 후 자동으로 설정 되 고 프로 비전 됩니다. Exchange 사서함이 있는 휴대폰 시스템 사용자는 추가 구성 단계를 수행 해야 합니다. 

클라우드 보이스 메일 및 해당 구성에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [클라우드 음성 메일 설정](set-up-phone-system-voicemail.md)
- [조직에서 보이스 메일 정책 설정](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>통화 id

기본적으로 모든 아웃 바운드 통화는 지정 된 전화 번호를 통화 id (발신자 ID)로 사용 합니다. 통화를 받는 사람은 발신자를 빠르게 확인 하 고 통화 수락 또는 거부 여부를 결정할 수 있습니다. 발신자 id를 구성 하거나 발신자 ID를 변경 하거나 차단 하는 방법에 대 한 자세한 내용은 [사용자의 발신자 Id 설정을](set-the-caller-id-for-a-user.md)참조 하세요. 

## <a name="public-switched-telephone-network-connectivity-options"></a>공개 교환 전화 네트워크 연결 옵션

전화 시스템은 조직의 완전 한 PBX 기능을 제공 합니다. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 하려면, PSTN (공개 교환 전화 네트워크)에 전화 시스템을 연결 해야 합니다. 전화 시스템을 PSTN에 연결 하기 위해 다음 옵션 중 하나를 선택할 수 있습니다.

- 통화 [**요금제를 사용 하는 전화 시스템**](#phone-system-with-calling-plan) Microsoft를 PSTN 통신 회사로 사용 하는 클라우드 솔루션입니다.

- 직접 라우팅 기능을 사용 하 여 온-프레미스 환경을 팀에 연결 하 여 [**고유한 PSTN 통신 업체를 갖춘 전화 시스템**](#phone-system-with-own-pstn-carrier-with-direct-routing)

복잡 한 환경의 솔루션을 디자인 하거나 여러 단계 마이그레이션 (나중에 마이그레이션에 대해 자세히 알아보세요)을 관리할 수 있는 옵션 조합을 선택할 수도 있습니다.

### <a name="phone-system-with-calling-plan"></a>통화 요금제가 포함 되어 있는 전화 시스템 

이 문서의 앞부분에서 설명한 대로, 통화 요금제가 포함 된 전화 시스템은 팀 사용자를 위한 Microsoft의 클라우드 간 음성 솔루션입니다. 이 옵션은 Microsoft 전화 시스템을 PSTN (공개 통신 네트워크)에 연결 하 여 전 세계의 유선전화 및 휴대 전화로 전화를 걸 수 있도록 하는 가장 간단한 방법입니다. 이 옵션을 사용 하는 경우 Microsoft는 다음 다이어그램에 표시 된 대로 조직에 대 한 PBX (사설 Branch Exchange) 기능을 제공 하 고 PSTN 통신 회사 역할을 합니다.

![다이어그램 1 통화 요금제가 포함 되어 있는 전화 시스템 표시](media/msft-voice-solutions-1a.png)

다음으로 질문에 대답 하는 경우에는 통화 요금제가 있는 전화 시스템을 적절 하 게 해결 하는 것이 좋습니다.

- 전화 요금제는 해당 지역에서 사용할 수 있습니다.
- 현재 PSTN 통신 회사를 유지할 필요는 없습니다.
- PSTN에 대 한 Microsoft 관리 액세스를 사용 하려고 합니다.

이 옵션을 사용 합니다. 

- 사용이 허가 되는 서비스 수준에 따라 전세계의 전화로 전화를 걸 수 있도록 하는 국내 또는 국제 통화 계획이 추가 된 Microsoft 전화 시스템을 이용할 수 있습니다.

- &mdash;통화 요금제가 Microsoft 365 또는 Office 365에서 작동 하기 때문에 온-프레미스 배포의 배포 또는 유지 관리를 요구 하지 않습니다.

- 참고: 필요한 경우 타사 Pbx, 아날로그 장치 및 SBC에서 지원 되는 타사 전화 통신 장비와의 상호 운용성을 위해 직접 라우팅을 통해 SBC (지원 되는 세션 경계 컨트롤러)에 연결 하도록 선택할 수 있습니다.

이 옵션을 사용 하려면 Microsoft 365 또는 Office 365에 대 한 중단 없는 연결이 필요 합니다.

통화 요금제에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 플랜을 구입하는 방법](calling-plans-for-office-365.md)
- [통화 플랜의 국가 및 지역 가용성](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [통화 요금제 설정](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>직접 라우팅이 있는 고유한 PSTN 캐리어가 있는 전화 시스템

이 옵션은 다음 다이어그램과 같이 직접 라우팅을 사용 하 여 Microsoft 전화 시스템을 전화 통신 네트워크에 연결 합니다. 

![다이어그램 2 직접 라우팅이 있는 전화 시스템 표시](media/msft-voice-solutions-2.png)

다음 질문에 대 한 답변을 사용 하는 경우 직접 라우팅이 필요한 전화 시스템은 적절 한 해결 방법입니다.

- 전화 시스템에서 팀을 사용 하려는 경우
- 현재 PSTN 통신 회사를 유지 해야 합니다.
- 통화 요금제를 통과 하는 일부 통화, 즉 통신 회사를 통해 라우팅을 혼합 하려고 합니다.
- 타사 Pbx 및/또는 장비 (예: 미국 오버 헤드 호출기, 아날로그 장치 등)와 상호 운용 해야 합니다.

이 옵션을 사용 합니다.

- 추가 온-프레미스 소프트웨어를 사용 하지 않고 자체 지원 SBC를 Microsoft 전화 시스템에 연결할 수 있습니다.

- Microsoft 전화 시스템을 사용 하 여 거의 모든 통신 사업자를 사용할 수 있습니다.

- 이 옵션을 구성 하 고 관리 하도록 선택 하거나, 통신 회사 또는 파트너가이 옵션을 제공 하는지 여부를 확인 하 여 구성 하 고 관리할 수 있습니다.

- &mdash;타사 PBX, 아날로그 장치 &mdash; , Microsoft 전화 시스템 등의 전화 통신 장비 간 상호 운용을 구성할 수 있습니다.


이 옵션을 사용 하려면 다음이 필요 합니다.

- Microsoft 365 또는 Office 365에 대 한 중단 없는 연결.

- 지원 되는 SBC 배포 및 유지 관리

- 타사 통신 업체와의 계약.
  (전화 시스템을 사용 하는 사용자를 위해 타사 PBX, 아날로그 장치 또는 기타 전화 통신 장비에 대 한 연결을 제공 하기 위한 옵션으로 배포 되지 않은 경우)

직접 라우팅에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [전화 시스템 직접 라우팅](direct-routing-landing-page.md)
- [직접 라우팅 계획](direct-routing-plan.md)
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅에 사용할 음성 라우팅 정책 관리](manage-voice-routing-policies.md)
- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)


## <a name="phone-numbers-from-microsoft"></a>Microsoft의 전화 번호

Microsoft에는 두 가지 유형의 전화 번호, 즉 조직의 사용자에 게 할당할 수 있는 *구독자* (사용자) 번호와 유료 및 무료 서비스 번호로 제공 되는 *서비스* 번호가 있습니다. 서비스 번호는 구독자 번호 보다 높은 동시 통화 용량을 가지 며 오디오 회의, 자동 전화 교환 또는 통화 대기열 등의 서비스에 할당할 수 있습니다.

다음 사항을 결정 해야 합니다.

- Microsoft에서 새 전화 번호를 필요로 하는 사용자 위치는 무엇 인가요?
- 어떤 종류의 전화 번호 (구독자 또는 서비스)가 필요 합니까? 
- 기존 전화 번호를 팀에 게 이식 하려면 어떻게 하나요?

새 번호 받기 또는 종료 번호 전송을 포함 하 여 조직의 전화 번호를 관리 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [사용자의 전화 번호 가져오기](getting-phone-numbers-for-your-users.md)
- [Microsoft 팀에 전화 번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>다이얼 플랜 및 통화 회람

다이얼 플랜은 전화 걸기 전화 번호를 대체 형식 (일반적으로 E. \ 164 형식)으로 변환 하는 표준화 규칙 집합으로, 통화 승인 및 통화 라우팅을 위해 사용할 수 있습니다.

다음 사항을 결정 해야 합니다. 

- 조직에 사용자 지정 다이얼 플랜이 필요한가요?
- 사용자 지정 다이얼 플랜을 필요로 하는 사용자
- 각 사용자에 게 어떤 테 넌 트 다이얼 플랜을 할당 해야 하나요?

자세한 내용은 다음 문서를 참조 하세요. 

- [다이얼 플랜이 무엇인가요?](what-are-dial-plans.md)
- [테 넌 트 다이얼 플랜 계획](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>비상 전화

응급 통화를 구성 하는 방법은 PSTN 연결 옵션 (Microsoft 호출 계획 또는 직접 라우팅)에 따라 다릅니다. Microsoft 통화 요금제 및 전화 시스템 다이렉트 라우팅을 위한 동적 긴급 통화는 팀 클라이언트의 현재 위치에 따라 긴급 전화를 구성 하 고 라우팅하고 보안 사용자에 게 알릴 수 있는 기능을 제공 합니다. 긴급 통화 개념 및 용어에 대 한 자세한 내용과 동적 비상 전화를 구성 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md)
- [Contoso 사례 연구: 비상 전화](voice-case-study-emergency-calling.md)<br>
  가상의 여러 국립 기업, Contoso, 조직에 대 한 긴급 통화 구현 방법에 대해 설명 합니다.

## <a name="location-based-routing-for-direct-routing"></a>직접 라우팅에 대 한 위치 기반 라우팅

일부 국가 및 지역에서는 PSTN (공개 전환 전화 네트워크) 공급자를 우회 하 여 시외 통화 비용을 줄일 수 없습니다. 직접 라우팅을 위한 위치 기반 라우팅을 사용 하면 Microsoft 팀 사용자의 지리적 위치를 기반으로 하는 무료 바이패스를 제한할 수 있습니다. LBR (위치 기반 라우팅)를 계획 하 고 구성 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅의 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Contoso 사례 연구: 위치 기반 라우팅](voice-case-study-location-based-routing.md)<br>
  조직의 여러 국내 기업, Contoso, 구현 된 위치 기반 라우팅에 대해 설명 합니다.

## <a name="network-topology-for-voice-features"></a>음성 기능에 대 한 네트워크 토폴로지

직접 라우팅에 대 한 동적 긴급 통화 또는 위치 기반 라우팅을 배포 하는 경우 Microsoft 팀에서 이러한 기능을 사용할 수 있도록 네트워크 설정을 구성 해야 합니다. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대 한 네트워크 설정을 구성 하는 방법을 알아보려면 다음 문서를 참조 하세요.

- [Microsoft 팀의 클라우드 음성 기능에 대 한 네트워크 설정-개념 및 용어](cloud-voice-network-settings.md)
- [Microsoft 팀의 클라우드 음성 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>기존 음성 솔루션을 팀으로 마이그레이션

팀으로 업그레이드 하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동 하는 것입니다. 팀과 함께 전화 시스템을 사용 하는 것은 사용자가 TeamsOnly 모드에 있는 경우에만 지원 됩니다. 팀으로 업그레이드 하는 방법에 대 한 기본 정보가 필요한 경우 다음을 실행 합니다.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [업그레이드 프레임워크 정보](upgrade-framework.md)
- [비즈니스용 Skype에서 팀으로 업그레이드 (IT 관리자 용)](upgrade-to-teams-on-prem-overview.md)

음성 솔루션을 마이그레이션할 때 팀 전용 모드로 전환할 때 네 가지 호출 시나리오가 있을 수 있습니다.

- [**Microsoft 전화 요금제를 사용 하 여 비즈니스용 Skype Online의 사용자**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)입니다. 업그레이드 되 면이 사용자는 계속 Microsoft 통화 요금제를 보유 하 게 됩니다.

- 비즈니스용 skype **Online의 skype For business for 온 [-프레미스 음성 기능을 사용 하는 사용자](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) ** 팀으로의 사용자 업그레이드는 사용자가 자신에 게 PSTN 기능을가지고 있는지를 확인 하기 위해 자신을 마이그레이션하도록 조정 해야 합니다.

- ** [비즈니스용 Skype 온-프레미스에서 엔터프라이즈 음성을 사용 하 여](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)온라인으로 전환 하 고 온-프레미스 PSTN 연결을 유지 하는 사용자**입니다. 이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 사용자의 직접 라우팅에 맞게 이동 하도록 조정 해야 합니다. 

- Enterprise Voice를 사용 하는 ** [비즈니스용 Skype 온-프레미스 사용자](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)로 서, 온라인으로 이동 하 고 Microsoft의 통화 요금제를 사용 하 게 됩니다**.  이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 해당 사용자의 전화 번호를 Microsoft 통화 요금제 또는 B로 이동 하 여 사용 가능한 지역에서 새 구독자 번호를 할당 해야 합니다.

&mdash;하이브리드 연결 설정에 대 한 정보, 직접 라우팅에 대 한 온-프레미스 음성 기능을 사용 하 여 사용자를 마이그레이션하는 방법에 대 한 정보가 포함 된 각 시나리오에 대해 음성 마이그레이션을 구현 하는 방법에 대 한 자세한 내용은 &mdash; 다음 문서를 참조 하세요.

- [팀으로 업그레이드할 때의 PSTN 고려 사항-IT 관리자 용](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 음성 마이그레이션 사례 연구](voice-case-study-overview.md)<br>
  사례 연구는 가상의 여러 국립 기업 (Contoso)이 조직에 대 한 팀 음성 솔루션을 구현 하는 방법을 설명 합니다. 여기에는 다음 문서가 포함 되어 있습니다.

  - [팀 업그레이드 계획](voice-case-study-migration-plan.md)
  - [전화 시스템 및 PSTN 연결 옵션](voice-case-study-phone-system.md)
  - [위치 기반 라우팅 구현](voice-case-study-location-based-routing.md)
  - [비상 전화](voice-case-study-emergency-calling.md)
  - [자동 전화 교환 및 통화 큐](voice-case-study-call-queues.md)
  - [오디오 회의](voice-case-study-audio-conferencing.md)












