---
title: 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 관리자는 직접 라우팅에 대해 인증된 SBC(세션 테두리 컨트롤러)에 대해 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33df0f9d00d0c02d28c5f69ef26ae151586803d2
ms.sourcegitcommit: 9b794b579e57d478e5e4bd76b8ca79fdea6f90c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2021
ms.locfileid: "53465386"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>직접 라우팅으로 인증된 SBC(Session Border Controller) 목록

Microsoft는 선택한 SBC(세션 테두리 컨트롤러) 공급업체와 파트너를 하여 SBC가 직접 라우팅과 함께 작동하고 있는지 인증합니다.

Microsoft는 각 공급업체와 함께 작업합니다.

- SIP 상호 연결 프로토콜을 공동으로 작업합니다.
- 타사 랩을 사용하여 격렬한 테스트를 수행합니다. 테스트를 통과하는 디바이스만 인증됩니다.
- 프로덕션 및 사전 프로덕션 환경에서 모든 인증된 디바이스를 통해 매일 테스트를 실행합니다. 프로덕션 전 환경에서 디바이스를 유효성 검사하면 클라우드의 새 버전의 직접 라우팅 코드가 인증된 SBC와 함께 작동할 수 있습니다.
- SBC 공급업체와 공동 지원 프로세스를 수립합니다.

  > [!NOTE]
  > Microsoft는 인증된 전화 시스템 디바이스가 직접 라우팅을 통해 연결된 경우만 지원됩니다. Microsoft는 인증되지 않은 디바이스가 직접 라우팅을 통해 전화 시스템 지원 사례를 거부할 수 있는 권리가 있습니다. Microsoft에서 고객의 직접 라우팅 문제가 공급업체의 SBC 디바이스와 관련이 있는 것으로 판단되는 경우 고객은 지원을 위해 SBC 공급업체에 문의해야 합니다.

직접 라우팅에 대해 인증된 디바이스 목록 다음 테이블입니다. (로컬 미디어 최적화를 지원하는 SBC 공급업체에 대한 자세한 내용은 직접 라우팅을 위한 로컬 미디어 최적화 [구성을 참조하세요.](direct-routing-media-optimization-configure.md)

[직접 라우팅에 대해 자세히 알아보자.](https://aka.ms/dr)
직접 라우팅에 대한 SBC 인증 프로그램에 대한 질문이 있는 경우 해당 drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>인증된 SBC 공급업체

|                                                       공급업체                                                        |       제품       | 미디어가 아닌 우회 | 미디어 바이패스 | 소프트웨어 버전 | 911 서비스 공급자 지원* | ELIN 가능 |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  지원되는 7.20A.250(권장 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  지원되는 7.20A.250(권장 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  지원되는 7.20A.250(권장 7.20A.258)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  지원되는 7.20A.250(권장 7.20A.258)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   보류 중     |  지원되는 7.20A.250(권장 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  지원되는 7.20A.250(권장 7.20A.258)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  지원되는 7.20A.250(권장 7.20A.258) |  &#10004;    |  &#10004;  |
|  [리본 통신](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       지원되는 8.2 및 7.2(권장 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       지원되는 8.2 및 7.2(권장 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       지원되는 8.2 및 7.2(권장 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       지원되는 8.2 및 7.2(권장 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       지원되는 8.2 및 7.2(권장 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 또는 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 또는 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 또는 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc 시리즈 |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    365 SBC 생각    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      지원되는 3.20(권장 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7(미디어 우회의 경우 4.9)      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     1000 시리즈 통합 서비스 라우터용 Cisco CUBE(통합 테두리 요소)        |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.3.2)         |    &#10004;     |   |  
|                                   |     4000 시리즈 통합 서비스 라우터에 대한 Cisco 통합 테두리 요소(CUBE)        |     &#10004;   | &#10004; |   지원되는 IOS XE 암스테르담 17.2.1r(권장 17.3.2)         |   &#10004;      |    |  
|                                   |     1000V 시리즈 클라우드 서비스 라우터용 Cisco 통합 테두리 요소(CUBE)       |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.3.2)         |    &#10004;     |    |  
|                                 |     1000 시리즈 집계 서비스 라우터에 대한 Cisco CUBE(통합 테두리 요소)      |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.3.2)         |    &#10004;     |    |
|                                 |     Catalyst 8000 Edge 플랫폼용 Cisco CUBE(통합 테두리 요소)      |     &#10004;   | &#10004; |      IOS XE 암스테르담 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller for Enterprise(ASBCE)    |     &#10004;     |       &#10004;     |       릴리스 8.1.1(미디어 우회용 8.1.2)      |     |    |
|                     [노키아](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 세션 테두리 컨트롤러    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia 세션 테두리 컨트롤러    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       지원되는 5.0(권장 5.1)     |     |    |
|                     [에릭슨](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [카탈리야](https://cataleya.com/orchidplatforms/)|    난초 링크    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape 세션 테두리 컨트롤러   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies(이전의 Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel 시리즈   |     &#10004;     |         |      DGW 48.0.2340(권장 DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops 세션 테두리 컨트롤러(ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller(ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    하이퍼컨버지드 음성   |     &#10004;     |         |      HCVoice 1.0.6       |     |    |

<br/>

* 911개 서비스 공급자

- [대역폭 동적 위치 라우팅](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [ERS(Intrado 긴급 라우팅 서비스)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [인트라도 응급 게이트웨이(EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>직접 라우팅 및 아날로그 디바이스 상호 연동성

다음 표에는 직접 라우팅과 아날로그 디바이스 간의 상호 연동성이 확인된 디바이스가 나열됩니다.

|                                                       공급업체                                                        |       제품       | 확인
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 Multiplatform 아날로그 전화 어댑터 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 소프트웨어 버전 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 소프트웨어 버전 8.3.0.1.2 |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. 소프트웨어 버전: 8.1.1(빌드 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. 소프트웨어 버전: 8.1.1(빌드 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  Grandstream GXW42xx를 사용할 수 있는 anynode(V1.0.7.10) |     &#10004;     |
  
새 기능에 대한 아이디어와 같은 Teams 제품 피드백을 제공하면 [Uservoice 을 참조합니다.](https://microsoftteams.uservoice.com)


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

주 버전에 부여된 인증에 유의합니다. 즉, 주 버전 다음의 SBC 펌웨어에 숫자가 있는 펌웨어가 지원됩니다.
