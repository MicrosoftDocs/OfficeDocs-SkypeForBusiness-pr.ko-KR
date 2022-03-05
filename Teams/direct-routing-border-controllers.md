---
title: 직접 라우팅에 대한 인증된 SBC(Session Border Controller)
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 직접 라우팅에 대해 인증된 SBA(Session Border Controller)에 대해 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c005d97a0d0d570cb362d6c82853e3a3f8e3116
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062502"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>직접 라우팅에 대한 인증된 SBC(Session Border Controller)

Microsoft는 선택한 SBC(Session Border Controller) 공급업체와 협력하여 해당 SBC가 직접 라우팅과 함께 작동함을 인증합니다.

Microsoft는 각 공급업체와 협력하여 다음을 수행합니다.

- SIP 상호 연결 프로토콜에서 공동으로 작업합니다.
- 타사 랩을 사용하여 강도 높은 테스트를 수행합니다. 테스트를 통과한 디바이스만 인증됩니다.
- 프로덕션 및 사전 프로덕션 환경에서 모든 인증된 디바이스를 사용하여 매일 테스트를 실행합니다. 사전 프로덕션 환경에서 디바이스의 유효성을 검사하면 클라우드의 새 버전의 직접 라우팅 코드가 인증된 SBC와 함께 작동합니다.
- SBC 공급업체와 공동 지원 프로세스를 수립합니다.

  > [!NOTE]
  > Microsoft는 인증 디바이스로 사용하는 경우에만 직접 라우팅을 사용하는 전화 시스템을 지원합니다. 문제가 있는 경우 SBC 공급업체의 고객 지원에 먼저 문의해야 합니다. 필요한 경우 SBC 공급업체에서 내부 채널을 통해 Microsoft로 문제를 에스컬레이션합니다. Microsoft에는 인증되지 않은 디바이스에서 직접 라우팅을 통해 전화 시스템에 연결할 경우 지원을 거부할 권리가 있습니다. Microsoft에서 고객의 직접 라우팅 문제가 공급업체의 SBC 장치와 관련된 것으로 판단되면 고객은 SBC 공급업체에 다시 참여를 요청해야 합니다.
  >
  > 인증은 특정 SBC 펌웨어 버전에 부여됩니다. 아래에 설명된 모든 SBC 펌웨어 버전은 인증되고 지원됩니다. 주.부(major.minor) 버전이 동일하면 문서화된 버전보다 높은 펌웨어 버전이 지원됩니다.
  >
  > 예제:
  >
  > - 6.10.258 지원 - 이 경우 Microsoft는 펌웨어 버전 6.10을 지원합니다(258 이상).
  > - 6.20.100 권장 - 이 경우 Microsoft는 펌웨어 버전 6.20을 권장합니다(100 이상).
  > - 특정 버전에 대한 지원 가능 여부 질문은 SBC 공급업체에 문의하세요.

직접 라우팅에 대해 인증된 목록 디바이스를 따르는 테이블입니다. (로컬 미디어 최적화를 지원하는 SBC 공급업체에 대한 자세한 내용은 [직접 라우팅을 위한 로컬 미디어 최적화 구성](direct-routing-media-optimization-configure.md)을 참조하세요.)

