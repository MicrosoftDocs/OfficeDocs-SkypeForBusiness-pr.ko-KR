---
title: Teams 전화 시스템에 대한 인터넷 연결 확인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 전화 시스템에 대한 인터넷이 준비되어 있는지 확인합니다.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 5cbc8613a91e2b776faff922fb9a3a98b3dd545e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271053"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Teams 전화 시스템에 대한 인터넷 연결 확인

Teams Phone System은 Microsoft 365 클라우드를 사용하여 Microsoft Teams 내에서 전화 기능을 사용하도록 설정하는 Microsoft의 기술입니다. Microsoft Teams 및 전화 시스템을 사용하는 모든 디바이스는 인터넷에 연결해야 합니다.

최상의 전화 시스템 환경을 얻으려면 조직에서 한 번에 수행할 수 있는 최대 전화 통화 수를 지원할 수 있는 광대역 인터넷 연결이 필요합니다. 또한 네트워크의 컴퓨터가 Microsoft 365 서비스에 연결할 수 있는지 확인해야 합니다.

## <a name="check-your-internet-connection-speed"></a>인터넷 연결 속도 확인

이 문서는 전화 통화를 해야 하는 사람들의 수에 맞게 인터넷 연결이 충분히 빠른지 여부를 결정하는 데 도움이 됩니다. 조직에 대한 정보를 제공하고 Teams 및 전화 시스템에서 사용할 인터넷 연결의 양을 보여 주는 보고서를 다시 가져옵니다.

### <a name="gather-information-about-your-internet-connection-and-users"></a>인터넷 연결 및 사용자에 대한 정보 수집

시작하기 전에 다음의 정보가 필요합니다.

* 인터넷 연결 속도
* 주로 사무실에서 전화 시스템을 사용하는 사용자 수
* 주로 홈 오피스와 같은 원격 위치에서 전화 시스템을 사용하는 사용자 수

### <a name="enter-your-information-into-the-network-planner"></a>네트워크 플래너에 사용자 정보를 입력합니다.

다음 단계를 따릅니다:

1. 브라우저 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com)에서 . 전역 관리자 권한이 있는 계정을 사용하여 로그인합니다. Microsoft 365에 등록하는 데 사용한 계정에는 이러한 권한이 있습니다.
2. **계획** 을 열고 **네트워크 플래너** 를 선택합니다.
3. **네트워크 플랜** 에서 **추가** 를 선택합니다. 플랜에 이름을 입력하고 **적용** 을 선택합니다.
4. 네트워크 플랜의 이름을 선택합니다.
5. 다음 페이지에서 **네트워크 사이트** 탭의 **네트워크 사이트 추가** 를 선택합니다.
6. **네트워크 사이트 이름**, **네트워크 사용자** 및 **인터넷 링크 용량** 필드를 입력한 다음 **저장** 을 선택합니다. 화면의 나머지 항목은 빈 칸으로 두고, **ExpressRoute** 나 **WAN에 연결됨** 옵션은 선택하지 않습니다.
7. **보고서** 탭에서 **보고서 시작** 을 선택합니다.
8. **보고서 이름** 및 **네트워크 사용자** 수(**Office** 및 **원격**)를 입력한 다음 **보고서 생성** 을 선택하여 Teams의 대역폭 요구 사항을 보여 주는 보고서를 만듭니다. 다음 섹션에서 보고서를 읽는 방법을 알려드립니다.

### <a name="find-your-minimum-internet-connection-speed"></a>최소 인터넷 연결 속도 찾기

**보고서 생성** 을 선택하면 Microsoft 365에서 보고서가 만들어집니다.

**[영향**] 열과 **Office 365** 행에서 이 번호는 Teams 및 Phone System에서 사용할 인터넷 연결의 양을 보여 제공합니다. 이 숫자는 전체 인터넷 연결 속도의 30%를 넘지 않는 것이 좋습니다. 예를 들어 인터넷 연결이 *60Mbps* 인 경우 Teams 및 전화 시스템은 *18Mbps* 이하를 사용해야 합니다.

<*영향 번호>/0.3* 의 최소 인터넷 연결 속도를 확인하려면 이 수식을 사용합니다.  

영향 번호가 *4.6875Mbps* 라고 가정해 보겠습니다. 최소 인터넷 연결 속도를 찾기 위한 계산은 *4.6875/0.3 = 15.6* 입니다. 이 경우 인터넷 연결 속도는 *15.6Mbps* 이상이어야 합니다.

Teams 및 전화 시스템이 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 **영향** 번호가 빨간색으로 표시됩니다. 이 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.

![연결 속도 경고입니다.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Network Planner에서 제공하는 대역폭 영향은 예상치에 불과합니다. [통화 품질 대시보드](../cqd-what-is-call-quality-dashboard.md)를 사용하여 조직 내에서 Microsoft Teams와의 오디오 및 영상 통화에 대한 사용자 환경을 적극적으로 모니터링하는 것이 좋습니다.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>사용자의 네트워크의 컴퓨터 및 장치가 Microsoft 365에 연결될 수 있는지 확인합니다.

전화 시스템을 사용하는 컴퓨터 및 디바이스는 특정 네트워크 포트를 사용하여 Microsoft 365 서비스와 통신해야 합니다. 이러한 포트는 기본적으로 디바이스가 네트워크 또는 인터넷을 통해 서로 통신하는 문입니다. 사용자의 방화벽은 네트워크의 장치가 다음의 *아웃바운드* 네트워크 포트를 사용하여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.

* **TCP 포트** 80 및 443
* **UDP 포트** 3478, 3479, 3480 및 3481

방화벽이 이러한 네트워크 포트에서 통신을 허용하는지 여부를 확인하는 가장 쉬운 방법은 테스트하려는 사무실 위치에서 [Microsoft 365 네트워크 연결 도구를 사용하여 연결](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) 테스트를 수행하는 것입니다. 테스트를 완료한 후 결과 및 권장 사항을 확인합니다.
