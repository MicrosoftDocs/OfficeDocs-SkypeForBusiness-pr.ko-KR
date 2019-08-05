---
title: Microsoft 전화 통신 솔루션
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Microsoft 전화 통신 솔루션에 대해 설명 합니다.
ms.openlocfilehash: 57d1abe69bc0513fa015543e8440e9d9f778b78c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185442"
---
# <a name="microsoft-telephony-solutions"></a>Microsoft 전화 통신 솔루션

Microsoft는 Microsoft 클라우드에서 팀으로 여행을 시작할 때 몇 가지 옵션을 지원 합니다. 이 문서는 조직의 사용자에 게 적합 한 Microsoft 전화 통신 솔루션 (클라우드 또는 Enterprise Voice 온-프레미스)을 결정 하는 데 도움이 되 고, 조직이 PSTN (공개 교환 전화 네트워크)에 연결 하는 방법에 대해 설명 합니다. 

이 문서를 관련 기술 다이어그램과 함께 사용 하 여 조직에 적합 한 의사 결정을 내리는 데 도움이 되는 시각을 제공 해야 합니다.

- [Microsoft 전화 통신 솔루션-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Microsoft 전화 통신 솔루션-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>PBX (개인 브랜치 교환) 옵션

### <a name="phone-system-office-365"></a>전화 시스템 (Office 365)
  
전화 시스템은 Microsoft 팀 및/또는 비즈니스용 Skype Online을 사용 하 여 Office 365 클라우드에서 통화 제어 및 개인 브랜치 교환 (PBX) 기능을 사용 하도록 설정 하기 위한 Microsoft의 기술입니다. 

전화 시스템은 팀 또는 비즈니스용 Skype Online 클라이언트 및 인증 된 장치에서 작동 합니다. 전화 시스템을 사용 하면 기존 PBX 시스템을 Office 365에서 직접 제공 되는 기능 집합으로 대체 하 고 회사의 클라우드 생산성 환경에 긴밀 하 게 통합할 수 있습니다. 휴대폰 시스템을 PSTN (공개 통신 네트워크)에 연결 하려면 Microsoft의 통화 요금제 또는 자신의 전화 통신 회사를 선택 하면 됩니다.

자세한 내용은 [Office 365의 전화 시스템을](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365)참조 하세요.

### <a name="enterprise-voice-skype-for-business-server"></a>엔터프라이즈 음성 (비즈니스용 Skype 서버)

Enterprise Voice는 온-프레미스 비즈니스용 Skype 서버에서 통화 제어 및 PBX (개인 브랜치 교환) 기능을 사용 하도록 설정 하기 위한 Microsoft의 기술입니다. 이 옵션은 개인 전화 통신 회사를 사용 하 여 공개 전환 전화 네트워크에만 연결할 수 있습니다. 

자세한 내용은 [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)을 참조 하세요.

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>PSTN (공개 통신 네트워크) 옵션에 대 한 연결

다음과 같은 방법으로 PSTN (공용 전환 전화 네트워크)에 연결 하도록 선택할 수 있습니다.

- Office 365에서 Microsoft 통화 계획 사용 
- 고유한 전화 통신 회사 연결

### <a name="calling-plan-office-365"></a>통화 요금제 (Office 365)

이 옵션은 Microsoft Office 365 전화 시스템을 PSTN (공개 교환 전화 네트워크)에 연결 하 여 전 세계의 유선전화 및 휴대 전화로 전화를 걸 수 있도록 합니다. 통화 요금제를 사용 하 여 Microsoft는 PSTN 통신 회사입니다.

자세한 내용은 [Office 365에 대 한 요금제 호출](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365)을 참조 하세요.

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>고유한 전화 통신 회사 (Office 365 및 비즈니스용 Skype 온-프레미스) 연결

이 옵션은 비즈니스용 Skype 온-프레미스에서 Office 365 또는 Enterprise Voice system의 전화 시스템을 전화 통신 네트워크로 연결 합니다. 이 옵션에는 지원 되는 세션 경계 컨트롤러 (SBC)가 필요 합니다. 이 옵션을 선택 하는 경우에는 온-프레미스에 추가 Microsoft 소프트웨어를 배포 해야 할 수도 있습니다.

## <a name="which-solution-is-right-for-your-organization"></a>조직에 적합 한 솔루션은 무엇 인가요?

모든 클라우드 솔루션, 소유 통신 회사 연결 솔루션 또는 모든 사용자와 타사 통신 회사 간의 혼합 기능을 선택할 수 있습니다. 다음을 수행 합니다.

- 통화 요금제가 포함 된 전화 시스템 (클라우드에서 모두)

- 직접 경로 지정을 통한 자체 통신 전화 시스템

- 비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 통한 자체 통신 전화 시스템

- 자체의 캐리어가 있는 비즈니스용 Skype 서버의 엔터프라이즈 음성

다음과 같은 현재 및 미래 요구 사항에 따라 다른 솔루션이 선택 됩니다.

- 온-프레미스 배포에서 제공 하는 기능을 유지 하 고 필요한 지 여부를 지정 합니다.
- 사용자를 위해 배포할 클라이언트를 선택 합니다.
- 사용자를 클라우드로 이동 하는 계획은 무엇 인가요?
- 타사 Pbx 및 기타 전화 통신 장비와 상호 운용 해야 하는지 여부

다음 질문을 고려 하 여 조직에 가장 적합 한 솔루션을 결정 합니다.

- 기존 비즈니스용 Skype 서버 배포를 사용 하 고 계십니까?
- 사용자가 온-프레미스 비즈니스용 Skype (비즈니스용 Skype Online의 경우) 또는 둘 다에 속한 경우 
- 온-프레미스 사용자를 클라우드로 이동 하 시겠습니까?
- Microsoft의 PSTN 통화 요금제는 해당 지역에서 사용할 수 있나요?
- 현재 전화 통신 회사를 유지 하 고 싶으신가요?  예를 들어 기존 계약으로 인해 현재 통신 회사를 유지 해야 하나요?
- 기존 온-프레미스 레거시 PBX가 필요 하거나 유지 해야 하나요?
- 현재 레거시 PBX가 귀하의 비즈니스에 중요 한 고유한 기능을 제공 하나요?
- 일부 또는 모든 사용자에 게 현재 전화 시스템에서 제공 되지 않는 기능이 필요 한가요?

다음 사항에 유의 하세요.

- 복잡 한 환경에 맞게 솔루션을 디자인 하거나 다단계 마이그레이션을 관리 해야 하는 경우에는 네 가지 옵션이 모두 함께 공존할 수 있습니다.
- 비즈니스용 Skype Server 또는 클라우드 커넥터 에디션을 통해 자체 통신 사업자를 사용 하는 전화 시스템은 비즈니스용 Skype 서버 또는 클라우드 커넥터로만 배포할 수 있습니다. 단일 회사에서는 비즈니스용 Skype 서버와 클라우드 커넥터의 공존을 지원 하지 않습니다.

## <a name="phone-system-with-calling-plan"></a>통화 요금제가 포함 되어 있는 전화 시스템


전화 플랜은 다음 다이어그램에 표시 된 것 처럼 팀 또는 비즈니스용 Skype Online 사용자에 대 한 클라우드 (전체 기능) 옵션입니다.

![통화 요금제가 포함 되어 있는 전화 시스템](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- 사용 허가를 받은 서비스 수준에 따라 전세계의 전화로 전화를 걸 수 있도록 하는 국내 또는 국제 통화 계획이 추가 된 Microsoft 전화 시스템입니다. 
- PSTN 통화 요금제가 Office 365에서 작동 하기 때문에이 옵션에는 온-프레미스 배포를 배포 하거나 유지 관리할 필요가 없습니다.
- 고객은 타사 PBX, 아날로그 장치, SBC에서 지원 되는 기타 타사 통신 장비와의 상호 운용성을 위해 직접 라우팅을 통해 지원 되는 SBC에 연결할 수 있습니다.

| 인프라 요구 사항                   | 필수?|
| :----------------------------------------------------| ---------:|
| Office 365에 대 한 중단 없는 연결 필요 | ' |
| 전세계 사용 가능 *                            | 아니요  |
| 지원 되는 세션 경계 컨트롤러 (SBC) 배포 및 유지 관리 필요 | 아니요 |
| 타사 통신 업체와 계약 필요      | 아니요   |
| 비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 배포 하 고 유지 관리 해야 합니다. | 아니요 |

\*통화 요금제를 사용할 수 있는 국가에 대 한 자세한 내용은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](https://docs.microsoft.com/en-us/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)을 참조 하세요.


예를 들어 다음 질문에 대답 하는 경우에는 다음과 같은 해결 방법이 적합 합니다.

- 전화 요금제는 해당 지역에서 사용할 수 있습니다.
- 현재 PSTN 통신 회사를 유지할 필요는 없습니다.
- Microsoft에서 관리 하는 PSTN (공개 통신 네트워크)에 대 한 액세스를 사용 하려고 합니다.
- 세션 경계 컨트롤러를 직접 관리 하지 않으려는 경우
- 팀 및/또는 비즈니스용 Skype Online에는 조직에서 필요로 하는 모든 기능이 포함 되어 있습니다.

자세한 내용은 office [365의 전화 시스템 소개](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) 및 [office 365에 대 한 통화 계획](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365)을 참조 하세요.

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>직접 경로 지정을 통한 자체 통신 전화 시스템

이 옵션은 팀 사용자를 위한 거의 모든 통신 통신 사업자를 사용 하 여 클라우드에서 Microsoft 전화 시스템을 제공 합니다.

![다이렉트 라우팅을 통한 통신 시스템 전화](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- 추가 온-프레미스 소프트웨어 없이도 직접 지원 되는 SBC를 Microsoft 전화 시스템에 연결할 수 있습니다.  
- Microsoft 전화 시스템을 사용 하 여 거의 모든 통신 사업자를 사용 합니다.
- 고객 또는 통신 회사 또는 파트너가 구성 하 고 관리할 수 있습니다 (통신 회사 또는 파트너가이 옵션을 제공 하는지 확인).
- 전화 통신 장비 (예: 타사 PBX 및 아날로그 장치)와 Microsoft 전화 시스템 간의 상호 운영성을 구성 합니다.

| 인프라 요구 사항                   | 필수?|
| :----------------------------------------------------| ---------:|
| Office 365에 대 한 중단 없는 연결 필요 | ' |
| 전세계에서 사용 가능                            | '  |
| 지원 되는 세션 경계 컨트롤러 (SBC) 배포 및 유지 관리 필요 | ' |
| 타사 통신 업체와의 계약 필요 *      | '   |
| 비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 배포 하 고 유지 관리 해야 합니다. | 아니요 |

\*전화 시스템을 사용 하는 사용자를 위해 타사 PBX, 아날로그 장치 또는 기타 전화 통신 장비에 연결을 제공 하는 옵션으로 배포 되지 않는 한, 통화 요금제

예를 들어 다음 질문에 대답 하는 경우에는 다음과 같은 해결 방법이 적합 합니다.

- 전화 시스템에서 팀을 사용 하려는 경우
- 현재 PSTN 통신 회사를 유지 해야 합니다.
- 통신을 혼합할 때 일부 통화는 통화 요금제를 통해 수행 되 고
- 타사 Pbx 및/또는 장비 (예: 미국 오버 헤드 호출기, 아날로그 장치)와 상호 운용 해야 하는 경우
- 팀에는 조직에서 필요로 하는 모든 기능이 있습니다.

자세한 내용은 [Office 365의 전화 시스템 소개](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) 및 [직접 라우팅 계획](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan)을 참조 하세요.


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 통한 자체 통신 전화 시스템

이 옵션은 비즈니스용 Skype Online 사용자를 위한 온-프레미스 전화 접속 네트워크 연결을 사용 하 여 클라우드에서 Microsoft Phone 시스템을 제공 합니다.

![비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 통한 통신 사업자 용 전화 시스템](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - 비즈니스용 Skype Server 또는 온-프레미스 비즈니스용 Skype 클라우드 커넥터 에디션을 통해 지원 되는 SBC를 Microsoft 전화 시스템에 연결 하세요. 
- Microsoft 전화 시스템을 사용 하 여 거의 모든 통신 사업자를 사용 합니다. 
- 온-프레미스 비즈니스용 Skype Server를 이미 보유 하 고 있는 경우,이를 이용할 수 있습니다.  그렇지 않으면 더 가벼운 버전의 클라우드 커넥터 에디션을 배포할 수 있습니다.


| 인프라 요구 사항                   | 필수?|
| :----------------------------------------------------| ---------:|
| Office 365에 대 한 중단 없는 연결 필요 | ' |
| 전세계에서 사용 가능                            | '  |
| 지원 되는 세션 경계 컨트롤러 (SBC) 배포 및 유지 관리 필요 | ' |
| 타사 통신 업체와 계약 필요      | '   |
| 비즈니스용 Skype 서버 또는 클라우드 커넥터 에디션을 배포 하 고 유지 관리 해야 합니다. | ' |



예를 들어 다음 질문에 대답 하는 경우에는 다음과 같은 해결 방법이 적합 합니다.

- 사용자에 게 비즈니스용 Skype Online을 사용 하려는 경우
- 해당 지역에서는 PSTN 통화 요금제를 사용할 수 없습니다.
- 현재 PSTN 통신 회사를 유지 해야 합니다.

자세한 내용은 [Office 365의 전화 시스템](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365), 비즈니스용 [skype Server 2019](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-server-2019)및 비즈니스용 [skype 클라우드 커넥터 에디션 계획](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)을 참조 하세요.

권장 사항: 비즈니스 조건이 변경 되는 경우, 예를 들어 더 이상 PSTN 통신 회사를 유지할 필요가 없으며 옵션 1 또는 2를 사용 하 여 Microsoft 팀으로 이동 하는 것이 좋습니다.
- 유지 관리 비용 최소화
- Microsoft에서 릴리스된 최신 기능에 액세스할 수 있습니다.

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>자체의 캐리어가 있는 비즈니스용 Skype 서버의 엔터프라이즈 음성

이 옵션은 비즈니스용 Skype 온-프레미스 사용자에 대 한 온-프레미스 전화 접속 네트워크 연결을 사용 하 여 Enterprise Voice 온-프레미스를 제공 합니다.

![자체의 캐리어가 있는 비즈니스용 Skype 서버의 엔터프라이즈 음성](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- 비즈니스용 Skype 온-프레미스 서버에서 지원 되는 SBC를 Enterprise Voice System에 연결 합니다.
- 지역 survivability 필요한 경우 사용 합니다.
- Microsoft 전화 시스템을 사용 하 여 거의 모든 통신 사업자를 사용 합니다. 
- 배포 및 유지 관리를 위한 가장 복잡 한 옵션입니다.

| 인프라 요구 사항                   | 필수?|
| :----------------------------------------------------| ---------:|
| Office 365에 대 한 중단 없는 연결 필요 | 아니요 |
| 전세계에서 사용 가능                            | '  |
| 지원 되는 세션 경계 컨트롤러 (SBC) 배포 및 유지 관리 필요 | ' |
| 타사 통신 업체와 계약 필요      | '   |
| 비즈니스용 Skype 서버를 배포 하 고 유지 관리 해야 합니다. | ' |

자세한 내용은 [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)을 참조 하세요.

권장 사항: 비즈니스 조건이 변경 되는 경우, 예를 들어 더 이상 PSTN 통신 회사를 유지할 필요가 없으며 옵션 1 또는 2를 사용 하 여 Microsoft 팀으로 이동 하는 것이 좋습니다.
- 유지 관리 비용 최소화
- Microsoft에서 릴리스된 최신 기능에 액세스할 수 있습니다.











  
