---
title: Microsoft Teams 패널
ms.author: serdars
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: 이 문서에서는 패널에서 지원되는 기능과 Microsoft Teams 제공합니다.
ms.openlocfilehash: b860b141cddddbb90ce9d28d7895cf385c77c0ff
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514743"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams 패널

Microsoft Teams 패널은 모임 공간 바로 바깥에 설치되는 소형 터치 스크린 디바이스이며, 일반적으로 입구 옆에 있습니다. Teams 패널을 통해 위치 및 모임 세부 정보를 한눈에 보고 현장에서 사용 가능한 모임 공간을 예약할 수 있습니다. 풍부하고 큰 텍스트 및 색으로 코딩된 표시기를 사용하면 멀리서 모임 공간의 가용성을 볼 수 있습니다.

Teams 패널은 Microsoft Teams 또는 365 일정 애플리케이션을 통해 예약된 모임 Teams Outlook 전용 디바이스입니다. 모임 세부 정보가 두드러진 경우 참석자들은 올바른 모임 공간에 있는지, 올바른 모임에 적합한지 확인할 수 있습니다.

이 문서에서는 Teams 패널에 대한 개요를 제공하며 조직의 패널 디바이스를 Teams 수 있습니다.

## <a name="features-supported-by-teams-panels"></a>패널에서 Teams 기능

Teams 패널은 다음 기능을 지원합니다.

- **모임 공간 및 모임 세부 정보를 전용으로 표시합니다.** 모임 공간에 대한 위치 및 가용성을 포함하여 한눈에 정보를 얻을 수 있습니다. 예약된 모임 공간의 경우 모임 제목, 모임 일정 및 모임 이끌이와 같은 주요 모임 세부 정보를 볼 수 있습니다.
- **비정기 모임에 사용할 수 있는 모임 공간을 예약합니다.** 터치 스크린 패널을 사용하여 자리에서 사용 가능한 모임 공간을 예약하고 회의실 또는 Teams 모임에 참가할 Microsoft Teams 룸 Surface Hub 있습니다.
- **공간 가용성 상태에 대한 색으로 코딩된 표시기입니다.** 활기찬 LED 및 홈 화면 표시기를 사용하여 1년 가까이에서 모임 공간 가용성을 볼 수 있습니다. 녹색은 모임 공간을 사용할 수 있으며, 필요한 경우 패널 자체에서 바로 예약할 수 있습니다. 빨간색 또는 보라색은 모임 공간이 예약되어 있는 경우를 나타냅니다.
- **배경 화면 및 예약 상태 표시기를 사용자 지정합니다.** 관리자는 설정을 통해 패널의 기본 모양을 변경할 수 있습니다. 예를 들어 관리자는 배경 배경 화면을 변경하거나 사용 중 상태 표시기 색을 변경할 수 있습니다.
- **접근성.** Teams 패널에는 명암비 텍스트와 같은 여러 접근성 기능이 제공되어 누구나 쉽게 사용할 수 있습니다.

이러한 기능 및 해당 기능을 사용하는 방법에 대한 자세한 내용은 패널 사용 Microsoft Teams [참조합니다](use-teams-panels.md).

## <a name="partners-certified-for-teams-panels"></a>패널에 대해 Teams 파트너

