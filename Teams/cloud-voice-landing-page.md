---
title: Microsoft Teams에서 음성 솔루션 계획
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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Microsoft Teams 클라우드 음성 기능 및 조직에 대해 내릴 배포 결정에 대해 자세히 설명합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd7ebfd4542c38bd56900c1e414dadec09bf246
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408194"
---
# <a name="plan-your-teams-voice-solution"></a>Teams 음성 솔루션 계획 

이 문서에서는 조직에 적합한 Microsoft 음성 솔루션을 결정하는 데 도움이 됩니다. 결정한 후 이 문서에서는 선택한 솔루션을 구현할 수 있도록 콘텐츠에 대한 로드맵을 제공합니다.

> [!NOTE]
> 비즈니스용 Skype 서버의 Teams로 업그레이드하기 위한 전체 계획의 일부로 Teams 음성 솔루션을 계획하는 방법에 대한 지침은 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 PSTN 고려 사항을 [참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md)

통화 계획을 통해 가장 간단한 솔루션 &mdash; 전화 시스템을 원할 수 있습니다. 다음 다이어그램과 같이 PBX(Private Branch Exchange) 기능을 제공하고 PSTN(공용 전환 전화 네트워크)에 대한 호출을 제공하는 Microsoft의 올인 더 클라우드 솔루션입니다. 이 솔루션을 통해 Microsoft는 PSTN 통신업체입니다.

![다이어그램 1은 통화 계획이 있는 전화 시스템을 보여줍니다.](media/voice-solutions-simple.png)

다음에 예로 대답하면 전화 요금제가 있는 전화 시스템이 적합한 솔루션입니다.

- 통화 요금제는 지역에서 사용할 수 있습니다.
- 현재 PSTN 캐리어를 유지할 필요가 없습니다.
- PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우

그러나 상황은 더 복잡할 수 있습니다. 예를 들어 통화 계획을 사용할 수 없는 위치에 사무실이 있을 수 있습니다. 또는 여러 지리적 위치에 대한 다양한 요구 사항과 함께 복잡하고 다국적 배포를 지원하는 조합 솔루션이 필요할 수 있습니다. Microsoft는 솔루션의 조합을 지원합니다. 

- 통화 계획이 있는 전화 시스템
- 직접 라우팅을 통해 사용자만의 PSTN 통신사가 있는 전화 시스템
- 직접 라우팅을 사용하여 전화 시스템과 통화 계획 및 전화 시스템을 모두 사용하는 조합 솔루션

## <a name="what-do-you-need-to-read"></a>무엇을 읽어야 하나요?

**모두에 필요합니다.** 이 문서의 일부 섹션은 모든 조직과 관련이 있습니다. 예를 들어 모든 사람이 전화 시스템에 대해 읽고 PSTN(공용 전환 전화 네트워크)에 연결하는 옵션을 이해해야 합니다. 


