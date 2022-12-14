---
title: SIP 게이트웨이 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 요구 사항 및 이점과 같은 SIP 게이트웨이에 대해 자세히 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d2bd923835da3c9ffcbf32e0675f1f0e4e63bd3
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392218"
---
# <a name="plan-for-sip-gateway"></a>SIP 게이트웨이 계획

SIP 게이트웨이를 사용하면 조직에서 Microsoft Teams와 호환되는 모든 SIP 디바이스를 사용하여 SIP 디바이스에 대한 투자를 유지할 수 있습니다. 이제 회사 자격 증명으로 Teams에 로그인하고 호환되는 SIP 디바이스로 전화를 걸고 받을 수 있습니다. 호환 디바이스는 표준 SIP 펌웨어가 있는 IP 휴대폰, 다중 플랫폼 SIP 펌웨어가 있는 Cisco IP 휴대폰 또는 Poly, Yealink 및 AudioCodes와 같은 공급업체의 SIP 디바이스를 비즈니스용 Skype 수 있습니다. SIP 게이트웨이에 대한 SIP 디바이스를 구성하는 방법을 알아보려면 [SIP 게이트웨이 구성](sip-gateway-configure.md)을 참조하세요.

## <a name="benefits-of-sip-gateway"></a>SIP 게이트웨이의 이점

SIP 게이트웨이는 호환되는 SIP 디바이스를 Teams에 연결하여 사용자가 Teams 전화 통신으로 원활하게 마이그레이션할 수 있도록 지원합니다. 사용자는 SIP 게이트웨이를 사용하여 다음을 모두 수행할 수 있습니다.

- **전화를 걸기:** SIP 디바이스 사용자는 PSTN(공용 전환 전화 네트워크), 다른 SIP 디바이스 및 Teams 및 비즈니스용 Skype 사용자에게 전화를 걸 수 있습니다. SIP 디바이스 사용자는 전화 번호가 있는 사용자만 전화를 걸 수 있습니다.
- **수신 전화:** SIP 디바이스 사용자는 PSTN, Teams 또는 SIP 디바이스가 있는 비즈니스용 Skype 사용자, Teams 및 비즈니스용 Skype 클라이언트 애플리케이션에서 전화를 받을 수 있습니다. SIP 디바이스는 Teams 엔드포인트 역할을 합니다. 또한 인바운드 호출은 사용자의 SIP 디바이스로 포크됩니다.
- **여러 동시 호출:** 통화에 있는 SIP 디바이스 사용자는 통화를 보류하여 다른 전화를 걸거나 받을 수 있습니다. SIP 디바이스 사용자는 두 번의 통화를 회의할 수도 있습니다.
- **방해 금지:** SIP 디바이스 사용자는 디바이스가 들어오는 호출에 대해 울리지 않도록 디바이스에서 방해 금지 를 설정할 수 있습니다. 이는 다른 모든 Teams 엔드포인트에서 사용자의 상태에 영향을 주지 않습니다.
- **보류/다시 시작 및 음소거/음소거 해제:** SIP 디바이스 사용자는 디바이스에서 해당 작업에 대한 기능을 사용하여 통화를 보류 및 다시 시작하거나 음소거하고 음소거 해제할 수 있습니다.
- **음성:** SIP 디바이스 사용자는 발신자가 떠나는 전자적으로 저장된 음성 메시지를 들을 수 있습니다.
- **메시지 대기 표시기:** SIP 디바이스 사용자는 새 음성 메일 메시지가 있을 때 경고하는 알림을 받을 수 있습니다.
- **로그인 및 로그아웃:** SIP 디바이스 사용자는 디바이스에서 Teams에 로그인하고 로그아웃할 수 있습니다.
- **이중 톤 다중 주파수:** SIP 디바이스 사용자는 대화형 음성 응답 호출 중에 숫자 키를 눌러 입력을 제공할 수 있습니다.
- **Teams 모임:** SIP 디바이스 사용자는 모임 액세스 번호로 전화를 걸어 Teams 모임에 참가할 수 있습니다. 모임 참가자는 사용자의 전화 번호로 전화를 걸거나 '참가 요청'을 클릭하여 참가자를 추가하여 모임에 SIP 디바이스 사용자를 추가할 수 있습니다. 또한 사용자의 SIP 디바이스에 경고합니다. 다른 조직의 게스트 사용자는 게스트 사용자의 번호로 전화를 걸어 해당 게스트를 포함하는 참가자가 Teams 모임에 추가할 수 있습니다.
- **통화 전송:** SIP 디바이스 사용자는 통화를 전송할 수 있습니다. SIP 게이트웨이는 블라인드 및 컨설팅 전송을 모두 지원합니다.
- **로컬 착신 전환:** SIP 디바이스 사용자는 디바이스에 대한 전달 규칙(항상 시간 제한 및 사용 중)을 설정할 수 있습니다. 디바이스가 SIP 게이트웨이에 연결된 경우 디바이스 사용자가 설정한 규칙에 따라 호출이 대상 주소로 리디렉션됩니다. 로컬 착신 전환 작업을 수행하려면 관리자가 `AllowCallRedirect` 의 특성을 로 `Set-CsTeamsCallingPolicy` `Enabled`설정해야 합니다.
- **부실 디바이스 오프보딩:** SIP 게이트웨이는 테넌트에 대해 프로비전된 부실 디바이스의 자동 오프보딩을 지원합니다. 페어링된(로그인한) 디바이스는 30일 동안 연결되지 않은 경우 오프보딩되고, 14일 후에는 미지급(로그아웃) 디바이스가 오프보딩됩니다. 오프보딩된 디바이스는 공장 초기화 후 다시 온보딩할 수 있습니다.

