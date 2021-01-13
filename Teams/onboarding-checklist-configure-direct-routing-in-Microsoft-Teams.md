---
title: 온보드 검사 목록 - 직접 라우팅 구성 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams에서 직접 라우팅을 구성할 때 이 검사 목록의 핵심 할 일 작업 및 활동을 수행합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 19a196c9a995bf146e2737ff72b298a0be2b3392
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812928"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>Microsoft Teams에서 직접 라우팅 구성

## <a name="direct-routing"></a>직접 라우팅

| 아니요 | 작업 또는 작업 | 설명 | 완료된 경우 | 추가 정보 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|조직의 위치에 배포할 PSTN 연결 결정|Microsoft는 Microsoft 365 또는 Office 365 Phone System을 사용하여 사용자에게 PSTN 연결을 제공하는 대체 방법을 제공합니다.<ul><li>통화 플랜이 있는 전화 시스템("통화 요금제"): 비즈니스용 Skype Online 및 Teams<li>전화 시스템 직접 라우팅("직접 라우팅"): Teams만 해당<li>전화 시스템과 프레미스 PSTN 연결: 비즈니스용 Skype Online만 해당<li>비즈니스용 Skype 클라우드 커넥터 버전: 비즈니스용 Skype Online만 해당</ul>직접 라우팅은 PSTN 연결이 Microsoft가 아닌 타사 공급자가 용이하다는 것을 제외하고는 조직에 통화 요금제와 동일한 이점을 제공합니다. 이렇게 하면 통화 계획을 사용할 수 없는 국가 또는 기존 PSTN 서비스 공급자 계약을 유지 관리해야 하는 배포 또는 특정 On-프레미스 시스템과의 상호 운영성이 필요한 배포에 사용할 수 있습니다.<br><br>조직에 가장 적합한 옵션을 결정하세요. | |[오디오 회의 및 통화 요금제 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[오디오 회의 및 통화 계획에 대한 온보드 검사 목록](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|직접 라우팅을 사용하도록 설정하기 위한 사용자 목록 및 배포 케이던스 확인|Teams를 통해 직접 라우팅 범위에 있는 사업부 또는 사이트 목록이 있는지 검사합니다. 목표 및 주요 결과 모델을 사용하여 직접 라우팅 범위에 포함되는 사용자를 해결합니다. 리소스에 집중할 수 있도록 사이트 기준으로 작업하는 것이 좋습니다.<br><br>사용 계획의 일부로 언제(파일럿, 사이트 1, 사이트 2 등)를 사용하도록 설정할 사용자를 식별합니다.||[직접 라우팅에 대한](2-envision-make-my-service-decisions-direct-routing.md)|
|3|라이선스 계획 및 얻기|직접 라우팅 사용자는 Microsoft 365 또는 Office 365에 할당된 다음 라이선스가 있어야 합니다.<ul><li>비즈니스용 Skype Online(요금제 2)<li>Microsoft Phone System<li>Microsoft Teams<li>Microsoft 오디오 회의</ul>직접 라우팅은 통화 요금제에 대한 라이선스가 있는 사용자도 지원됩니다. 통화 계획이 있는 전화 시스템은 직접 라우팅 인터페이스를 사용하여 일부 호출을 라우팅할 수 있습니다.<br><br>오디오 회의 라이선스는 외부 참가자에게 전화를 걸거나 전화 접속 번호를 제공하여 예약된 모임에 외부 참가자를 추가하는 데 필요합니다.||[직접 라우팅 라이선스](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|세션 경계 컨트롤러(SBC) 도메인 이름 계획|SBC 도메인 이름은 테넌트의 "Domains"에 등록된 이름 중 하나에서 시작해야 합니다.<br><br>**참고:** SBC의 FQDN(onmicrosoft.com 도메인 이름)에는 *.onmicrosoft.com 사용할 수 없습니다.<br><br>SBC 도메인 이름은 각 SBC에 필요한 인증서를 계획하는 데도 중요합니다.||[SBC 도메인 이름](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|인증서 계획|CSR(인증 서명 요청)을 생성하여 SBC에 대한 인증서를 요청하는 것이 좋습니다.<br><br>인증서는 주체, 일반 이름 또는 주체 대체 이름 필드에 SBC FQDN이 필요합니다. 또는 직접 라우팅은 일반 이름 또는 주체 대체 이름에 와일드카드를 지원합니다.<br><br>SBC용 CSR 생성에 대한 구체적인 지침은 SBC 공급업체에서 제공하는 설명서를 참조하세요.<br><br>추가 정보 **열의** 문서에는 지원되는 루트 인증 기관이 나열됩니다.||[SBC에 대한 공용 신뢰할 수 있는 인증서](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|방화벽 포트 계획 및 구성|직접 라우팅에 대한 연결점은 다음 세 가지 FQDNS입니다.<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>이러한 연결점과 SBC 간의 트래픽은 회사 방화벽에서 허용되어야 합니다. SBC를 구성할 때 SBC에서 TCP 포트를 정의합니다.<br><br>미디어 트래픽은 UDP에 있습니다. 이 유형의 트래픽은 미디어 프로세서 구성 요소에서 흐르고 있습니다. SBC와 미디어 프로세서 간의 양방향 트래픽도 방화벽에서 허용되어야 합니다.<br><br>**참고:** 미디어 프로세서에는 동적 IP 주소가 있으며 고정 IP 주소는 나중에 사용할 수 있습니다. Azure 데이터 센터 IP 범위에 나열된 IP 주소를 허용하는 [것이 중요합니다.](https://www.microsoft.com/download/details.aspx?id=41653)||[SIP 신호: FQDNs 및 방화벽 포트](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[미디어 트래픽: IP 주소 및 포트 범위](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 데이터 센터 IP 범위](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|SBC 구성|Microsoft는 직접 라우팅과 쌍을 이루는 인증된 SBC만 지원됩니다.<br><br>추가 정보 열에 있는 문서의 공급업체별 지침 및 지침을 사용하여 SBC를 **구성합니다.**||[지원되는 SBC(세션 테두리 컨트롤러)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|8|직접 라우팅과 SBC 페어링|각 사이트의 SBC는 직접 라우팅과 쌍을 이루어 사용자 자신의 트렁크를 사용하여 다이얼톤 및 PSTN 통화 기능을 제공해야 합니다.<br><br>특정 사이트의 SBC가 직접 라우팅과 이미 쌍으로 연결되어 있는지 확인하거나, 전에 수행하지 않은 경우 쌍을 구성합니다.<br><br>Microsoft는 직접 라우팅과 쌍을 이루는 인증된 SBC만 지원합니다. 이 사이트의 SBC가 인증된지 유효성을 검사합니다.||[SBC와 전화 시스템의 직접 라우팅 서비스 페어링](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|SBC 페어링 유효성 검사|특정 사이트에 대해 페어링한 각 SBC에 대해 cmdlet을 실행하고 Enabled 매개 변수가 `Get-CsOnlinePSTNGateway` **True** 값을 표시하는지 **확인합니다.**<br><br>SBC 관리 인터페이스를 사용하여 SBC가 발신 SIP 옵션에 **대해 200개 "확인"**  응답을 받을지 확인할 수 있습니다.|||
|10|사용자 구성 유효성 검사|디렉터리 동기화를 사용하여 사용자 계정이 직접 만들어지거나 Microsoft 365 또는 Office 365에 동기화되도록 합니다.<br><br>필요한 라이선스가 사용자에게 할당되어 있는지 확인<br><br>직접 라우팅과 PSTN을 연결하려면 사용자가 비즈니스용 Skype Online에 있어야 합니다. Microsoft Teams를 사용하도록 설정해야 합니다.||[직접 라우팅 서비스에 대해 사용자 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|사용자의 전화 번호 구성|직접 라우팅 범위에 있는 모든 사용자에게는 전화 번호와 음성메일이 할당되어야 합니다.<br><br> `Set-CsUser`cmdlet을 사용하여 음성메일을 사용하도록 설정하고 사용자에게 전화 번호를 할당합니다.||[전화 번호 구성 및 엔터프라이즈 음성 및 음성 이메일 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|12|음성 라우팅 구성|전화 시스템에는 통화를 특정 SBC로 보낼 수 있는 라우팅 메커니즘이 있습니다.<ul><li>호출된 숫자 패턴<li>호출된 번호 패턴 + 호출하는 특정 사용자</ul>다음을 만들어 사용자에 대한 음성 라우팅을 구성합니다.<ul><li>음성 라우팅 정책<li>PSTN 사용 현황<li>음성 경로<li>온라인 PSTN 게이트웨이</ul>||[음성 라우팅 구성](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|사용자의 기본 통화 클라이언트로 Microsoft Teams 설정|사용자가 Microsoft Teams에서 통화 탭을 볼 수  있도록 하기 전에 Microsoft Teams에서 테넌트에 대해 비공개  통화를 사용하도록 설정해야 합니다. Teams 클라이언트는 사용자의 기본 통화 클라이언트로 구성되어야 합니다. ||[Microsoft Teams에 대한 통화 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[사용자의 기본 통화 클라이언트로 Microsoft Teams 설정](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|직접 라우팅에 대해 사용자 사용|구성된 SBC를 통해 직접 라우팅을 사용하여 PSTN 통화를 걸고 받을 사용자에게 음성 라우팅 정책을 할당합니다.||[직접 라우팅 서비스에 대해 사용자 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|15|사용자 승인 테스트 준비 및 실행|전화 접속 및 전화 걸기 시나리오를 포함하여 사용자 승인 테스트를 준비하고 실행합니다.||[Teams에서 클라우드 음성 워크로드 테스트](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|사용량, 상태, KSIS(주요 성공 지표) 및 품질 보고|계획 단계에서 정의한 사용 현황, 상태, KIS 및 품질에 대해 보고합니다.||[작업 가이드](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>다음 단계

이 검사 목록을 완료하면 Teams 배포를 통해 직접 라우팅을 성공적으로 구성하게 됩니다.

다음 단계로, 각 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사이트에 사용자를 온보드하고 중요한 사이트별 활동을 계획하고 실행하는 데 도움이 되도록 사이트 사용 플레이북(플레이북)을 사용하세요.
