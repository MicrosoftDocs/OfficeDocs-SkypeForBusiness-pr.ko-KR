---
title: Business Voice에 대한 인터넷 연결 확인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 473c053036b766ef475c3aed5f0bba2d24dd9e6c
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824886"
---
# <a name="check-your-internet-connection-for-business-voice"></a>Business Voice에 대한 인터넷 연결 확인

Business Voice는 Microsoft 365에서 클라우드에 있습니다. Microsoft Teams 및 Business Voice를 사용하는 모든 장치는 인터넷 연결을 필요로 합니다.

최적의 Business Voice 환경을 위해 어느 특정 시간에 조직에서 사용할 수 있는 최대 전화 통화의 수를 지원할 수 있도록 광대역 인터넷 연결이 필요합니다. 또한 사용자의 네트워크의 컴퓨터가 Microsoft 365 서버에 연결할 수 있는지 확인해야 합니다.

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

이 문서는 사용자의 인터넷 연결이 전화를 걸고 화상 회의를 호스팅해야 하는 사용자의 수를 수용하기에 충분히 빠른지를 확인하는 데 도움을 줍니다. 사용자는 조직에 대한 정보를 제공하고 Teams 및 Business Voice로 인해 사용될 인터넷 연결의 용량을 보여주는 보고서를 받을 수 있습니다.

### <a name="gather-information-about-your-internet-connection-and-users"></a>인터넷 연결 및 사용자에 대한 정보 수집

시작하기 전에 다음의 정보가 필요합니다.

* 인터넷 연결 속도.
* 사무실에서 Business Voice를 주로 사용하는 사용자의 수
* 홈 사무실과 같이 주로 원격 위치에서 Business Voice를 사용하는 사용자의 수

### <a name="enter-your-information-into-the-network-planner"></a>네트워크 플래너에 사용자 정보를 입력합니다.

다음 단계를 따릅니다:

1. 브라우저에서 https://admin.teams.microsoft.com로 이동합니다. 전역 관리자 권한이 있는 계정을 사용하여 로그인합니다. Office 365에 등록하기 위해 사용한 계정에는 이러한 사용 권한이 있습니다.
2. **계획**을 열고 **네트워크 플래너**를 선택합니다.
3. **네트워크 플랜**에서 **추가**를 선택합니다. 플랜에 이름을 입력하고 **적용**을 선택합니다. 네트워크 플랜은 다음과 같이 보여야 합니다.

    ![네트워크 플래너의 메인 화면](../media/network-planner-main.png)
1. 네트워크 플랜의 이름을 선택합니다. (이전 그림에서 **기본 office**입니다.)
2. 다음 페이지에서 **네트워크 사이트**탭의 **네트워크 사이트 추가**를 선택합니다.
3. 다음의 스크린샷에 표시된 항목만 입력하고 **저장**을 선택합니다. 화면의 나머지 항목은 빈 칸으로 두고, **ExpressRoute**나 **WAN에 연결됨** 옵션은 선택하지 않습니다.

    ![네트워크 플래너 사이트 정보](../media/network-planner-site-info.png)
1. **보고서** 탭에서 **보고서 시작**을 선택합니다.
1. 다음 정보를 입력하고 **보고서 생성**을 선택하면 Teams에서 필요한 대역폭을 보여주는 보고서가 생성됩니다. 다음 항목에서 보고서를 보는 방법을 설명합니다.

    ![네트워크 플래너 보고서 정보](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>최소 인터넷 연결 속도를 확인합니다

**보고서 작성**을 선택 시 Office 365에서 다음과 같이 표시되는 보고서를 만듭니다.

![네트워크 플래너 보고서의 세부 정보](../media/network-planner-report.png)

강조 표시된 숫자는 Teams와 Business Voice가 사용할 인터넷 연결의 용량을 보여줍니다. 이 숫자가 총 인터넷 연결 속도의 30%를 넘지 않는 것이 좋습니다. 예를 들어 인터넷 연결 속도가 60Mbps인 경우 Teams 및 Business Voice는 18Mbps 이상을 사용하지 않아야 합니다.

다음 수식을 사용하여 최소 인터넷 연결 속도를 확인합니다. *\<강조 표시된 숫자>/0.3*. 이전 이미지에서 강조 표시된 번호를 사용하면 계산은 *4.6875/0.3 = 15.6*이 됩니다. 이 경우 인터넷 연결 속도는 적어도 15.6Mbps이어야 합니다.

Teams 및 Business Voice에서 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 강조 표시된 숫자가 빨간색으로 표시됩니다. 이 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.

![연결 속도 경고](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>사용자의 네트워크의 컴퓨터 및 장치가 Microsoft 365에 연결될 수 있는지 확인합니다.

Business Voice를 사용하는 컴퓨터 및 장치는 특정 네트워크 포트를 사용하여 Microsoft 365 서버와 통신해야 합니다. 이러한 포트는 기본적으로 네트워크 또는 인터넷을 통해 모든 장치가 서로 통신할 수 있는 문입니다. 사용자의 방화벽은 네트워크의 장치가 다음의 *아웃바운드* 네트워크 포트를 사용하여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.

* **TCP 포트** 80 및 443
* **UDP 포트** 3478, 3479, 3480 및 3481

사용자의 방화벽이 이러한 네트워크 포트에서의 통신을 허용하는지를 확인하는 가장 쉬운 방법은 Teams에서 테스트 통화를 해보는 것입니다.

1. 사용자의 네트워크의 컴퓨터에서 https://aka.ms/getteams로 이동하여 Teams를 설치합니다. 컴퓨터에 스피커와 마이크가 있는지 확인합니다.
2. Teams를 열고 Microsoft 365 계정을 사용하여 로그인합니다.
3. Teams에서 프로필 사진을 선택하고 **설정** > **장치**로 이동합니다.
4. **오디오 장치**에서 **테스트 통화**를 선택합니다.
5. 단계를 따라 메시지를 남기고 사용자에게 다시 재생되도록 합니다.

   * 통화가 연결되고 메시지가 들린다면 방화벽이 제대로 설정된 것입니다.
   * 통화가 연결되지만 안내 음성이나 메시지가 들리지 않으면 스피커 및 마이크가 컴퓨터에서 제대로 설정되었는지 확인하고 다시 시도합니다.
   * 통화가 연결되지 않거나 연결되지만 메시지가 들리지 않으면 필요한 네트워크 포트에 액세스를 허용하도록 방화벽을 업데이트해야 할 수도 있습니다. 방화벽 설명서를 확인하거나 IT 전문가에게 도움을 요청하세요.

 사용자가 IT 전문가이고 Business Voice를 지원하기 위해 더욱 크거나 복잡한 네트워크를 준비하는 방법에 대한 자세한 정보를 필요로 하는 경우 [사용자 환경 평가](../3-envision-evaluate-my-environment.md)를 참조하세요. 이 문서는 대역폭, 프록시 및 방화벽 요구 사항에 정보를 제공하고 또한 [네트워크 평가 도구](../3-envision-evaluate-my-environment.md#test-the-network)를 사용하여 네트워크를 테스트하는 방법도 제공합니다.