[직접 라우팅](https://aka.ms/dr)에 대해 자세히 알아보세요.
직접 라우팅용 SBC 인증 프로그램 관련 질문은 drsbccertification@microsoft.com으로 문의해 주세요. 참고: 추후 공지가 있을 때까지 인증에 대한 새 추천을 수락하지 않습니다.
<br/>

## <a name="certified-sbc-vendors"></a>인증된 SBC 공급업체

|                                                       공급업체                                                        |       제품       | 미디어가 아닌 바이패스 | 미디어 바이패스 | 소프트웨어 버전 | 911 서비스 공급자 지원* | ELIN 지원 |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   중앙값 500 SBC   |     &#10004;     |   &#10004;    |  지원되는 7.20A.258(권장 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   중앙값 800 SBC   |     &#10004;     |   &#10004;     |  지원되는 7.20A.258(권장 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  중앙값 2600 SBC   |     &#10004;     |   &#10004;    |  지원되는 7.20A.258(권장 7.40A.250)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  중앙값 4000 SBC   |     &#10004;     |   &#10004;     |  지원되는 7.20A.258(권장 7.40A.250)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | 중앙값 1000B  SBC  |     &#10004;     |   &#10004;     |  지원되는 7.20A.250(권장 7.40A.250)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | 중앙값 9000  SBC  |     &#10004;     |   &#10004;     |  지원되는 7.20A.258(권장 7.40A.250)   | &#10004;     |  &#10004;  |
|                                                                                                                     | 가상 버전 SBC |     &#10004;     |   &#10004;     |  지원되는 7.20A.258(권장 7.40A.250) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | 중앙값 클라우드 버전 SBC  |     &#10004;     |   &#10004;     |  지원되는 7.20A.258(권장 7.40A.250) |  &#10004;    |  &#10004;  |
|  [리본 통신](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       지원 대상 9.2, 8.2 및 7.2(권장 10.1)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       지원 대상 9.2, 8.2 및 7.2(권장 10.1)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       지원 대상 9.2, 8.2 및 7.2(권장 10.1)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       지원 대상 9.2, 8.2 및 7.2(권장 10.1)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       지원 대상 9.2, 8.2 및 7.2(권장 10.1)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 또는 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 또는 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 또는 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc 시리즈 |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      지원되는 3.20(권장 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7(미디어 바이패스용 4.9)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     1000 시리즈 통합 서비스 라우터용 Cisco CUBE(통합 테두리 구성 요소)        |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.6.1a)         |    &#10004;     |   |  
|                                   |     4000 시리즈 통합 서비스 라우터용 Cisco CUBE(통합 테두리 구성 요소)        |     &#10004;   | &#10004; |   지원되는 IOS XE 암스테르담 17.2.1r(권장 17.6.1a)         |   &#10004;      |    |  
|                                   |     1000V 시리즈 클라우드 서비스용 Cisco CUBE(통합 테두리 구성 요소)       |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.3.3)         |    &#10004;     |    |  
|                                 |     1000 시리즈 집계 서비스 라우터용 Cisco CUBE(통합 테두리 구성 요소)      |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.2.1r(권장 17.6.1a)         |    &#10004;     |    |
|                                 |     표시 8000 Edge 플랫폼용 Cisco CUBE(통합 테두리 구성 요소)      |     &#10004;   | &#10004; |      지원되는 IOS XE 암스테르담 17.3.2(권장 17.6.1a)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    ASBCE(기업용 Avaya Session Border Controller)    |     &#10004;     |       &#10004;     |       릴리스 8.1.1(미디어 바이패스용 8.1.2)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5(1908)       |     |    |
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |      &#10004;     |       지원 대상 5.0, 5.1(권장 5.3)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape Session Border Controller   |     &#10004;     |   &#10004;        |     V10R2.2.0     |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse 네트워크](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 기술(이전의 Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel 시리즈   |     &#10004;     |         |      DGW 48.0.2340(권장 DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller(ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller(ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs BUILDER](https://46labs.com/docs/hcvoice/teams/)|    하이퍼 컨버지드 음성   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **911 서비스 공급자**

- [대역폭 동적 위치 라우팅](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado ERS(긴급 라우팅 서비스)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [EGW(Intrado 긴급 게이트웨이)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>로컬 미디어 최적화 지원

다음 표에서는 [로컬 미디어 최적화](direct-routing-media-optimization.md)를 지원하는 SBC 공급업체에 대해 설명합니다. 

| 공급업체 | 제품 |    소프트웨어 버전 |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    중앙값 500 SBC |   7.20A.256 | 
|            |  중앙값 800 SBC |   지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 2600 SBC |  지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 4000 SBC |  지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 1000B SBC | 지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 9000 SBC |  지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 가상 버전 SBC |   지원되는 7.20A.258(권장 7.40A.100)  |  
|            |  중앙값 클라우드 버전 SBC | 지원되는 7.20A.258(권장 7.40A.100)  |
| [Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |
| [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    ASBCE(기업용 Avaya Session Border Controller)    |  10.1.2 | 




## <a name="direct-routing-and-analog-devices-interoperability"></a>직접 라우팅 및 아날로그 디바이스 상호 운용성

다음 표에서는 직접 라우팅과 아날로그 디바이스 간의 상호 운용성을 위해 확인된 디바이스를 나열합니다.

|                                                       공급업체                                                        |       제품       | 확인됨
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 다중 플랫폼 아날로그 전화 어댑터 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 소프트웨어 버전 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 소프트웨어 버전 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 소프트웨어 버전 8.3.0.1.2 |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. 소프트웨어 버전: 8.1.1(빌드 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. 소프트웨어 버전: 8.1.1(빌드 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [리본 메뉴](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. 소프트웨어 버전: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  Grandstream GXW42xx이 포함된 anynode(V1.0.7.10) |     &#10004;     |
  

주 버전에 부여된 인증을 확인합니다. 즉, 주 버전 이후의 SBC 펌웨어에서 임의의 번호를 가진 펌웨어가 지원됩니다.

새 기능에 대한 아이디어 등 Teams 관련 피드백을 제공하려면 [Microsoft 피드백 포털](https://feedbackportal.microsoft.com/)을 방문하세요.