| 모두에 필수 | 설명 |
| :------------|:-------|
| [**전화 시스템**](#phone-system) | Microsoft Teams를 사용하여 Microsoft 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다. |
| [**PSTN(공용 전환 전화 네트워크) 연결 옵션**](#public-switched-telephone-network-connectivity-options) | Microsoft를 전화 통신 사업자로 사용하거나 직접 라우팅을 사용하여 사용자 자신의 전화 통신 통신업체를 Microsoft Teams에 연결하는 중 선택할 수 있습니다. 전화 시스템과 결합된 PSTN 연결 옵션을 사용하면 사용자가 전 세계에 전화를 걸 수 있습니다.|

**요구 사항에 따라 다릅니다.** 이 문서의 일부 섹션은 기존 배포 및 요구 사항에 따라 관련이 있습니다. 예를 들어 Location-Based 우회를 허용하지 않는 지리적 위치에 있는 직접 라우팅 고객에게만 이러한 라우팅이 필요합니다.

다음 추가 구성 중 어느 것이 필요할지 고려합니다.

![다이어그램 2에서는 Microsoft의 전화 번호, 전화 걸기 계획 및 통화 라우팅과 같은 추가 음성 구성 요소를 보여줍니다.](media/voice-consider-additional-components.png)

| 요구 사항에 따라 | 설명 |
| :------------|:-------|
| [**Microsoft의 전화 번호**](#phone-numbers-from-microsoft) | Microsoft에서 전화 번호를 얻고 관리하는 방법 및 기존 번호를 Microsoft로 전송하는 방법. Microsoft 통화 요금제에 대한 전화 번호를 획득하고 기존 번호를 전송하고, 서비스 번호를 확보해야 하는 경우 이 정보를 읽어 읽습니다. |
| [**전화 걸기 계획 및 통화 라우팅**](#dial-plans-and-call-routing) | 통화 권한 부여 및 통화 라우팅을 위해 전화 걸기 전화 번호를 대체 형식으로 변환하는 전화 요금제(일반적으로 E.164 형식)를 구성하고 관리하는 방법. 전화 걸기 계획의 대상과 조직의 전화 걸기 계획을 지정해야 하는지 이해해야 하는 경우 이 내용을 읽어 읽습니다.|
| [**긴급 통화**](#emergency-calling) | PSTN 연결 옵션에 따라 긴급 통화를 &mdash; 관리하고 구성하는 방법. Microsoft 통화 계획 또는 직접 라우팅을 사용하는 경우 조직에 대한 긴급 통화를 관리하는 방법을 이해해야 하는 경우 이 섹션을 참조하세요. |
| [**직접 라우팅에 대한 위치 기반 라우팅**](#location-based-routing-for-direct-routing) |LBR(Location-Based 라우팅)을 사용하여 해당 지리적 위치에 따라 Microsoft Teams 사용자에 대한 대금 우회를 제한하는 방법 조직에서 우회를 허용하지 않는 위치에서 직접 라우팅을 사용하는 경우 이 섹션을 읽습니다.
| [**클라우드 음성 기능에 대한 네트워크 토폴로지**](#network-topology-for-voice-features) | 조직에서 직접 라우팅 또는 동적 Location-Based LBR(라우팅)을 배포하는 경우 Microsoft Teams에서 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 합니다. 직접 라우팅에 대한 LBR을 구현하는 경우 또는 통화 계획 또는 직접 라우팅을 통해 동적 긴급 호출을 구현하는 경우 이 섹션을 참조하세요. |
| [**기존 음성 솔루션 마이그레이션**](#migrate-your-existing-voice-solution-to-teams) | 음성 솔루션을 Teams로 마이그레이션할 때 생각해야 할 일입니다.  기존 음성 솔루션에서 Teams로 마이그레이션하는 경우 이 섹션을 참조하세요. 



> [!Important]
> 이 문서에서는 Microsoft Teams를 사용할 수 있는 음성 솔루션에 중점을 비즈니스용 Skype Online 솔루션을 여전히 사용할 수 있는 [반면(Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)전화 통신 솔루션에 설명된 바와 같이) 비즈니스용 Skype Online이 2021년 7월 31일 사용 중지됩니다.  이 날짜 이후에는 비즈니스용 Skype Online 서비스에 더 이상 액세스할 수 없습니다. 또한 비즈니스용 Skype 서버 또는 Cloud Connector Edition 및 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 온라인 환경 간에 PSTN 연결은 지원되지 &mdash; &mdash; 않습니다. 이 문서에서는 Teams 음성 솔루션과 필요한 경우 직접 라우팅을 사용하여 Teams에 On-프레미스 전화 통신 네트워크를 연결할 수 있는 방법을 소개합니다.


## <a name="phone-system"></a>전화 시스템

전화 시스템은 Microsoft 365 또는 Office 365 클라우드에서 Microsoft Teams에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다.

Phone System은 Teams 또는 Skype for Business 클라이언트 및 인증된 디바이스와 함께 작동합니다. 전화 시스템을 사용하면 기존 PBX 시스템을 Microsoft 365 또는 Office 365에서 직접 배달하는 기능 집합으로 바꿀 수 있습니다. 

조직의 사용자 간 통화는 전화 시스템 내에서 내부적으로 처리하며 PSTN(공용 전환 전화 네트워크)으로 이동하지 않습니다. 이는 다른 지리적 영역에 있는 조직의 사용자 간 통화에 적용되어 이러한 내부 호출에 대한 장거리 비용이 제거됩니다.

이 문서에서는 다음 Phone System 주요 기능 및 기능을 소개하고, 고려해야 할 배포 결정을 소개합니다.

- [자동 전화 교환 및 통화 큐](#auto-attendants-and-call-queues)
- [클라우드 음성 메일](#cloud-voicemail)
- [ID 호출](#calling-identity)

![다이어그램 3에서는 전화 시스템에 자동 참석자 및 호출 쿼리, 클라우드 음성 문서 및 통화 ID가 포함되어 있습니다.](media/phone-system-contains.png)

모든 전화 시스템 기능 및 전화 시스템을 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [다음은 통화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)
- [조직에서 전화 시스템 설정](setting-up-your-phone-system.md)<br>
  전화 시스템 라이선스를 구입하고 할당하고, 전화 번호를 관리하고, 무료 번호에 대한 통신 크레딧을 설정하는 방법을 설명합니다. 

지원되는 디바이스 관리에 대한 자세한 내용은 [Microsoft Teams](devices/device-management.md) 및 Teams Marketplace에서 디바이스 [관리를 참조하세요.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>자동 참석자 및 통화 큐

자동 참석자는 발신자 입력에 따라 호출을 라우팅하도록 메뉴 옵션을 설정할 수 있습니다. 호출 큐는 발신자 대기 영역입니다. 함께 사용되는 자동 참석자 및 통화 큐는 조직의 적절한 사람 또는 부서로 발신자 라우팅을 쉽게 할 수 있습니다.

자동 참석자 및 호출 큐에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Teams 자동 참석자 및 호출 큐 계획](plan-auto-attendant-call-queue.md)
- [자동 참석자 설정](create-a-phone-system-auto-attendant.md)
- [통화 큐 만들기](create-a-phone-system-call-queue.md) 
- [Contoso 사례 연구: 자동 참석자 및 통화 큐](voice-case-study-call-queues.md)<br>
  소설적 다국적 기업 Contoso가 음성 솔루션에 대한 자동 참석자 및 호출 큐를 구현하는 방법을 설명합니다.

### <a name="cloud-voicemail"></a>클라우드 음성 메일

Azure Voicemail 서비스에서 제공하는 Cloud Voicemail은 Exchange 사서함에만 음성 메일 예금을 지원합니다. 타사 전자 메일 시스템을 지원하지 않습니다. 

클라우드 음성 사서함에는 기본적으로 조직의 모든 사용자가 사용할 수 있는 음성 메일 기록이 포함됩니다. 비즈니스 요구에 따라 조직 전체의 특정 사용자 또는 모든 사용자에 대한 음성사본 전사 기능을 사용하지 않도록 설정해야 할 수 있습니다.

온라인 전용 사용자의 경우 전화 시스템 라이선스가 할당된 후에 Cloud Voicemail이 자동으로 설정되고 프로비전됩니다. Exchange 사서함이 있는 Phone System 사용자의 경우 추가 구성 단계를 수행해야 합니다. 

Cloud Voicemail 및 해당 구성에 대한 자세한 내용은 다음 문서를 참조하세요.

- [클라우드 음성 메일 설정](set-up-phone-system-voicemail.md)
- [조직의 음성메일 정책 설정](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>ID 호출

기본적으로 모든 아웃바운드 호출은 할당된 전화 번호를 호출 ID(발신자 ID)로 사용됩니다. 전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다. 발신자 ID를 구성하거나 발신자 ID를 변경하거나 차단하는 데 대한 자세한 내용은 사용자에 대한 [발신자 ID 설정을 참조하세요.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>공용 전환된 전화 네트워크 연결 옵션

Phone System은 조직에 대한 완전한 PBX 기능을 제공합니다. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 설정하려면 전화 시스템을 PSTN(공용 전환 전화 네트워크)에 연결해야 합니다. 전화 시스템을 PSTN에 연결하기 위해 다음 옵션 중 하나를 선택할 수 있습니다.

- [**통화 계획이 있는 전화 시스템.**](#phone-system-with-calling-plan) PSTN 통신사로 Microsoft를 사용할 수 있는 올인원 클라우드 솔루션입니다.

- 직접 라우팅을 사용하여 자체 [**PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) 통신사와 전화 시스템으로 프레미스 환경을 Teams에 연결합니다.

복잡한 환경에 대한 솔루션을 디자인하거나 다단계 마이그레이션을 관리할 수 있는 옵션의 조합을 선택할 수도 있습니다(나중에 마이그레이션에 대한 자세한 내용은).

### <a name="phone-system-with-calling-plan"></a>통화 계획이 있는 전화 시스템 

이 문서의 앞부분에서 설명한 대로 통화 계획이 있는 전화 시스템은 Teams 사용자를 위한 Microsoft의 올인원 클라우드 음성 솔루션입니다. 전 세계 유선 전화 및 휴대폰에 대한 통화를 사용하도록 설정하기 위해 PSTN(공용 전환 전화 네트워크)에 Microsoft Phone System을 연결하는 가장 간단한 옵션입니다. 이 옵션을 사용하면 Microsoft는 조직에 대한 PBX(Private Branch Exchange) 기능을 제공하며 다음 다이어그램과 같이 PSTN 통신 사업자 역할을 합니다.

![다이어그램 4에서는 자동 전화 시스템, 전화 큐, 발신자 ID 등 PSTN 통신사로 Microsoft를 보여줍니다.](media/voice-solution-microsoft-complete.png)

다음에 예로 대답하면 전화 요금제가 있는 전화 시스템이 적합한 솔루션입니다.

- 통화 요금제는 지역에서 사용할 수 있습니다.
- 현재 PSTN 캐리어를 유지할 필요가 없습니다.
- PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우

이 옵션을 사용합니다. 

- 전 세계 휴대폰에 전화를 걸 수 있는 추가 국내 또는 국제 전화 요금제가 있는 Microsoft Phone System을 사용할 수 있습니다(라이선스가 부여되는 서비스 수준에 따라 다를 수 있습니다.

- 호출 계획은 &mdash; Microsoft 365 또는 Office 365에서 작동하기 때문에 프레미스 배포의 배포 또는 유지 관리가 필요하지 않습니다.

- 참고: 필요한 경우 SBC에서 지원하는 타사 PBX, 아날로그 디바이스 및 기타 타사 전화 통신 장비와 상호 연동성을 위해 직접 라우팅을 통해 지원되는 SBC(세션 경계 컨트롤러)를 연결할 수 있습니다.

이 옵션은 Microsoft 365 또는 Office 365에 대한 끊임 없는 연결이 필요합니다.

통화 계획에 대한 자세한 내용은 다음 문서를 참조하세요.

- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 플랜을 구입하는 방법](calling-plans-for-office-365.md)
- [통화 플랜의 국가 및 지역 가용성](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [통화 계획 설정](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>직접 라우팅이 있는 자체 PSTN 통신사가 있는 전화 시스템

이 옵션은 다음 다이어그램과 같이 직접 라우팅을 사용하여 Microsoft Phone System을 전화 통신 네트워크에 연결합니다. 

![다이어그램 5에서는 직접 라우팅이 있는 전화 시스템 표시](media/voice-solution-with-direct-routing.png)

다음 질문에 예로 대답하면 직접 라우팅이 있는 전화 시스템이 적합한 솔루션입니다.

- Teams를 전화 시스템과 함께 사용하려는 경우
- 현재 PSTN 캐리어를 유지해야 합니다.
- 라우팅을 혼합하고, 일부 호출은 통신사를 통해 통화 계획을 통해 진행됩니다.
- 타사 PBX 및/또는 오버헤드 페이지, 아날로그 디바이스 등의 장비와 상호 협력해야 합니다.

이 옵션을 사용합니다.

- 추가 프레미스 소프트웨어 없이도 지원되는 SBC를 Microsoft Phone System에 연결합니다.

- Microsoft Phone System에서 거의 모든 전화 통신 통신을 사용할 수 있습니다.

- 이 옵션을 구성하고 관리하도록 선택하거나 이동통신사 또는 파트너가 구성하고 관리할 수 있습니다(이동통신사 또는 파트너가 이 옵션을 제공하는지 묻는 질문).

- 타사 PBX와 아날로그 디바이스 및 Microsoft Phone System과 같은 전화 통신 장비 간에 상호 &mdash; &mdash; 운영성을 구성할 수 있습니다.


이 옵션에는 다음이 필요합니다.

- Microsoft 365 또는 Office 365에 대한 끊임 없는 연결.

- 지원되는 SBC를 배포하고 유지 관리합니다.

- 타사 통신사와의 계약입니다.
  (통화 요금제가 있는 전화 시스템에 있는 사용자를 위해 타사 PBX, 아날로그 디바이스 또는 기타 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포되지 않는 한).)

직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.

- [전화 시스템 직접 라우팅](direct-routing-landing-page.md)
- [직접 라우팅 계획](direct-routing-plan.md)
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅에서 사용할 음성 라우팅 정책 관리](manage-voice-routing-policies.md)
- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Microsoft의 전화 번호

Microsoft에는 구독자(사용자)  번호와 조직의 사용자에게 할당할 수 있는 전화 번호와  무료 서비스 번호로 사용할 수 있는 서비스 번호의 두 가지 유형이 있습니다. 서비스 번호는 구독자 번호보다 동시 호출 용량이 높고 오디오 회의, 자동 참석자 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.

다음을 결정해야 합니다.

- Microsoft에서 새 전화 번호가 필요한 사용자 위치는 무엇입니까?
- 어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요? 
- 기존 전화 번호를 Teams에 이식하는 방법

새 번호 또는 나가는 번호 전송을 포함하여 조직의 전화 번호 관리에 대한 자세한 내용은 다음 문서를 참조하세요.

- [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [통화 계획에 사용되는 다양한 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [사용자의 전화 번호 가져오기](getting-phone-numbers-for-your-users.md)
- [Microsoft Teams로 전화 번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>전화 걸기 계획 및 통화 라우팅

다이얼 플랜은 통화 권한 부여 및 통화 라우팅을 위해 전화 걸기 전화 번호를 대체 형식(일반적으로 E.164 형식)으로 변환하는 정규화 규칙 집합입니다.

다음을 결정해야 합니다. 

- 조직에 사용자 지정 다이얼 플랜이 필요한가요?
- 사용자 지정 다이얼 플랜이 필요한 사용자는 무엇입니까?
- 각 사용자에게 어떤 테넌트 다이얼 플랜을 할당해야 하나요?

자세한 내용은 다음 문서를 참조하세요. 

- [다이얼 플랜이 무엇인가요?](what-are-dial-plans.md)
- [테넌트 다이얼 계획](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>비상 전화

긴급 통화를 구성하는 방법은 PSTN 연결 옵션인 Microsoft 통화 계획 또는 직접 라우팅에 따라 다릅니다. Microsoft 통화 계획 및 전화 시스템 직접 라우팅에 대한 동적 긴급 호출은 Teams 클라이언트의 현재 위치에 따라 긴급 통화를 구성하고 라우팅하고 보안 담당자에게 알릴 수 있는 기능을 제공합니다. 긴급 호출 개념 및 용어 및 동적 긴급 호출을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md)
- [Contoso 사례 연구: 긴급 통화](voice-case-study-emergency-calling.md)<br>
  소설적 다국적 기업 Contoso가 조직에 대한 긴급 호출을 구현하는 방법을 설명합니다.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based 라우팅에 대한 Location-Based 라우팅

일부 국가 및 지역에서는 PSTN(공용 전환 전화 네트워크) 공급자를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다. Location-Based 라우팅을 사용하면 해당 지리적 위치에 따라 Microsoft Teams 사용자에 대한 대금 우회를 제한할 수 있습니다. LBR(라우팅)을 계획하고 Location-Based 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅의 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Contoso 사례 연구: Location-Based 라우팅](voice-case-study-location-based-routing.md)<br>
  소설 다국적 기업인 Contoso가 조직에 대한 라우팅을 Location-Based 방법을 설명합니다.

## <a name="network-topology-for-voice-features"></a>음성 기능에 대한 네트워크 토폴로지

동적 긴급 통화를 배포하거나 직접 라우팅에 Location-Based 라우팅을 배포하는 경우 Microsoft Teams에서 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 합니다. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft Teams의 클라우드 음성 기능에 대한 네트워크 설정 - 개념 및 용어](cloud-voice-network-settings.md)
- [Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>기존 음성 솔루션을 Teams로 마이그레이션

Teams로 업그레이드하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다. Teams와 전화 시스템 사용은 사용자가 TeamsOnly 모드일 때만 지원됩니다. Teams로 업그레이드하는 데 대한 기본 정보가 필요한 경우 여기에서 시작하세요.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [업그레이드 프레임워크 정보](upgrade-framework.md)
- [IT 관리자를 위한 업그레이드 전략](upgrade-to-teams-on-prem-implement.md)

음성 솔루션을 마이그레이션할 때 TeamsOnly 모드로 전환할 때 다음과 같은 4개의 가능한 호출 시나리오가 있습니다.

- Microsoft 통화 계획이 있는 [**비즈니스용 Skype Online의 사용자입니다.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) 업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다.

- **[비즈니스용 Skype Online의 사용자로,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 버전 을 통해 프레미스 음성 기능을 제공합니다. Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능을 보장하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 방법을 조정해야 합니다.

- 온라인으로 이동하고 Enterprise Voice PSTN 연결을 유지하는 비즈니스용 **[Skype온-프레미스](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 사용자입니다. 이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고, 사용자의 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다. 

- **[비즈니스용 Skype온-Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)사용자가** 온라인으로 이동하고 Microsoft 통화 요금제 를 사용할 것입니다.  이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.

하이브리드 연결을 설정해야 하는 경우와 직접 라우팅으로 사용자를 마이그레이션하는 방법에 대한 정보를 포함하여 이러한 각 시나리오에 대한 음성 마이그레이션을 구현하는 방법에 대한 자세한 내용은 다음 문서를 &mdash; &mdash; 참조하세요.

- [IT 관리자를 위해 Teams로 업그레이드할 때 PSTN 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 음성 마이그레이션 사례 연구](voice-case-study-overview.md)<br>
  사례 연구에서는 다국적 기업인 Contoso가 조직에 대해 Teams 음성 솔루션을 구현하는 방법을 설명합니다. 이 문서에는 다음 문서가 포함되어 있습니다.

  - [팀 업그레이드 계획](voice-case-study-migration-plan.md)
  - [전화 시스템 및 PSTN 연결 옵션](voice-case-study-phone-system.md)
  - [위치 기반 라우팅 구현](voice-case-study-location-based-routing.md)
  - [긴급 통화](voice-case-study-emergency-calling.md)
  - [자동 전화 교환 및 통화 큐](voice-case-study-call-queues.md)
  - [오디오 회의](voice-case-study-audio-conferencing.md)












