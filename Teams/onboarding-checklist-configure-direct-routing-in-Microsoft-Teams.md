---
title: Microsoft 팀에서 직접 라우팅을 구성 하기 위한 온 보 딩 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 팀에서 직접 라우팅을 구성할 때이 검사 목록의 핵심, 할 일 작업 및 활동을 따릅니다.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61d23d2aa9aeef58a581233c07ed950b494531b6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573354"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>Microsoft 팀에서 직접 라우팅 구성

## <a name="direct-routing"></a>직접 라우팅

| 아니요 | 활동 또는 작업 | 설명 | 완료? | 추가 정보 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|raid-1|조직의 위치에 어떤 PSTN 연결을 배포할지 결정|Microsoft는 Office 365 전화 시스템을 사용 하 여 사용자에 게 PSTN 연결을 제공 하는 대체 방법을 제공 합니다.<ul><li>통화 요금제가 있는 전화 시스템 ("통화 요금제"): 비즈니스용 Skype Online 및 팀<li>전화 시스템 직접 라우팅 ("직접 라우팅"): 팀 전용<li>온-프레미스 PSTN 연결을 사용 하는 전화 시스템: 비즈니스용 Skype Online만<li>비즈니스용 skype 클라우드 커넥터 에디션: 비즈니스용 Skype Online만</ul>직접적인 라우팅에서는 Microsoft가 아닌 타사 공급자가 PSTN 연결을 촉진 한다는 점을 제외 하 고는 호출 계획과 동일한 이점을 제공 합니다. 이는 전화 요금제를 사용할 수 없는 국가에서 배포 하거나 기존 PSTN 서비스 공급자 계약을 유지 관리 해야 하거나 특정 온-프레미스 시스템과의 상호 운용성이 필요한 배포에 사용할 수 있습니다.<br><br>조직에 가장 적합 한 옵션을 결정 합니다. | |[오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능 여부](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[오디오 회의 및 통화 플랜에 대 한 온 보 딩 검사 목록](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|직접 라우팅 사용을 위한 사용자 목록 및 배포 흐름 확인|팀과 직접 라우팅하기 위한 범위 내에 사업부 또는 사이트 목록이 있는지 확인 합니다. 목표 및 키 결과 모델을 사용 하 여 직접 라우팅 범위에 있는 사용자를 확인 합니다. 사이트 별로 작업 하 여 리소스에 집중할 수 있도록 하는 것이 좋습니다.<br><br>사용 계획의 일환으로, 언제 (파일럿, 사이트 1, 사이트 2 등)에 따라 어떤 사용자를 사용할 것인지를 결정 합니다.||[다이렉트 라우팅 구상](2-envision-make-my-service-decisions-direct-routing.md)|
|3-4|라이선스 계획 및 가져오기|직접 라우팅 사용자에 게는 Office 365에 할당 된 다음 라이선스가 있어야 합니다.<ul><li>비즈니스용 Skype Online (요금제 2)<li>Microsoft 전화 시스템<li>Microsoft 팀<li>Microsoft 오디오 회의</ul>또한 직접 라우팅은 통화 요금제에 대 한 사용이 허가 된 사용자를 지원 합니다. 통화 요금제가 포함 된 전화 시스템은 직접 라우팅 인터페이스를 사용 하 여 일부 통화를 라우팅할 수 있습니다.<br><br>오디오 회의 라이선스는 외부 참가자에 게 전화를 거 나 전화 접속 번호를 제공 하 여 예약 된 모임에 외부 참석자를 추가 하는 데 필요 합니다.||[직접 라우팅 라이선스](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4(tcp/ipv4)|SBC (세션 경계 컨트롤러) 도메인 이름 계획|SBC 도메인 이름은 테 넌 트의 "Domains"에 등록 된 이름 중 하나 여야 합니다.<br><br>**참고:** SBC의 FQDN (정규화 된 도메인 이름)에는 onmicrosoft.com를 사용할 수 없습니다.<br><br>SBC 도메인 이름은 각 SBC에 필요한 인증서를 계획 하는 데에도 중요 합니다.||[SBC 도메인 이름](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5mb|인증서 계획|CSR (인증 서명 요청)을 생성 하 여 SBC에 대 한 인증서를 요청 하는 것이 좋습니다.<br><br>인증서의 제목, 일반 이름 또는 주체 대체 이름 필드에 SBC FQDN이 있어야 합니다. 또는 직접적인 라우팅이 일반 이름 또는 주체 대체 이름에 와일드 카드를 지원 합니다.<br><br>SBC에 대 한 CSR을 생성 하는 방법에 대 한 자세한 내용은 SBC 공급 업체에서 제공 하는 문서를 참조 하세요.<br><br>**추가 정보** 열의 문서에 지원 되는 루트 인증 기관이 나열 됩니다.||[SBC에 대해 신뢰할 수 있는 공용 인증서](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|26|방화벽 포트 계획 및 구성|직접 라우팅의 연결 지점은 다음 세 가지 Fqdn입니다.<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>이러한 연결 지점과 SBCs 사이의 트래픽은 회사 방화벽에서 허용 되어야 합니다. SBC를 구성할 때 SBC에서 TCP 포트를 정의 합니다.<br><br>미디어 트래픽이 UDP 상에 있습니다. 이러한 유형의 트래픽은 미디어 프로세서 구성 요소에 전달 됩니다. SBCs와 미디어 프로세서 간의 양방향 트래픽은 방화벽 에서도 허용 되어야 합니다.<br><br>**참고:** 미디어 프로세서는 동적 IP 주소를 가지 며, 나중에 고정 IP 주소를 사용할 수 있게 됩니다. [Azure DATACENTER Ip 범위](https://www.microsoft.com/download/details.aspx?id=41653)에 나열 된 모든 IP 주소를 허용 하는 것이 중요 합니다.||[SIP 신호: Fqdn 및 방화벽 포트](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[미디어 트래픽: IP 주소 및 포트 범위](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 데이터 센터 IP 범위](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|SBCs 구성|Microsoft는 직접 라우팅과 쌍을 연결 하는 인증 된 SBCs만 지원 합니다.<br><br>공급 업체별 지침과 **추가 정보** 열에 있는 문서의 지침을 사용 하 여 SBCs를 구성 합니다.||[지원 되는 SBCs (세션 경계 컨트롤러)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|20cm(8|직접 라우팅이 있는 SBCs 쌍|각 사이트의 SBCs는 고유한 trunks를 사용 하 여 발신음 및 PSTN 통화 기능을 제공 하는 직접적인 라우팅과 쌍을 이루어야 합니다.<br><br>특정 사이트의 SBC이 이미 직접 라우팅과 연결 되어 있는지 확인 하거나 이전에 수행 하지 않은 경우에는 쌍을 구성 합니다.<br><br>Microsoft는 직접 라우팅과 관련 하 여 인증 된 SBC의 유일한 기능을 지원 합니다. 해당 사이트의 SBC가 인증 되었는지 확인 합니다.||[SBC를 쌍으로 연결 하 여 전화 시스템의 다이렉트 라우팅 서비스](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|되었는지|SBC 페어링 유효성 검사|특정 사이트 `Get-CsOnlinePSTNGateway` 에 대해 쌍을 이룬 각 SBC에 대해 cmdlet을 실행 하 고 **사용 하도록 설정** 된 매개 변수에 **True**값이 표시 되는지 확인 합니다.<br><br>Sbc 관리 인터페이스를 사용 하 여 SBC가 보내는 SIP 옵션에 대 한 **200 "OK"** 응답을 수신 하는지 확인 합니다.|||
|1천만|사용자 구성 유효성 검사|사용자 계정이 Office 365에서 직접 만들어졌는지 또는 디렉터리 동기화를 사용 하 여 Office 365와 동기화 되었는지 확인 합니다.<br><br>필요한 라이선스가 사용자에 게 할당 되었는지 확인 합니다.<br><br>직접 라우팅이 포함 된 PSTN 연결의 경우 사용자를 비즈니스용 Skype Online으로 설정 하 고 Microsoft 팀에 사용 해야 합니다.||[사용자가 직접 라우팅 서비스를 사용 하도록 설정](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|mb|사용자의 전화 번호 구성|직접 라우팅 범위에 있는 모든 사용자에 게는 전화 번호와 보이스 메일을 할당 해야 합니다.<br><br> Cmdlet `Set-CsUser` 을 사용 하 여 음성 메일을 사용 하도록 설정 하 고 사용자에 게 전화 번호를 할당 합니다.||[전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|까지|음성 라우팅 구성|전화 시스템에는 다음 기준에 따라 특정 SBC로 전화를 보낼 수 있는 라우팅 메커니즘이 있습니다.<ul><li>전화 번호 패턴<li>전화 번호 패턴 호출을 하는 특정 사용자</ul>다음을 만들어 사용자에 대 한 음성 라우팅을 구성 합니다.<ul><li>음성 라우팅 정책<li>PSTN 용도<li>음성 경로<li>온라인 PSTN 게이트웨이</ul>||[음성 라우팅 구성](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|일자|Microsoft 팀을 사용자를 위한 기본 호출 클라이언트로 설정|사용자가 Microsoft 팀에서 **통화** 탭을 볼 수 있으려면 먼저 microsoft 팀에서 테 넌 트에 대해 **전용 통화** 를 사용 하도록 설정 해야 하며 팀 클라이언트는 사용자의 **기본 호출 클라이언트로** 구성 되어야 합니다.||[Microsoft 팀을 위한 통화 사용](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[Microsoft 팀을 사용자를 위한 기본 호출 클라이언트로 설정](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|13|사용자가 직접 라우팅 하도록 설정|구성 된 SBC를 통한 직접 라우팅을 사용 하 여 PSTN 전화를 걸고 받을 사용자에 게 음성 라우팅 정책을 할당 합니다.||[사용자가 직접 라우팅 서비스를 사용 하도록 설정](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|~|사용자 수용 테스트 준비 및 실행|전화 접속 및 전화 접속 시나리오를 포함 하 여 사용자 수용 테스트를 준비 하 고 실행 합니다.||[팀에서 클라우드 음성 작업 부하 테스트](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|보고서 사용 현황, 상태, 주요 성공 표시기 (KSIs) 및 품질|구상 단계에서 정의한 사용 현황, 상태, KSIs 및 품질에 대해 보고 합니다.||[운영 가이드](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>다음 단계

이 검사 목록을 완료 하면 팀 배포에 대 한 직접 라우팅이 성공적으로 구성 됩니다.

다음 단계로, [Playbook (Playbook) 사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용을 위해 각 사이트의 사용자를 등록 하 고 중요 한 사이트별 작업을 계획 하 고 실행 하도록 도와 보세요.
