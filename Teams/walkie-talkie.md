---
title: Microsoft Teams의 Walkie Talkie 애플리케이션
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin 관점에서 Microsoft Teams에서 Walkie Talkie 앱을 구성하는 방법.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb00501a0c795f754c927dd9ed3bd5114f61fab7
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875048"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams의 Walkie Talkie 앱

Teams의 Walkie Talkie 앱은 팀에 대한 PTT(즉시 푸시-토크) 통신을 제공하며 이제 Android에서 사용할 수 있습니다. Walkie Talkie를 사용하면 사용자가 구성원인 동일한 기저 채널을 사용하여 팀과 연결할 수 있습니다. 채널에서 Walkie Talkie에 연결하는 사용자만 참가자가 되기만 하여 한 번씩 푸시-토크를 사용하여 서로 통신할 수 있습니다.

Teams의 Walkie Talkie를 사용하여 프런트라인 작업자는 부피가 큰 라디오를 들지 않고도 친숙한 PTT 환경과 안전하게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결로 어디서나 작동합니다.

## <a name="getting-started"></a>시작

### <a name="deploying-walkie-talkie"></a>Walkie Talkie 배포

현재 Walkie Talkie는 미리 설치되어 있지 않습니다. 조직의 사용자가 이 기능을 사용하도록 설정하려면 Teams 관리 센터의 [](teams-app-setup-policies.md)사용자에게 할당된 앱 설정 정책에   Walkie [Talkie를 추가해야 합니다.](https://admin.teams.microsoft.com/)

활성화되면 48시간 이내에 Android 앱에서 Walkie Talkie를 사용할 수 있습니다.

### <a name="adding-walkie-talkie-to-your-app-list"></a>앱 목록에 Walkie Talkie 추가

Microsoft Teams 관리 센터의 **Teams 앱** 설정 정책 아래에서 사용자 고정 허용을  >  On으로 설정해야 **합니다.**  그런 다음 고정된 앱 섹션에서 **+앱 추가 를 클릭합니다.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="고정된 앱 섹션 및 선택할 앱 추가 단추를 보여줍니다.":::

오른쪽에  나타나는 고정된 앱 추가 패널에서 검색  텍스트 상자를 사용하여 Walkie Talkie를 검색합니다. 검색 결과로 있는 경우 이름  오른쪽에 있는 추가 단추를 선택하여 목록에 추가합니다.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="검색 창에 입력된 Walkie가 있는 고정된 앱 추가 사이드바와 검색 결과의 Walkie Talkie 앱 옆에 추가 단추가 표시됩니다.":::

이제 Walkie Talkie 앱이 고정된 앱 목록에 표시되어 저장 단추를 클릭하면 사용할 **수** 있습니다.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Walkie Talkie 앱이 추가된 고정된 앱 목록과 목록 아래에 저장 단추를 보여줍니다.":::

### <a name="network-documentation"></a>네트워크 설명서

Teams의 Walkie Talkie는 최적의 환경을 위해 인터넷 연결이 필요하며 네트워크 조건 아래에 있어야 합니다.

|메트릭 | 필수 |
|---|---|
|RTT(대기 시간) | < 300ms |
|지터 |< 30ms |
|패킷 손실 |< 1% |

위에서 설명한 대로 IP 네트워크를 통해 실시간 미디어의 품질은 네트워크 연결의 품질에 크게 영향을 주지만, 특히 다음의 양에 따라 크게 영향을 미치게 됩니다.

- **대기 시간** - 네트워크의 지점 A에서 B 지점까지 IP 패킷을 수신하는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 두 지점 사이의 물리적 거리와 라이트 속도 사이의 다양한 라우터에서 취한 오버헤드를 포함하여 물리적 거리와 연결됩니다. 대기 시간은 RTT(왕복 시간)로 측정됩니다.
- **패킷 손실** - 종종 특정 기간에 손실되는 패킷의 백분율로 정의됩니다. 패킷 손실은 거의 영향을 주지 않고 개별 손실된 작은 패킷에서 전체 오디오 컷아웃을 일으키는 백-백 버스트 손실까지 오디오 품질에 직접 영향을 미치게 됩니다.
- **Jitter** - 연속 패킷 간의 지연의 평균 변경입니다.

Walkie Talkie의 예상 데이터 사용량은 오디오를 보내거나 받을 때 약 20KB/s입니다. 유휴 시 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.

### <a name="walkie-talkie-devices"></a>Walkie Talkie 디바이스

프런트라인 작업자는 휴대폰이 잠겨 있는 경우에도 Walkie Talkie 통화를 말하고 수신해야 하는 경우가 종종 있습니다. 이 환경은 전용 PTT 단추가 있는 특수 디바이스를 통해 가능합니다.

- 헤드셋
  - 유선[헤드셋(Klein Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)
  - 무선[헤드셋(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- 견고한 휴대폰
  - 삼성 갤럭시 XCover Pro
    - [자세한 정보](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)입니다.
    - [설정 가이드.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> 이러한 디바이스는 Teams 인증되지 않습니다. Teams Walkie Talkie와 함께 작업할 수 있는 유효성이 검사됩니다.

### <a name="license-requirements"></a>라이선스 요구 사항

Walkie Talkie 앱은 [Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)구독의 Teams의 모든 유료 라이선스에 포함됩니다. Teams를 다운로드하는 방법에 대한 자세한 내용은 Microsoft Teams에 액세스하는 방법을 [확인하세요.](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> 특정 고급 기능에는 추가 라이선스가 필요할 수 있습니다. 예를 들어 삼성 갤럭시 XCover Pro와 통합하려면 Knox 라이선스가 필요합니다.

## <a name="further-information"></a>추가 정보

- ITAdmins는 App Policies를 통해 Walkie Talkie를 사용하는 사용자에 대한 제어를 유지할 수 있습니다.
- Frontline 워커가 모바일 데이터를 사용하여 Teams를 통해 통신하는 경우 Walkie Talkie는 동일한 방법을 사용합니다.
- Walkie Talkie는 대역폭이 낮은 상황에서나 스마트폰이 연결되고 작동되는 상황에서도 잘 작동해야 합니다. Walkie Talkie는 연결이 없는 경우 작동하지 않습니다.

최종 사용자 경험에 대한 자세한 내용은 다음을 참조하세요.

- [Teams Walkie Talkie 시작](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Walkie Talkie를 통해 팀과 통신](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
