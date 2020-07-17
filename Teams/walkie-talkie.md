---
title: Microsoft 팀의 Walkie Talkie 응용 프로그램
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin 관점에서 Microsoft 팀의 Walkie Talkie 앱을 구성 하는 방법을 설명 합니다.
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
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043017"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft 팀의 Walkie Talkie app

[!INCLUDE [preview-feature](includes/preview-feature.md)]

팀에 있는 Walkie Talkie 앱은 팀에 대 한 PTT (인스턴트) 통신을 제공 하며 Android의 공개 미리 보기에서 곧 사용할 수 있게 됩니다. Walkie Talkie 사용자는 자신이 구성원으로 속해 있는 동일한 기본 채널을 사용 하 여 팀과 연결할 수 있습니다. 채널에서 Walkie Talkie에 연결 하는 사용자만이 참가자가 되며 한 번에 하나씩 푸시 투-통신을 사용 하 여 서로 통신할 수 있습니다.

Walkie Talkie 팀에서 현재에서 일선 worker는 라디오를 사용할 필요 없이 익숙한 ptt 환경과 안전 하 게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결을 통해 어디서 나 작동 합니다.

## <a name="getting-started"></a>시작

### <a name="deploying-walkie-talkie"></a>Walkie Talkie 배포

공개 미리 보기 중에는 Walkie Talkie가 사전 설치 되어 있지 않습니다. 조직의 사용자에 대해이 기능을 사용 하도록 설정 하려면 [App Setup Policy](teams-app-setup-policies.md)   [팀 관리 센터](https://admin.teams.microsoft.com/)에서 사용자에 게 할당 된 앱 설정 정책에 Walkie Talkie를 추가 해야 합니다.

활성화 한 후에는 Walkie Talkie 48 시간 내에 Android 앱에서 사용할 수 있게 됩니다.

### <a name="adding-walkie-talkie-to-your-app-list"></a>앱 목록에 Walkie Talkie 추가

Microsoft 팀 관리 센터의 **팀 앱**  >  **설정 정책**에서 **사용자 고정 허용** 을 **On**으로 설정 해야 합니다. 그런 다음 고정 된 앱 섹션에서 **+ 앱 추가**를 클릭 합니다.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="고정 된 앱 섹션 및 선택 되는 앱 추가 단추를 표시 합니다.":::

오른쪽에 표시 되는 **고정 된 앱 추가** 패널에서 **검색** 텍스트 상자를 사용 하 여 Walkie Talkie를 찾습니다. 검색 결과로 있으면 이름 오른쪽에 있는 **추가** 단추를 클릭 하 여 목록에 추가 합니다.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="검색 창에 Walkie를 입력 하 고 검색 결과 옆에 있는 추가 단추를 사용 하 여 Walkie Talkie 앱을 고정 된 앱 추가 사이드바를 표시 합니다.":::

이제 Walkie Talkie 앱이 고정 된 앱 목록에 나타나고 **저장** 단추를 클릭 하면 사용할 수 있게 됩니다.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Walkie Talkie app이 추가 된 고정 앱 목록과 목록 아래에 있는 저장 단추를 보여 줍니다.":::

### <a name="network-documentation"></a>네트워크 설명서

Walkie Talkie 팀은 인터넷에 연결 되어야 하 고, 최상의 환경을 위해 네트워크 조건 아래에 있어야 합니다.

지연 (RTT) < 300ms | 지터 < 30ms | 패킷 손실 < 1%

위에서 언급 한 것 처럼 IP 네트워크를 통한 실시간 미디어의 품질은 네트워크 연결의 품질에 따라 크게 영향을 받지만, 특히 다음의 금액에 의해 발생 합니다.

- **대기 시간** -네트워크의 지점간 a에서 B 지점의 IP 패킷을 받는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 본질적으로 두 점과 라이트의 속도 사이에서 다양 한 라우터가 차지 하는 추가 오버 헤드를 포함 하 여 실제 거리에 연결 됩니다. 대기 시간은 왕복 시간 (RTT)으로 측정 됩니다.
- **패킷 손실** -지정 된 시간 창에서 손실 되는 패킷의 백분율로 정의 되는 경우가 많습니다. 패킷 손실로 인해 오디오 품질에 직접적인 영향을 주지 않고, 거의 전혀 영향을 주지 않는 개별 손실 패킷, 그리고 완전 한 오디오 컷오프로 인 한 연속 버스트 손실.
- **지터** -연속 된 패킷 간의 지연 시간 변경입니다.

Walkie Talkie의 예상 데이터 사용량은 오디오를 보내거나 받을 때 약 20KB/s입니다. 유휴 상태일 때 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.

### <a name="walkie-talkie-devices"></a>Walkie Talkie 장치

일반적으로 FirstLine worker는 전화를 Walkie Talkie 전화를 주고 받아야 할 때도 있습니다. 전용 PTT 단추가 있는 특수 장치를 통해이 문제가 발생할 수 있습니다.

- 기존 전화
  - 유선 헤드셋 ([Klein 전자](https://www.kleinelectronics.com/))
  - 무선 헤드셋 ([Jabra BlueParrott](https://www.blueparrott.com/))
- 강력한 전화
  - 삼성 Galaxy XCover Pro
    - [추가 정보](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [설정 가이드](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> 이러한 장치는 인증 된 팀이 아닙니다. 팀 Walkie Talkie에서 작업 하도록 유효성을 검사 했습니다.

### <a name="license-requirements"></a>라이선스 요구 사항

Walkie Talkie 앱은 [Office 365 구독](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)에서 팀의 모든 유료 라이선스에 포함 되어 있습니다. 팀을 가져오는 방법에 대 한 자세한 내용은 [Microsoft 팀에 대 한 액세스 권한을 얻는 방법](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)확인을 참조 하세요.

> [!NOTE]
> 일부 고급 기능에는 추가 라이선스가 필요할 수 있습니다. 예를 들어 삼성 Galaxy XCover Pro와 통합 하려면 Knox 라이선스가 필요 합니다.

## <a name="further-information"></a>추가 정보

- ITAdmins는 앱 정책을 통해 Walkie Talkie를 사용 하는 사람을 제어할 수 있습니다.
- 에서 일선 worker가 팀을 통해 통신 하는 데 모바일 데이터를 사용 하는 경우 Walkie Talkie는 동일한 메서드를 사용 합니다.
- Walkie Talkie는 낮은 대역폭 상황이 나 smartphone이 연결 되어 작동 하는 경우에도 잘 작동 합니다. 연결이 없는 경우 Walkie Talkie는 작동 하지 않습니다.

최종 사용자 환경에 대 한 자세한 내용은 다음을 참조 하세요.

- [Walkie Talkie 팀 시작 하기](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Walkie Talkie를 사용 하 여 팀과 의사 소통](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
