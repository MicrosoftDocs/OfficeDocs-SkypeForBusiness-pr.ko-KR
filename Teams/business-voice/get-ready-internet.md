---
title: 인터넷 연결을 확인하여 Teams 전화 시스템
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 인터넷에서 인터넷을 사용할 준비가 되어 Teams 전화 시스템
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b165f540fe3c6280f1c6a7c2b4dec716a1fa611
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053097"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>인터넷 연결을 확인하여 Teams 전화 시스템

Teams 전화 시스템 클라우드를 사용하여 Microsoft Teams 기능을 사용하도록 설정하는 Microsoft 365 기술입니다. 모든 디바이스에서 Microsoft Teams 전화 시스템 인터넷에 연결해야 합니다.

최상의 전화 시스템 환경을 제공하려면 조직에서 한 번만 걸 수 있는 최대 전화 통화 수를 지원할 수 있는 광대역 인터넷 연결이 필요합니다. 또한 네트워크의 컴퓨터가 서비스에 도달할 수 있는지 Microsoft 365 합니다.

## <a name="check-your-internet-connection-speed"></a>인터넷 연결 속도 확인

이 문서는 전화 통화를 해야 하는 사용자 수에 대해 인터넷 연결이 충분히 빠른지 여부를 확인하는 데 도움이 됩니다. 조직에 대한 정보를 제공하고 인터넷 연결의 수를 보여주는 보고서를 Teams 전화 시스템.

### <a name="gather-information-about-your-internet-connection-and-users"></a>인터넷 연결 및 사용자에 대한 정보 수집

시작하기 전에 다음의 정보가 필요합니다.

* 인터넷 연결 속도
* 주로 사무실에서 전화 시스템 사용자 수
* 홈 오피스와 전화 시스템 주로 사용하는 사람 수

### <a name="enter-your-information-into-the-network-planner"></a>네트워크 플래너에 사용자 정보를 입력합니다.

다음 단계를 따릅니다:

1. 브라우저에서 로 이동합니다 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). 전역 관리자 권한이 있는 계정을 사용하여 로그인합니다. 등록하는 데 사용한 계정에는 이러한 Microsoft 365 있습니다.
2. **계획** 을 열고 **네트워크 플래너** 를 선택합니다.
3. **네트워크 플랜** 에서 **추가** 를 선택합니다. 플랜에 이름을 입력하고 **적용** 을 선택합니다.
4. 네트워크 플랜의 이름을 선택합니다.
5. 다음 페이지에서 **네트워크 사이트** 탭의 **네트워크 사이트 추가** 를 선택합니다.
6. 네트워크 사이트 **이름****, 네트워크** 사용자 및 인터넷 링크 용량 필드  를 입력한 다음 저장을 **선택합니다**. 화면의 나머지 항목은 빈 칸으로 두고, **ExpressRoute** 나 **WAN에 연결됨** 옵션은 선택하지 않습니다.
7. **보고서** 탭에서 **보고서 시작** 을 선택합니다.
8. 보고서 이름 및 네트워크 사용자 수(Office 및 원격)를 입력한 다음 보고서 생성을 선택하여 보고서에 대한  대역폭 요구 사항을 Teams.  다음 섹션에서 보고서를 읽는 방법을 설명합니다.

### <a name="find-your-minimum-internet-connection-speed"></a>최소 인터넷 연결 속도 찾기

보고서 생성 **을 선택하면** Microsoft 365 만듭니다.

영향 **열** **및** Office 365 행에서 이 숫자는 인터넷 연결 및 Teams 전화 시스템 보여줍니다. 이 숫자는 총 인터넷 연결 속도의 30%를 넘지 말아야 합니다. 예를 들어 인터넷 연결이 *60Mbps* 인 경우 Teams 전화 시스템 *18Mbps를 사용하지 말아야 합니다*.

이 수식을 사용하여 최소 인터넷 연결 속도(<영향> */0.3)를 확인합니다*.  

영향 수가 *4.6875Mbps라고 하자*. 최소 인터넷 연결 속도를 찾기 위한 계산은 *4.6875 / 0.3 = 15.6입니다*. 이 경우 인터넷 연결 속도는 *15.6Mbps 이상입니다*.

Teams 전화 시스템 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 영향 번호가 빨간색으로 표시됩니다. 이 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.

![연결 속도 경고입니다.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Network Planner에서 제공하는 대역폭 영향은 예상치입니다. 통화 품질 대시보드를 사용하여 [](../cqd-what-is-call-quality-dashboard.md) 조직 내에서 오디오 및 비디오 통화에 대한 사용자 환경을 Microsoft Teams 것이 좋습니다.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>사용자의 네트워크의 컴퓨터 및 장치가 Microsoft 365에 연결될 수 있는지 확인합니다.

전화 시스템 컴퓨터 및 디바이스는 특정 네트워크 포트를 사용하여 Microsoft 365 합니다. 이러한 포트는 기본적으로 디바이스가 네트워크 또는 인터넷을 통해 서로 대화하는 문입니다. 사용자의 방화벽은 네트워크의 장치가 다음의 *아웃바운드* 네트워크 포트를 사용하여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.

* **TCP 포트** 80 및 443
* **UDP 포트** 3478, 3479, 3480 및 3481

방화벽이 이러한 네트워크 포트에서 통신을 허용하는지 여부를 확인할 수 있는 가장 쉬운 [방법은](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) 테스트하려는 사무실 Microsoft 365 네트워크 연결 도구를 사용하여 연결 테스트를 수행하는 것입니다. 테스트를 완료한 후 결과 및 권장 사항을 확인하세요.
