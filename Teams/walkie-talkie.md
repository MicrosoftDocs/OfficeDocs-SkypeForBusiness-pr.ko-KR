---
title: 2018년 1월의 Walkie Talkie 애플리케이션 Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin 관점에서 Microsoft Teams Walkie Talkie 앱을 구성하는 방법.
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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62015018"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams

현재의 Walkie Talkie 앱은 Teams PTT(즉시 푸시-토크) 통신을 제공하며 이제 Android iOS에서 사용할 수 & 있습니다. Walkie Talkie를 사용하면 사용자가 구성원인 동일한 기저 채널을 사용하여 팀과 연결할 수 있습니다. 채널에서 Walkie Talkie에 연결하는 사용자만 참가자가 되기만 하여 한 번씩 푸시-토크를 사용하여 서로 통신할 수 있습니다.

이제 Walkie Talkie를 Teams 프런트라인 작업자는 부피가 큰 라디오를 수행하지 않고도 친숙한 PTT 환경과 안전하게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결로 어디서나 작동합니다.

## <a name="getting-started"></a>시작

### <a name="deploying-walkie-talkie"></a>Walkie Talkie 배포

Walkie Talkie는 GMS(Google Mobile Services) 및 iOS 디바이스를 Mobile Services Android 디바이스에서 지원됩니다. 

현재 Walkie Talkie는 미리 설치되어 있지 않습니다. 조직의 사용자에 대해 이 기능을 사용하도록 설정하려면 Walkie Talkie [](teams-app-setup-policies.md) 를 관리자 센터의 사용자에게 Teams 설치 정책에 [추가해야 합니다](https://admin.teams.microsoft.com/). 활성화되면 48시간 이내에 앱에서 Walkie Talkie를 사용할 수 있습니다.

### <a name="adding-walkie-talkie-to-your-app-list"></a>앱 목록에 Walkie Talkie 추가

Microsoft Teams 관리 센터의 Teams **AppSetup** >  정책에서 사용자 고정 허용을 On **으로 설정해야** **합니다**. 그런 다음 고정된 앱 섹션에서 **+앱 추가를 클릭합니다**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="고정된 앱 섹션 및 선택할 앱 추가 단추를 보여줍니다.":::

오른쪽 **에 나타나는** 고정된 앱 추가 패널에서 검색 텍스트 상자를 사용하여 Walkie  Talkie를 검색합니다. 검색 결과로 있는 경우 이름 오른쪽에 있는 추가 단추  를 선택하여 목록에 추가합니다.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="검색 창에 입력된 Walkie가 있는 고정된 앱 추가 사이드바와 검색 결과의 Walkie Talkie 앱 옆에 추가 단추가 표시됩니다.":::

이제 Walkie Talkie 앱이 고정된 앱 목록에 표시되어 저장 단추를 클릭하면 사용할 **수** 있습니다.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Walkie Talkie 앱이 추가된 고정된 앱 목록과 목록 아래에 저장 단추를 보여줍니다.":::

### <a name="network-documentation"></a>네트워크 설명서

워크리 토키 Teams 최적의 환경을 위해서는 인터넷 연결이 필요하고 네트워크 조건 아래에 있어야 합니다.

|메트릭 | 필수 |
|---|---|
|RTT(대기 시간) | < 300ms |
|지터 |< 30ms |
|패킷 손실 |< 1% |

위에서 설명한 대로 IP 네트워크를 통해 실시간 미디어의 품질은 네트워크 연결의 품질에 크게 영향을 주지만, 특히 다음의 양에 따라 크게 영향을 미치게 됩니다.

- **대기 시간** - 네트워크의 지점 A에서 B 지점까지 IP 패킷을 수신하는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 두 지점 사이의 물리적 거리와 라이트 속도 사이의 다양한 라우터에서 취한 오버헤드를 포함하여 물리적 거리와 연결됩니다. 대기 시간은 RTT(왕복 시간)로 측정됩니다.
- **도착 간 지** 터 - 연속 패킷 간의 평균 지연 변경입니다.
- **패킷 손실** - 종종 특정 기간에 손실되는 패킷의 백분율로 정의됩니다. 패킷 손실은 거의 영향을 주지 않고 개별 손실된 작은 패킷에서 전체 오디오 컷아웃을 일으키는 백-백 버스트 손실까지 오디오 품질에 직접 영향을 미치게 됩니다.

Walkie Talkie의 예상 데이터 사용량은 오디오를 보내거나 받을 때 약 20 Kb/s입니다. 유휴 시 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.

### <a name="walkie-talkie-devices"></a>Walkie Talkie 디바이스

프런트라인 작업자는 휴대폰이 잠겨 있는 경우에도 Walkie Talkie 통화를 말하고 수신해야 하는 경우가 종종 있습니다. 이 환경은 전용 PTT 단추가 있는 특수 디바이스를 통해 가능합니다.

- **헤드셋**
  - 무선 헤드셋(iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - 유선 헤드셋(Android만 해당)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **견고한 Android 휴대폰**
  - 삼성 [갤럭시 XCover](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) Pro, [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 수동 설정 - Teams 설치된 경우 XCover/Active 설정 > 고급 기능 > 이동합니다. '앱으로 XCover 키 제어'를 켜고 'Teams'
    - [MDM 설정](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 수동 설정 - Teams 설치된 전용 PTT 단추(LEFT_TRIGGER_2)는 기본적으로 Walkie Talkie와 함께 작동합니다.
    
> [!NOTE]
> 이러한 디바이스는 인증되지 Teams 없습니다. Walkie Talkie에서 작업하는 Teams 유효성이 검사됩니다.

### <a name="license-requirements"></a>라이선스 요구 사항

Walkie Talkie 앱은 구독의 모든 유료 Teams Office 365 [포함되어 있습니다](/office365/servicedescriptions/teams-service-description). 액세스 액세스에 대한 자세한 내용은 Teams 액세스 권한을  [Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="further-information"></a>추가 정보

- ITAdmins는 App Policies를 통해 Walkie Talkie를 사용하는 사용자에 대한 제어를 유지할 수 있습니다.
- 프런트라인 워커가 모바일 데이터를 사용하여 통신을 Teams Walkie Talkie는 동일한 방법을 사용합니다.
- Walkie Talkie는 대역폭이 낮은 상황에서나 스마트폰이 연결되고 작동되는 상황에서도 잘 작동해야 합니다. Walkie Talkie는 연결이 없는 경우 작동하지 않습니다.

최종 사용자 경험에 대한 자세한 내용은 다음을 참조하세요.

- [Walkie talkie Teams 시작](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Walkie Talkie를 통해 팀과 통신](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
