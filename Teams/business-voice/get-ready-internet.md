---
title: 인터넷 연결 확인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4dbfd1bdaec48ebe8c6adbed86da431a6f4ecbfc
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972279"
---
# <a name="check-your-internet-connection"></a>인터넷 연결 확인

Business Voice는 Microsoft 365에서 클라우드에 있습니다. Microsoft Teams와 Business Voice를 사용하는 모든 컴퓨터와 장치는 인터넷 연결을 필요로 합니다. Business Voice를 사용하여 최고의 환경을 활용 하려면 어느 특정 시간에 걸려올 수 있는 예상 전화의 수를 지원할 수 있는 광대역 인터넷 연결이 필요합니다. 또한 네트워크에 있는 컴퓨터에서 Microsoft 365 서버에 연결할 수 있는지 확인해야 합니다.

이 단계를 따르려면 다음의 구독 중 하나를 포함하는 테넌트가 있어야 합니다.

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

이들 단계를 따르기 위해 Business Voice 라이선스가 필요하지는 않습니다.

## <a name="check-your-internet-connection-speed"></a>인터넷 연결 속도를 확인합니다

이 문서는 사용자의 인터넷 연결이 전화를 걸고 화상 회의를 호스팅하는 등의 작업을 수행해야 하는 사용자의 수를 수용하기에 충분히 빠른지를 확인하는 데 도움을 줍니다. 사용자는 조직에 대한 정보를 입력하고 Teams와 Business Voice가 사용할 인터넷 연결의 용량이 포함된 보고서를 받습니다.

### <a name="get-information-about-your-internet-connection-and-users"></a>인터넷 연결 및 사용자에 대한 정보 받기

시작하기 전에 다음의 정보를 알고 있어야 합니다.

* 인터넷 연결 속도.
* 사무실에서 주로 Business Voice를 사용하는 사용자의 수.
* 홈 사무실과 같이 주로 원격 위치에서 Business Voice를 사용하는 사용자의 수.

### <a name="enter-your-information-into-the-network-planner"></a>네트워크 플래너에 사용자 정보를 입력합니다.

수행해야 하는 사항은 다음과 같습니다.

1. 브라우저를 열고 https://admin.teams.microsoft.com로 이동하여 전역 관리자 권한이 있는 계정으로 로그인합니다. Office 365에 등록하는 데 사용한 계정에는 이러한 사용 권한이 있습니다.
1. **조직 전체 설정**을 열고 **네트워크 플래너**를 선택합니다.
1. **네트워크 플랜**에서 **추가**를 선택합니다. 플랜에 이름을 지정하고 **적용**을 선택합니다. 네트워크 플랜은 다음과 같이 보여야 합니다.

    ![네트워크 플래너의 메인 화면](../media/network-planner-main.png)
1. 네트워크 플랜의 이름을(위의 그림에서 **주 사무실**) 클릭합니다.
1. 다음 페이지에서 **네트워크 사이트**탭의 **네트워크 사이트 추가**를 선택합니다.
1. 다음의 정보를 입력하고 **저장**을 선택합니다.

    ![네트워크 플래너 사이트 정보](../media/network-planner-site-info.png)
1. **보고서** 탭에서 **보고서 시작**을 선택합니다.
1. 다음의 정보를 입력하고 **보고서 작성**을 선택합니다.

    ![네트워크 플래너 보고서 정보](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>최소 인터넷 연결 속도를 확인합니다

**보고서 작성**을 선택 시 Office 365에서 다음과 같이 표시되는 보고서를 만듭니다.

![네트워크 플래너 보고서의 세부 정보](../media/network-planner-report.png)

강조 표시된 숫자는 Teams와 Business Voice가 사용할 인터넷 연결의 용량을 보여줍니다. 이 숫자가 총 인터넷 연결 속도의 30%를 넘지 않는 것이 좋습니다. 예를 들어 인터넷 연결 속도가 60Mbps인 경우 Teams와 Business Voice는 18Mbps 이상을 차지하지 않아야 합니다.

다음의 계산을 수행하여 최소 인터넷 연결 속도를 확인할 수 있습니다. `<highlighted number> / .3`. 위 그림에 강조 표시된 숫자를 사용하면 계산은 `4.6875 / .3 = 15.6`가 됩니다. 즉, 최소 인터넷 연결 속도가 적어도 15.6Mbps가 되어야 합니다.

Teams와 Business Voice에서 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 강조 표시된 숫자가 빨간색으로 표시됩니다. 이러한 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.

![연결 속도 경고](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>네트워크의 컴퓨터와 장치가 Microsoft 365에 연결될 수 있는지 확인합니다

제대로 작동하려면 Business Voice를 사용하려는 컴퓨터와 장치가 특정 네트워크 포트를 사용하 여 Microsoft 365 서버와 통신을 해야 합니다. 네트워크 포트는 기본적으로 네트워크 또는 인터넷을 통해 컴퓨터와 장치가 서로 통신할 수 있는 문입니다. 사용자의 방화벽은 네트워크의 컴퓨터 및 장치가 다음의 아웃바운드 네트워크 포트를 사용하 여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.

* **TCP 포트** 80 및 443
* **UDP 포트** 3478, 3479, 3480 및 3481

방화벽이 이들 네트워크 포트에서의 통신을 허용하는지를 확인하는 가장 쉬운 방법은 Teams를 사용하여 테스트를 해보는 것입니다. 테스트를 수행하려면 다음을 수행합니다.

1. 네트워크의 컴퓨터에서 https://aka.ms/getteams로 이동하여 Teams를 설치합니다. 스피커와 마이크가이 컴퓨터에 연결되어 있는지 확인합니다.
2. Teams를 열고 Microsoft 365 계정을 사용하여 로그인합니다.
3. Teams에서 프로필 사진을 선택한 다음 **설정** > **장치**를 선택합니다.
4. **오디오 장치**에서 **테스트 전화걸기**를 선택합니다.
5. 프롬프트에 따라 메시지를 나가고 다시 재생합니다.

* 통화가 연결되고 메시지가 재생되는 것을 들을 수 있다면 방화벽이 제대로 설정된 것입니다.
* 통화가 연결되지만 프롬프트나 메시지가 재생되는 것을 듣지 못하는 경우 스피커와 마이크가 컴퓨터에서 제대로 설정되고 인식이 되는지를 확인합니다. 다시 시도하십시오.
* 통화가 연결되지 않거나 연결되어도 메시지가 ㅅ재생되는 것을 듣지 못하는 경우 위에 열거된 네트워크 포트를 허용하도록 방화벽을 업데이트해야 할 수도 있습니다. 네트워크 포트가 인터넷에 연결되도록 하는 방법에 대한 방화벽 문서를 확인하거나 IT 전문가에 게 도움을 요청합니다.

사용자가 IT 전문가이고 Business Voice를 지원하기 위해 더욱 크거나 복잡한 네트워크를 준비하는 방법에 대한 자세한 정보를 필요로 하는 경우 [사용자 환경 평가](../3-envision-evaluate-my-environment.md)를 참조하세요. [사용자 환경 평가](../3-envision-evaluate-my-environment.md) 문서는 대역폭, 프록시 및 방화벽 요구 사항에 대한 추가 정보를 제공 하고 또한 [네트워크 평가 도구](../3-envision-evaluate-my-environment.md#test-the-network)를 사용하여 네트워크를 테스트하는 방법도 설명합니다.
