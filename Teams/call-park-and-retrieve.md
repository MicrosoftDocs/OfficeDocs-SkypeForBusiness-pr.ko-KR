---
title: 통화 공원 및 Microsoft 팀에서 검색
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 통화 대기를 사용 하 고 Microsoft 팀에서 통화를 진행 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424596"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>통화 공원 및 Microsoft 팀에서 검색

통화 공원 및 검색은 사용자가 통화를 대기 상태로 설정할 수 있는 기능입니다. 통화가 파킹 되 면 서비스에서 호출 검색에 대 한 고유 코드를 생성 합니다. 통화를 대기 하거나 다른 사용자가 해당 코드를 지원 되는 앱 또는 장치와 함께 사용 하 여 통화를 검색할 수 있습니다. 자세한 내용은 [팀에서 통화 대기의 파킹을](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 참조 하세요.

통화 공원 사용에 대 한 일반적인 시나리오는 다음과 같습니다.

- Receptionist는 공장에서 작업 하는 사람에 게 전화를 공원 합니다. 그런 다음 receptionist는 공용 주소 시스템을 통해 통화와 코드 번호를 알립니다. 전화를 받은 사용자는 공장 바닥에서 팀 전화를 선택 하 고 통화를 검색 하는 코드를 입력할 수 있습니다.
- 디바이스 배터리의 전원이 부족 하 여 모바일 장치에서 통화를 공원. 그러면 사용자는 팀의 일반 전화기에서 통화를 검색 하는 코드를 입력할 수 있습니다.
- 지원 담당자는 고객에 게 전화를 걸고 전문가를 위해 팀 채널에 알림을 보내 고객에 게 도움을 줍니다. 전문가는 전화를 검색 하기 위해 팀 클라이언트에 코드를 입력 합니다.

통화를 대기 하 고 검색 하려면 사용자가 엔터프라이즈 음성 사용자 여야 하며 통화 대기 정책에 포함 되어야 합니다.

> [!NOTE]
> 통화 공원 및 검색은 [팀 전용 배포 모드](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 에서만 사용할 수 있으며 비즈니스용 Skype IP 전화에서는 지원 되지 않습니다.

## <a name="configure-call-park-and-retrieve"></a>통화 공원 구성 및 검색

통화 공원 및 검색을 구성 하려면 팀 관리자 여야 합니다. 이 기능은 기본적으로 비활성화 되어 있습니다. 사용자에 대해이 기능을 사용 하도록 설정 하 고 통화 공원 정책을 사용 하 여 사용자 그룹을 만들 수 있습니다. 사용자 집합에 같은 정책을 적용 하는 경우에는 서로 간에 전화를 걸고 검색할 수 있습니다.

통화 공원 정책을 사용 하도록 설정 하려면

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 공원 정책**으로 이동 합니다.
2. **정책 관리** 탭에서 **추가**를 클릭 합니다.
3. 정책 이름을 지정한 다음 **통화 대기 허용** 을 **설정**으로 전환 합니다.

    ![통화 공원 정책 설정 스크린샷](media/call-park-add-policy.png)

4. **저장**을 선택 합니다.

목록에서 정책을 선택 하 고 **편집**을 클릭 하 여 편집할 수 있습니다.

정책이 작동 하려면 사용자에 게 할당 되어야 합니다. [정책을 사용자에 게 개별적으로 할당](assign-policies.md) 하거나 그룹에 할당할 수 있습니다.

전화 파트 정책을 그룹에 할당 하려면

1. **통화 공원 정책** 페이지의 **그룹 정책 할당** 탭에서 **그룹 추가**를 클릭 합니다.
2. 사용할 그룹을 검색 한 다음 **추가**를 클릭 합니다.
3. 다른 그룹 배정과 비교한 순위를 선택 합니다.
4. **정책 선택**에서이 그룹에 할당할 정책을 선택 합니다.

    ![](media/call-park-assign-policy-to-group.png)

5. **적용**을 클릭 합니다.

## <a name="related-topics"></a>관련 항목

[팀에서 통화 대기](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[팀에서 사용자에 게 정책 할당](assign-policies.md)

[새로운 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[부여-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)