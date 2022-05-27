---
title: Microsoft Teams 워키 토키 앱
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin 관점에서 Microsoft Teams Walkie Talkie 앱을 구성하는 방법입니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e311fb94996e1c51bb5f73190539cd0e1f9f127
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681899"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 워키 토키 앱

Teams Walkie Talkie 앱은 팀에 대한 즉각적인 PTT(푸시 투 토크) 통신을 제공하며 이제 Android & iOS 사용할 수 있습니다. Walkie Talkie를 사용하면 사용자가 구성원인 것과 동일한 기본 채널을 사용하여 팀과 연결할 수 있습니다. 채널에서 Walkie Talkie에 연결하는 사용자만 참가자가 되고 한 번에 하나씩 푸시 투 토크를 사용하여 서로 통신할 수 있습니다.

Teams 워키 토키(Walkie Talkie)를 통해 일선 직원들은 이제 부피가 큰 라디오를 휴대할 필요 없이 친숙한 PTT 환경과 안전하게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결을 통해 어디서나 작동합니다.

> [!NOTE]
> 워키 토키는 현재 중국에서 사용할 수 없습니다.

## <a name="getting-started"></a>시작

### <a name="deploying-walkie-talkie"></a>워키 토키 배포

Walkie Talkie는 GMS(Google Mobile Services) 및 iOS 디바이스를 사용하는 Android 장치에서 지원됩니다.

### <a name="pin-walkie-talkie-to-teams"></a>Teams 워키 토키 고정

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>맞춤형 최전방 앱 환경을 사용하여 Walkie Talkie 및 기타 앱을 Teams

Teams 맞춤형 최전방 앱 환경은 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자를 위해 Teams 가장 관련성이 큰 앱을 고정합니다. 고정된 앱에는 Walkie Talkie, 교대 근무, 작업 및 승인 포함됩니다. 기본적으로 이 기능은 최전방 근로자에게 요구 사항에 맞는 기본 제공 환경을 제공합니다.

앱은 사용자가 빠르고 쉽게 액세스할 수 있는 앱 바(Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트의 아래쪽에 있는 막대)에 고정됩니다.

설정한 앱 정책의 작동 방식을 포함하여 자세한 내용은 [최전방 작업자를 위한 Teams 앱 조정](pin-teams-apps-based-on-license.md)을 참조하세요.

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>앱 설정 정책을 사용하여 Walkie Talkie를 Teams 고정

앱 설정 정책을 사용하면 사용자의 사용자에게 가장 중요한 앱을 고정하는 Teams 사용자 지정할 수 있습니다.

사용자를 위해 Walkie Talkie 앱을 고정하려면 전역(조직 전체 기본값) 정책을 편집하거나 사용자 지정 앱 설정 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="고정된 앱 추가 창의 고정된 앱 목록에 Walkie Talkie를 추가하는 스크린샷" lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>네트워크 설명서

Teams Walkie Talkie는 최적의 환경을 위해 인터넷 연결이 필요하고 네트워크 조건 미만이 필요합니다.

|메트릭 | 필수 |
|---|---|
|대기 시간(RTT) | < 300ms |
|지터 |< 30ms |
|패킷 손실 |< 1% |

위에서 설명한 것처럼 IP 네트워크를 통해 실시간 미디어의 품질은 네트워크 연결의 품질, 특히 다음의 양에 의해 크게 영향을 받습니다.

- **대기 시간** - 네트워크의 지점 A에서 지점 B까지 IP 패킷을 가져오는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 두 지점 사이의 물리적 거리와 빛의 속도와 관련이 있으며, 그 사이에 다양한 라우터가 더 많은 오버헤드를 사용합니다. 대기 시간은 RTT(왕복 시간)로 측정됩니다.
- **도착 간 지터** - 연속 패킷 간의 평균 지연 변화입니다.
- **패킷 손실** - 지정된 기간 동안 손실되는 패킷의 백분율로 정의되는 경우가 많습니다. 패킷 손실은 영향을 거의 받지 않는 작은 개별 손실 패킷부터 완전한 오디오 컷아웃을 유발하는 백투백 버스트 손실에 이르기까지 오디오 품질에 직접적인 영향을 줍니다.

오디오를 보내거나 받을 때 Walkie Talkie의 예상 데이터 사용량은 약 20Kb/s입니다. 유휴 상태일 때 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.

### <a name="walkie-talkie-devices"></a>워키 토키 디바이스

일선 근로자는 종종 휴대 전화가 잠겨있는 경우에도 워키 토키 전화를 말하고 받아야합니다. 이 환경은 전용 PTT 단추가 있는 특수 디바이스를 통해 가능합니다.

- **헤드셋**
  - 무선 헤드셋(iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - 유선 헤드셋(Android 전용)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **러기드 Android 휴대폰**
  - 삼성 [갤럭시 XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [갤럭시 XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [갤럭시 탭 활성 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 수동 설정 - Teams 설치된 상태에서 XCover/활성 키를 > 설정 > 고급 기능으로 이동합니다. '앱으로 XCover 키 제어'를 켜고 'Teams'을 선택합니다.
    - [MDM 설정](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 수동 설정 - Teams 설치되면 전용 PTT 단추(LEFT_TRIGGER_2)가 기본적으로 Walkie Talkie에서 작동합니다.
    
> [!NOTE]
> 이러한 디바이스는 Teams 인증되지 않았습니다. 그들은 Teams 워키 토키와 함께 일하는 것으로 확인되었습니다.

### <a name="license-requirements"></a>라이선스 요구 사항

Walkie Talkie 앱은 Office 365 구독에서 Teams 모든 유료 라이선스에 포함되어 [있습니다](/office365/servicedescriptions/teams-service-description). Teams 가져오는 방법에 대한 자세한 내용은 [Microsoft Teams 액세스](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b) 어떻게 할까요? 확인하세요.

## <a name="further-information"></a>추가 정보

- IT 관리자는 앱 정책을 통해 Walkie Talkie를 사용하는 사용자를 제어할 수 있습니다.
- 일선 작업자가 모바일 데이터를 사용하여 Teams 통해 통신하는 경우 Walkie Talkie는 동일한 방법을 사용합니다.
- 워키 토키는 낮은 대역폭 상황 또는 스마트 폰이 연결되고 작동하는 상황에서 잘 작동해야합니다. 워키 토키는 연결이 전혀 없을 때 작동하지 않습니다.

최종 사용자 환경에 대한 자세한 내용은 다음을 참조하세요.

- [Teams 워키 토키와 시작](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Walkie Talkie를 사용하여 팀과 커뮤니케이션](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
