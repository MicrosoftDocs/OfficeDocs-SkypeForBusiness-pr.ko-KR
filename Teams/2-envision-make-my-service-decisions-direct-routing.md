---
title: 전화 시스템 다이렉트 라우팅 서비스 결정-Microsoft 팀
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 직접 라우팅, 라이선스 및 의사 결정에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa92fcf7c30ecd8dfcecb84c3463f70ba13ee7ef
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240810"
---
# <a name="make-my-service-decisions"></a>내 서비스 결정 하기

전화 시스템 다이렉트 라우팅의 기술 구현 ("직접 라우팅")을 계획 하려면 사용자가 정의한 비즈니스 요구 사항에 맞는 솔루션을 구현할 수 있도록 조직 준비를 더 잘 하는 일련의 서비스 의사 결정을 미리 만들어야 합니다.

## <a name="calling-in-teams"></a>팀에서 통화

Microsoft 팀을 통해 사용자는 PSTN (공개 교환 전화 네트워크)에 전화를 걸거나 받을 수 있습니다. 사용자는 팀 클라이언트 응용 프로그램에서 국내 및 국제 전화 통화 (보이스 메일 포함)를 설정 하 고 수신 하는 데 고유한 전용 전화 번호를 사용할 수 있습니다.

## <a name="direct-routing"></a>직접 라우팅

팀 사용자가 PSTN 통화를 배치 하 고 수신할 수 있으려면 Office 365의 기능인 전화 시스템을 사용 해야 합니다.

PSTN에 대 한 연결을 가능 하 게 하려면 직접 라우팅을 사용 하 여 조직의 사용자에 게 PSTN을 통해 조직 외부에서 전화를 걸고 받을 수 있는 능력을 제공 합니다.

직접적인 라우팅에서는 타사 공급자가 PSTN 연결을 촉진 하 여 PSTN 서비스 공급자가 제공 하는 기존 PSTN trunks를 계속 사용할 수 있습니다. 이는 전화 시스템에 통화 요금제 ("통화 요금제")를 사용할 수 없거나 기존 PSTN 서비스 공급자 계약을 유지 관리 해야 하거나 특정 온-프레미스 시스템과 상호 운용 되는 배포 환경에서 배포할 수 있습니다. 필수.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>직접 라우팅의 가용성