패널에 대해 인증된 파트너에 대한 Teams 자세한 내용은 현재 인증된 Teams [참조하세요](teams-ip-phones.md#certified-teams-panels).

## <a name="teams-panels-requirements"></a>Teams 패널 요구 사항

패널 디바이스를 배포하기 위한 하드웨어, 소프트웨어 및 네트워크 요구 사항은 배포할 패널 디바이스 유형에 따라 다를 수 있습니다. 디바이스 집합에 필요한 것을 알고자 하는 OEM(원래 장비 제조업체) 설명서를 참조하세요.

## <a name="license-requirement"></a>라이선스 요구 사항

패널을 Teams 사용하려면 라이선스가 [Microsoft Teams 룸 스탠더드 필요합니다](../rooms/rooms-licensing.md).

> [!Note]
> 이미 Microsoft Teams 룸 패널을 설치하는 모임 공간에 배포된 Teams 패널을 사용하기 위한 추가 라이선스가 Teams 없습니다.

## <a name="deploy-teams-panels-devices"></a>Teams 디바이스 배포

패널 디바이스를 계획, 배포 및 Teams 관련이 있는 경우 이 섹션을 참조하세요. 이 섹션은 패널의 최종 사용자를 위한 Teams 없습니다.

패널 Teams 배포는 다음 작업으로 세분화할 수 있습니다.

- [모임 공간 인](#inventory-sites-and-meeting-spaces)벤토리 및 기능 계획: 조직의 사이트 및 모임 공간의 인벤토리를 만들어 패널 Teams 있습니다.
- [조달](#procurement): 선택한 디바이스 파트너에서 디바이스를 조달합니다.  
- [사이트 준비](#site-readiness): 배포 위치(모임 공간)가 배포 요구 사항을 충족하는지 확인합니다.
- [구성 및 배포](#configuration-and-deployment): 리소스 계정을 만들고 디바이스에 할당합니다.

## <a name="inventory-sites-and-meeting-spaces"></a>인벤토리 사이트 및 모임 공간

조직의 기존 예약 가능한 모임 공간의 인벤토리를 찍습니다. 패널을 배포하기 위한 범위에 있는 사이트 및 모임 Teams 식별합니다. 시설 및 시청각 팀과 함께 패널 디바이스를 설치하는 위치와 Teams 및 패널을 탑재하기 위한 추가 하드웨어가 필요한지 여부를 파악합니다.

## <a name="procurement"></a>조달

패널을 배포하기 위한 범위에 있는 모임 공간의 Teams 패널에 대해 인증된 파트너 [중 Teams.](#partners-certified-for-teams-panels) 디바이스 및 조달 옵션에 대한 자세한 내용은 파트너의 웹 사이트를 방문하세요.

조직의 모임 공간에는 디바이스를 설치하거나 탑재하기 위한 하드웨어 요구 사항이 다를 수 있습니다. 예를 들어 장치를 유리, 석고, 건식 벽체 또는 나무 패널에 탑재하는 데 필요한 하드웨어는 같지 않을 수 있습니다. 사용 가능한 탑재 옵션은 디바이스 파트너의 설명서를 참조하세요.

## <a name="site-readiness"></a>사이트 준비

주문된 디바이스가 조직에 전달되는 동안 네트워킹, 시설 및 시청각 팀과 함께 작업하여 배포 요구 사항을 충족하고 각 사이트 및 모임 공간이 전원 및 네트워킹 측면에서 준비되어 있는지 확인합니다.

패널 사이트에 대한 Teams 권장 사항은:

- 전용 리소스 계정
- 전원 공급 장치(패널은 일반적으로 전원을 위한 이더넷 및 PoE+)를 지원합니다. 디바이스별 전원 요구 사항에 대한 OEM 설명서를 참조하세요.)


물리적 설치 고려 사항은 OEM 설명서를 참조하고, 디바이스를 설치하고 탑재하고 케이블을 실행하기 전에 시청각 팀의 환경을 사용하세요.

## <a name="configuration-and-deployment"></a>구성 및 배포

구성 및 배포 계획은 다음 주요 영역을 다를 수 있습니다.

- 리소스 계정 프로비전
- 테스트

### <a name="resource-account-provisioning"></a>리소스 계정 프로비전

모든 Teams 디바이스에는 Microsoft 365 리소스 계정이 필요합니다. 리소스 계정 자격 증명을 사용하여 패널 디바이스에서 앱을 Microsoft Teams 로그인합니다.

패널에 대한 Microsoft 365 리소스 계정을 Teams 라이선스를 구입하는 [Microsoft Teams 룸 스탠더드 좋습니다](#license-requirement). 리소스 계정을 만들고 라이선스를 할당하는 방법에 대한 자세한 내용은 회의실 및 공유 디바이스에 대한 리소스 [계정 만들기를 Teams.](../rooms/with-office-365.md)

> [!NOTE]
>
>- 패널을 설치하는 모임 공간에 대해 회의실 리소스 계정이 이미 설정되어 있는 경우 동일한 회의실 리소스 계정을 사용하여 패널 디바이스에 로그인합니다. 그러나 패널 리소스 계정으로 사용하기 위해 룸 리소스 계정에 할당된 Microsoft Teams 룸 스탠더드 라이선스가 있는지 확인하세요.
>
>- 패널을 Microsoft Teams 룸 모임 공간에 이미 배포된 Teams 패널을 배포하기 위한 별도의 라이선스를 구입할 필요가 없습니다. 관리자는 동일한 공간에 대한 자격 증명과 동일한 자격 증명을 Microsoft Teams 룸 디바이스에 로그인합니다.
>
>- 여러 개의 입구가 있는 회의실 또는 회의실과 같은 대규모 모임 공간의 경우 각 입구에 하나의 패널 디바이스를 탑재할 수 있습니다. 단일 모임 공간에 속하는 여러 패널은 동일한 리소스 계정을 공유하고 동일한 자격 증명으로 로그인합니다. 동일한 공간에 대해 각 패널에 대해 별도의 리소스 계정을 만들 필요가 없습니다.

> [!TIP]
> 실제 패널 설치에 앞서 리소스 계정을 Teams 것이 좋습니다.
> 패널 리소스 계정에 이름 Teams 사용하는 것이 고려됩니다. 리소스 계정에 대한 표시 이름을 Microsoft 365 설명하고 쉽게 이해할 수 있도록 합니다. 이러한 이름은 사용자가 모임 공간을 검색하는 동안 일정 또는 일정에서 모임을 Outlook Teams 이름입니다.

### <a name="testing"></a>테스트

패널을 배포한 후 테스트해야 합니다. 배포된 디바이스 [](#features-supported-by-teams-panels) 에서 지원되는 Teams 패널이 작동하고 있는지 확인합니다. 컴퓨터에서 365 또는 365를 통해 다양한 시간 슬롯에 Teams Outlook 여러 모임을 만들어  시도합니다. 패널이 예약된 모임에 대한 모임 세부 정보 및 가용성을 올바르게 표시하는지 확인합니다. 예약 단추 **를** 사용하여 디바이스에서 직접 사용 가능한 모임 공간을 예약할 수 있는지 확인합니다.

## <a name="manage-teams-panels-in-your-organization"></a>조직의 Teams 패널 관리

Teams 디바이스를 관리하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **DevicesPanels** > 로 Teams 이동하세요. 여기에서 디바이스 구성 프로필을 변경하고, 업데이트를 관리하고, 디바이스를 다시 시작하고, 디바이스 태그를 추가 및 제거할 수 있습니다. 자세한 내용은 에서 디바이스 [관리를](device-management.md) Teams.

## <a name="next-steps"></a>다음 단계

[패널 디바이스를 Microsoft Teams 방법](use-teams-panels.md)

## <a name="see-also"></a>참고 항목

[Microsoft Teams 패널에 Teams 블로그](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[패널 시작 Teams 시작](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teams 패널 마켓플레이스](https://office.com/teamsdevices)

[패널 인증 Microsoft Teams 인증된 디바이스](teams-ip-phones.md#certified-teams-panels)