## <a name="requirements-to-use-sip-gateway"></a>SIP 게이트웨이 사용 요구 사항

Teams 사용자는 SIP 게이트웨이를 사용하려면 PSTN 통화가 사용하도록 설정된 전화 번호가 있어야 합니다.

> [!NOTE]
> 정부 환경(GCC, GCC High 및 DoD)에는 SIP 게이트웨이를 사용할 수 없습니다.

### <a name="hardware-software-and-licenses"></a>하드웨어, 소프트웨어 및 라이선스

3PIP 또는 SIP 디바이스가 있는 경우 다음이 있어야 합니다.

- Microsoft Teams, 비즈니스용 Skype Online Plan 2 및 Microsoft 365 Phone System에 대한 라이선스(E5 또는 독립 실행형 라이선스를 통해)
- Microsoft Teams 통화 플랜, 직접 라우팅 또는 운영자 연결을 통한 PSTN 사용(즉, 전화 번호)
- 공용 영역 디바이스에 대한 **Microsoft Teams 공유** 디바이스 라이선스

## <a name="compatible-devices"></a>호환되는 디바이스

|공급업체    |모델      |최소 펌웨어 버전|승인된 펌웨어 버전|설명|링크|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |엔터프라이즈 펌웨어를 실행하는 디바이스는 다중 플랫폼 펌웨어로 변환해야 합니다. 방법을 알아보려면 오른쪽의 가이드를 읽어보세요.|[Cisco 펌웨어 변환 가이드](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832<sup>1</sup>       |11.3.5MPP   |11-3-7MPP  |   |   |
|          |6821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8845<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8851<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8865<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|**많은**  |           |            |           |디바이스가 자동으로 다시 부팅되고 선택한 펌웨어가 설치됩니다.|   |
|          |트리오 8500  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |트리오 8800  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove B4    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 30    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 40    |8.0.3.0010  |8.0.3.0010 |   |   |
|**Yealink**|          |            |           |   |[Yealink 지원](https://support.yealink.com/)|
|          |T21P       |83          |34.72.0.75 |   |   |
|          |T21P_E2    |83          |52.84.0.125|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G<sup>1</sup>      |83          |69.86.0.15 |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30<sup>1</sup>       |83          |124.86.0.40|   |   |
|          |T30P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T33G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T41S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T43U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|          |T46S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T48U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T53<sup>1</sup>       |83          |96.86.5.1  |   |   |
|          |T53W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T54W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T57W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |W56H                  |            |61.85.0.56 |   |   |
|          |W73H                  |            |116.85.0.38|   |   |
|          |W59R                  |            |115.85.0.56|   |   |
|          |W70B NOAM             |            |146.85.5.4 |   |   |
|          |W70B EMEA             |            |146.85.5.2 |   |   |
|          |W70B APAC             |            |146.85.5.3 |   |   |
|          |W80 NOAM              |            |130.85.5.5 |   |   |
|          |W80 EMEA              |            |130.85.5.6 |   |   |
|          |W80 APAC              |            |130.85.5.4 |   |   |
|          |W90 NOAM              |            |130.85.5.5 |   |   |
|          |W90 EMEA              |            |130.85.5.6 |   |   |
|          |W90 APAC              |            |130.85.5.4 |   |   |
|**AudioCodes**|       |            |           |일부 AudioCodes SIP 디바이스에는 프로비저닝 URL 설정이 필요합니다. 오른쪽에 영향을 받는 AudioCodes 디바이스에 대한 업그레이드 파일을 다운로드하고 설치합니다. |[AudioCodes에서 영향을 받는 디바이스에 대한 다운로드 가능한 파일](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.589 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |405HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |420HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |430HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704 |   |   |
|          |445HDG<sup>1</sup>     |3.2.1      |3.4.6.704 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.704  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.704  |   |   |
|**Spectralink**|       |           |           |   |[Spectralink 지원](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |단말기 |   |
|          |7212        |PCS22B     |PCS22B     |단말기 |   |
|          |7502        |PCS22B     |PCS22B     |단말기 |   |
|          |7522        |PCS22B     |PCS22B     |단말기 |   |
|          |7532        |PCS22B     |PCS22B     |단말기 |   |
|          |7622        |PCS22B     |PCS22B     |단말기 |   |
|          |7642        |PCS22B     |PCS22B     |단말기 |   |
|          |7722        |PCS22B     |PCS22B     |단말기 |   |
|          |7742        |PCS22B     |PCS22B     |단말기 |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |IP-DECT 서버 |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |IP-DECT 서버 |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |IP-DECT 서버 |   |
|          |가상 IP-DECT 서버 1 |PCS22Ab |PCS22Ab |IP-DECT 서버 |   |
|          |IP-DECT 기지국 |PCS22Ab |PCS22Ab |IP-DECT 서버 |   |
|**Ascom**|       |           |           |   |[Ascom 지원](https://www.ascom.com/products-and-services/services/support-and-maintenance/)|
|          |Ascom d43        |2.11.4     |2.11.4     |단말기 |   |
|          |Ascom d63        |2.11.4     |2.11.4     |단말기 |   |
|          |Ascom d81        |4.13.1     |4.13.1     |단말기 |   |
|          |Ascom d83        |4.13.1     |4.13.1     |단말기 |   |
|          |Ascom Myco 3 DECT        |3.4.1     |3.4.1     |단말기 |   |
|          |IP-DECT 액세스 지점 IPBSx        |11.8.8     |11.8.8     |IP-DECT 액세스 지점 |   |
|          |IP-DECT 게이트웨이 IPBL     |11.8.8     |11.8.8     |IP-DECT 게이트웨이 |   |
|          |TDM 기지국        |R3N     |R3N     |IP-DECT 기지국 |   |
|          |IP-DECT 가상 어플라이언스 IPVM        |11.8.8     |11.8.8     |IP-DECT 서버 |   |

<sup>1</sup> 디바이스는 SIP 게이트웨이를 사용하여 E911(동적 긴급 통화)을 지원합니다.

> [!NOTE]
> 고객은 AudioCodes OVOC 및 Poly Lens를 사용하여 AudioCodes 400 시리즈 및 Poly VVX/Trio 디바이스의 디바이스 쪽 구성을 각각 관리할 수 있습니다.

> [!NOTE]
> Spectralink 핸드셋은 Spectralink IP-DECT 서버에서 무선으로 펌웨어 업데이트를 받습니다.

> [!NOTE]
> Ascom 핸드셋은 Ascom IP-DECT 서버에서 무선으로 펌웨어 업데이트를 받습니다.

> [!NOTE]
> Yealink DECT 기본 스테이션의 경우 최상의 통화 환경을 위해 위에 나열된 적절한 지역별 펌웨어 버전을 사용하세요.

> [!NOTE]
> 지원 쿼리의 경우 Teams SIP Gateway와 함께 IP-DECT 시스템을 사용하는 고객은 DECT 제조업체 또는 구현 채널 파트너에게 문의해야 합니다.

> [!NOTE]
> 일부 디바이스의 경우 최소 펌웨어 버전이 승인된 펌웨어 버전보다 큽 있습니다. 이는 3.X 버전이 비즈니스용 Skype 버전이기 때문입니다. 2.X인 SIP 버전을 업데이트합니다.