직접 라우팅은 Office 365를 사용할 수 있는 모든 국가에서 사용할 수 있습니다. 이러한 국가 목록은 [국제 가용성](https://products.office.com/business/international-availability) 을 참조 하세요.

조직에서 전화 시스템 기능을 구할 수 있는지 확인 한 후에는 사용 가능한 국가 및 지역 목록에 따라 전화 시스템을 구현할 사용자 위치 또는 사무실 목록을 컴파일해야 합니다. 또한 사용 중인 각 위치에 대 한 플랜 또는 직접 라우팅에 대 한 통화를 수행할 사용자를 식별 합니다.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>전화 시스템을 구현할 사용자 위치 또는 사무실을 식별 합니다.<li>사용할 각 위치에 대 한 요금제 또는 직접 라우팅을 사용 하도록 설정할 사용자를 식별 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>전화 시스템에 사용할 사용자 위치 또는 사무실을 문서화 합니다.<li>사용할 각 위치에 대 한 요금제 또는 직접 라우팅을 사용 하도록 설정할 사용자 목록을 문서화 합니다.</ul>|

> [!TIP]
> 다음은 다이렉트 라우팅 사이트 활용 목록의 예입니다.
> 
> | **지사**                     | **위치**   | **전화 시스템 서비스** |
> |--------------------------------|----------------|--------------------------|
> | 하나의 Epping도로                | 오스트레일리아      | 레거시 PSTN 서비스 |
> | 100 Cyberport도로             | 홍콩 특별 행정구  | 전화 시스템 직접 라우팅 |
> | One Marina Royal           | 싱가포르      | 전화 시스템 직접 라우팅 |
> | 32 런던 다리의 거리        | 영국 | 통화 요금제가 포함 되어 있는 전화 시스템 |
> | 39 Roosevelt Président du | 프랑스         | 통화 요금제가 포함 되어 있는 전화 시스템 |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>전화 번호 및 비상 위치

전화 시스템에는 조직의 모든 사용자가 고유한 직접 안쪽 전화 걸기 (a) 전화 번호를 사용 해야 합니다. 다이렉트 라우팅과 함께 PSTN 서비스 공급자가 전화 번호와 응급 서비스를 제공 합니다.

> [!NOTE]
> 직접 라우팅의 경우 사용자는 PSTN 서비스 공급자가 제공 하는 자신의 전화 번호를 계속 사용할 수 있습니다.
> 
> [!TIP]
> 다음 서식 파일을 사용 하 여 전화 번호에 대 한 정보를 문서화할 수 있습니다.
> 
> |클릭할 |전화 번호 |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |세인트루이스의 Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>보이스 메일

Azure 보이스 메일 서비스를 통해 제공 되는 클라우드 보이스 메일은 Exchange 사서함에 대 한 보이스 메일 저축과 지원 하며 타사 전자 메일 시스템을 지원 하지 않습니다.

클라우드 보이스 메일에는 조직의 모든 사용자가 기본적으로 사용 하도록 설정 된 음성 메일의 내용이 포함 됩니다. 비즈니스 요구에 따라 특정 사용자 또는 조직 전체에 대 한 보이스 메일을 사용 하지 않도록 설정 해야 할 수 있습니다. 조직에서 음성 메일 기록을 사용 하기로 결정 한 경우에는 보이스 메일 보관 함 표시를 사용 해야 하는지 여부도 고려해 야 합니다. 자세한 내용은 [조직의 보이스 메일 정책 설정을](set-up-phone-system-voicemail.md) 참조 하세요.

전화 시스템 구현에서 보이스 메일에 대 한 자세한 내용은 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>다이렉트 라우팅 구현에서 클라우드 보이스 메일을 사용할지 여부를 결정 합니다.<li>조직 전체 또는 특정 사용자에 대 한 보이스 메일 기록 및 음성 메일 기록 사용 금지 마스크를 사용할지 여부를 결정 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>해당 하는 경우 클라우드 보이스 메일을 지원 하기 위한 결정 지점을 문서화 합니다.<li>음성 메일, 음성 메일, 음성 메일을 사용 하거나 사용 하지 않도록 설정 하는 경우 특정 사용자에 대해서만 해당 사용자 목록을 문서화할 수 있습니다.</ul>|

> [!TIP]
> 호출 계획 구현에 대 한 구름 보이스 메일 정보는 다음 표에 나와 있는 것 처럼 문서화 될 수 있습니다.
> 
> | **클릭할**         | **Exchange 사서함** | **보이스 메일을 가능 하 게 하 시겠습니까?** | **보이스 메일** | **보이스 메일 기록 불경 마스크** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | 온라인               | '                   | 수                     | 수                                       |
> | Lidia Holloway   | 온라인               | '                   | 수                     | 비활성화                                      |
> | 세인트루이스의 Lahr       | 온-프레미스          | '                   | 수                     | 수                                       |
> | Marcel Beauchamp | 온-프레미스          | '                   | 비활성화                    | 해당 없음                                           |
> | Rachelle Cormier | 온라인               | '                   | 비활성화                    | 해당 없음                                           |
> | Isabell Potvin   | 온-프레미스          | '                   | 비활성화                    | 해당 없음                                           |
> 
> [!NOTE]
> 팀과 보이스 메일을 사용 하려면 사용자에 게 Exchange 사서함이 있어야 합니다. 자세한 내용은 [Exchange 및 Microsoft 팀의 상호 작용](exchange-teams-interact.md) 을 참조 하세요.

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>직접 라우팅 라이선스

조직에서 직접 라우팅을 사용 하려는 경우 필요한 라이선스를 얻어야 합니다. 직접 라우팅 사용자에 게는 Office 365에 할당 된 다음 라이선스가 있어야 합니다.

-   Microsoft 전화 시스템

-   Microsoft 팀

-   오디오 회의

오디오 회의 라이선스는 외부 참가자에 게 전화를 거 나 전화 접속 번호를 제공 하는 방법으로 예약 된 모임을 추가 하는 데 필요 합니다. 외부 참가자에 게 전화를 거는 경우 오디오 회의 서비스에서 온라인 통화 기능을 사용 하 여 통화를 할 수 있습니다. 오디오 회의 라이선스는 선택 사항이 며 오디오 회의를 포함 하는 팀 회의를 구성 하는 사용자 에게만 필요 합니다.


> [!NOTE]
> 무료 회의 브리지 전화 번호를 제공 하 고 국제 전화 번호로 회의 전화 걸기를 지원 하려면 조직의 [통신 크레딧을](what-are-communications-credits.md) 설정 해야 합니다.

오디오 회의 및 전화 시스템은 Office 365 E3 또는 E1 구독 계획을 보유 하 고 있는 기존 고객을 위한 추가 기능 서비스와 별도로 라이선스가 부여 될 수 있습니다. 이미 Office 365 E5 구독 계획의 일부로 포함 되어 있습니다.

> [!TIP]
> 타사 Pbx로 전화를 라우팅할 때 통화 계획을 사용할 수 있는 사용자에 게 직접 라우팅을 사용할 수도 있습니다. 자세한 내용은 [라이선스 및 직접 라우팅의 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements)참조 하세요.


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>조직에 필요한 전화 시스템 라이선스가 없는 경우 기존 Office 365 구독을 단계별로 진행 하거나 전화 시스템 추가 기능 서비스를 획득 하 여 전화 시스템 라이선스를 확보할 것인지 여부를 결정 합니다.<li>다이렉트 라우팅 구현에 통신 크레딧이 필요한 지 여부를 결정 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>전화 시스템 라이선스를 할당할 디비전, 부서, 사무실 또는 사용자 그룹을 문서화 합니다.<li>무료 번호를 사용 하는 오디오 회의가 범위 내에 있는 경우 통신 크레딧을 사용할 수 있는 부서, 부서, 사무실 또는 사용자 그룹을 문서화 합니다.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Office 365 고려 사항

직접 라우팅을 사용할 수 있는 모든 사용자는 Office 365에 있어야 합니다. 온-프레미스 비즈니스용 Skype Server 또는 Lync Server를 사용 하는 하이브리드 배포의 경우 팀과의 다이렉트 라우팅을 사용 하도록 구성 하기 전에 비즈니스용 Skype Online으로 사용자를 이동 해야 합니다.

직접 라우팅 구현 범위에 있는 모든 사용자를 팀에서 사용할 수 있어야 합니다.

Onmicrosoft.com 도메인은 \*직접 라우팅과 함께 사용할 수 없으므로 하나 이상의 도메인에서 Office 365 테 넌 트를 사용 하도록 설정 해야 합니다. 도메인 및 Office 365 테 넌 트에 대 한 자세한 내용은 [도메인 FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)를 참조 하세요.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>직접 라우팅을 지원 하려면 비즈니스용 Skype Online으로 마이그레이션해야 할 사용자가 있는지 여부를 결정 합니다.<li>팀에 대해 사용 하도록 설정 해야 하는 사용자를 식별 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>비즈니스용 Skype Online으로 이동 하 고 팀에 대해 사용 하도록 설정 해야 하는 사용자 목록을 문서화 합니다.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC 고려 사항

사용자에 게 PSTN 연결을 제공 하기 위해 직접 라우팅 서비스와 쌍을 두어야 하는 인증 된 또는 지원 되는 세션 경계 컨트롤러 (SBCs)를 사용 해야 합니다. 인증 된 SBCs 목록은 [지원 되는 세션 경계 컨트롤러](direct-routing-plan.md#supported-session-border-controllers-sbcs)를 참조 하세요.

환경, 위치 수, 음성 라우팅 요구 사항에 따라 사용자 기반을 지원 하기 위해 여러 개의 SBCs를 배포 해야 할 수 있습니다.

### <a name="sbc-domain-names"></a>SBC 도메인 이름

직접 라우팅과 쌍을 두는 각 SBC에는 고유한 DNS 이름이 있어야 합니다. SBC DNS 이름은 Office 365 테 넌 트에 등록 된 도메인 이름 중 하나 여야 합니다. 테 넌 트에서 여러 도메인 이름을 할당 한 경우에는 SBCs의 DNS 이름을 계획할 때 이러한 도메인 이름을 사용할 수 있습니다.

> [!IMPORTANT]
> SBC DNS 이름에는 *. onmicrosoft.com을 사용 하는 것이 허용 되지 않습니다.

### <a name="certificates"></a>인증

직접 라우팅으로 배포 된 각 SBC에는 지원 되는 인증 기관 목록에서 받은 인증서가 필요 합니다. 인증서는 주체, 주체 대체 이름 또는 일반 이름 필드에 SBC DNS 이름을 포함 해야 합니다.

> [!NOTE]
> SBCs와 함께 와일드 카드 인증서를 사용 하는 방법도 지원 됩니다.

지원 되는 인증 기관 목록 및 자세한 내용은 [SBC에 대 한 신뢰할 수 있는 공개 인증서](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)를 참조 하세요.


### <a name="sbc-ip-addresses-and-ports"></a>SBC IP 주소 및 포트

각 SBC는 Office 365 데이터 센터에서 액세스할 수 있는 공용 IP 주소를 사용 하 여 구성 해야 합니다. NAT (network address translation)를 구성 하 여 Office 365 데이터 센터에 SBCs를 게시할 수도 있습니다.

SBCs는 신호 및 미디어에 대 한 클라우드 서비스와 통신 하기 위해 양방향 연결을 요구 합니다. 신호는 *SIP 프록시*라는 구성 요소에 의해 처리 되며 미디어 *프로세서*에서 처리 됩니다.

각 SBC에서 SIP 신호 및 미디어에 대 한 특정 포트 번호를 정의 하 고 이러한 포트와 연결 된 IP 주소에 대 한 양방향 트래픽을 허용 하도록 방화벽을 구성 해야 합니다.

자세한 내용은 [SIP 신호: fqdn 및 방화벽 포트](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) 및 [미디어 트래픽: 포트 범위](direct-routing-plan.md#media-traffic-port-ranges)를 참조 하세요.


> [!NOTE]
> SBC 모델을 기반으로 각 SBC에 대해 최대 동시 세션 제한을 설정할 것을 적극 권장 합니다. 그러면 해당 용량에 따라 SBC이 실행 되는 동안에도 알림이 트리거됩니다.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>SBCs를 배포할 위치를 결정 합니다.<li>배포 하려고 하는 각 SBC에 대 한 DNS 이름을 결정 하세요.<li>SBC 도메인 이름 결정에 따라 배포에 있는 모든 SBCs를 지원 하기 위해 와일드 카드 인증서를 사용할지 SBC 당 전용 인증서를 사용할지 여부를 결정 합니다.<li>사용자의 SBCs에 대 한 인증서를 얻을 공용 인증 기관을 결정 합니다.<li>배포할 각 SBC에 대해 공용 IP 주소/포트 쌍을 정의 하 고 공용 IP 주소를 SBCs에 할당 하거나 NAT를 사용할지 여부를 결정 합니다.<li>각 SBC가 지원 하거나 처리할 수 있는 최대 동시 세션 수를 확인 합니다.<li>미디어 바이패스를 사용 하 여 구성할 SBCs를 결정 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>다음 예제 표를 사용 하 여 SBCs에 대 한 각 결정을 문서로 작성 합니다.</ul>|


> [!TIP]
> 직접 라우팅 배포에 대 한 SBC 세부 정보를 문서화 하려면 다음 서식 파일을 사용 합니다.
> 
> | **SBC DNS 이름 (FQDN)** | **SBC 만들기 및 모델** | **인증** | **위치**  | **IP 주소** | **SIP 신호 포트** | **A?** | **최대 동시 세션** | **미디어 바이패스 사용 가능 여부** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*contoso.com | 암스테르담 | TBD | TBD | ' | TBD | 아니요 |
> | SBC-Asia.contoso.com | TBD | \*contoso.com | 홍콩 특별 행정구 | TBD | TBD | 아니요 | TBD | ' |
> | SBC-Africa.contoso.com | TBD | \*contoso.com | 요하네스버그 | TBD | TBD | ' | TBD | ' |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>음성 라우팅

직접 라우팅에 대 한 통화를 특정 SBCs로 라우팅하려면 Microsoft 전화 시스템을 구성 해야 합니다. 다음을 기준으로 음성 경로를 구성할 수 있습니다.

-   번호 패턴 이라고 합니다.

-   번호 패턴 + 통화를 하는 사용자입니다.


통화 라우팅은 다음 요소로 구성 됩니다.

-   음성 라우팅 정책 – PSTN 사용을 위한 컨테이너 사용자 또는 여러 사용자에 게 할당할 수 있습니다.

-   PSTN 사용 – 음성 경로 및 PSTN 사용량을 위한 컨테이너 다른 음성 라우팅 정책에서 공유 가능

-   음성 경로 – 전화 번호 패턴과 패턴과 일치 하는 통화에 사용할 온라인 PSTN 게이트웨이 집합

-   SBC의 온라인 PSTN 게이트웨이 포인터에는 호출이 호출 될 때 적용 되는 구성 (예: 정방향 P-어설션된-Id (PAI) 또는 기본 설정 코덱)이 저장 됩니다. 음성 경로에 추가할 수 있습니다.

전화 요금제와 함께 직접 라우팅이 가능 하도록 음성 경로를 구성할 수 있습니다. 이 구성을 통해 착신 지를 사용 하 여 전화 요금제가 특정 SBCs에 대 한 일부 통화를 라우팅할 수 있습니다.

> [!TIP]
> SBCs는 *활성* 및 *백업*으로 지정 될 수 있습니다. 즉,이 번호 패턴에 대해 활성화로 구성 된 SBC 또는 숫자 패턴 + 특정 사용자를 사용할 수 없는 경우에는 통화가 백업 SBC로 라우팅됩니다.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>직접 라우팅 구현 범위에서 사용자 위치 또는 사무실을 지원 하기 위해 만들 음성 라우팅 정책, PSTN 용도, 음성 경로를 결정 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>조직의 음성 라우팅 정책, PSTN 용도, 음성 경로를 문서화 합니다.<li>정의한 각 음성 라우팅 정책에 할당할 사용자를 문서화 합니다.</ul>|

> [!TIP]
> 다음 서식 파일을 사용 하 여 다이렉트 라우팅 배포에 대 한 음성 정책을 문서화 합니다.
> 
> | **PSTN 사용** | **음성 경로** | **번호 패턴** | **중요도** | **하더라도** | **설명** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | 미국만 | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | raid-1 | sbc1.contoso.com sbc2.contoso.com | 호출 되는 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로 |
> | 미국만 | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | 호출 되는 번호에 대 한 백업 경로 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX |
> | 미국만 | "기타 + 1" | \^\\+ 1 (\\d{10})\$ | 3-4 | sbc5.contoso.com sbc6.contoso.com | 호출 되는 번호에 대 한 경로 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외) |
> | 국제화 | 국제화 | \\d + | 4(tcp/ipv4) | sbc2.contoso.com sbc5.contoso.com | 임의의 숫자 패턴에 대 한 라우팅 |
> 
> [!IMPORTANT]
> 음성 라우팅 정책의 PSTN 사용은 순서 대로 적용 되며, 첫 번째 사용에서 일치 하는 항목을 찾은 경우 다른 용도는 평가 되지 않습니다.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>통화 및 Interop 정책

직접 라우팅은 Microsoft 팀 에서만 지원 됩니다. 직접 라우팅을 통해 PSTN 전화를 걸거나 받으려면 팀에서 수신 전화를 받을 수 있도록 필요한 정책을 구성 해야 합니다.

> [!NOTE]
> 직접 라우팅이 가능 하도록 설정 된 사용자는 비즈니스용 Skype를 사용 하 여 다이렉트 라우팅 전화를 걸거나 받을 수 없으므로 팀 클라이언트에 배포 해야 합니다.

다음 두 가지 방법 중 하나를 호출 하 여 팀을 기본 클라이언트로 설정 하도록 사용자를 구성할 수 있습니다.

-   팀 전용 모드로 사용자 구성

-   TeamsCallingPolicy 및 TeamsInteropPolicy를 할당 하 여 팀을 기본 호출 클라이언트로 구성 합니다.

자세한 내용은 [Microsoft 팀을 사용자를 위한 기본 호출 클라이언트로 설정을](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)참조 하세요.


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>통화에 대 한 기본 클라이언트로 팀을 설정 하는 데 사용할 방법을 결정 합니다.</ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>Interop 및 호출 정책을 사용 하 여 구성할 사용자를 문서화 합니다.</ul>|

> [!IMPORTANT]
> 사용자가 팀 전용 모드로 구성 된 경우이 사용자는 더 이상 비즈니스용 Skype에 로그인 할 수 없습니다.

팀 클라이언트에서 사용자에 게 통화 탭이 표시 되도록 하려면 테 넌 트에 대 한 조직 수준에서 비공개 호출을 사용 하도록 설정 해야 합니다. 개인 통화를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에 대 한 통화 사용](direct-routing-configure.md) 을 참조 하세요.


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>문서 서비스 결정

이 문서의 이전 섹션에 나와 있는 정보를 사용 하 여 서비스 의사 결정을 문서화할 수 있습니다. 일반적으로이 설명서에는 다음과 같은 주요 섹션이 포함 됩니다.

-   통화 요금제 사이트 사용 목록을 포함 하는 전화 시스템

-   보이스 메일 구성 세부 정보

-   전화 시스템 다이렉트 라우팅 사용자에 대 한 라이선스 할당

-   SBC 구성 세부 정보

-   음성 라우팅 정책 및 라우팅 세부 정보

-   Interop 및 호출 정책 세부 정보

<!--ENDOFSECTION-->
