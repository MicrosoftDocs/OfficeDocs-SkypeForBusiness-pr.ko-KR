---
title: Microsoft 팀의 발신자 ID 정책 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 발신자 ID 정책을 사용 하 고 관리 하 여 조직에서 팀 사용자의 발신자 ID를 변경 하거나 차단 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255531"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft 팀의 발신자 ID 정책 관리

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

관리자는 Microsoft 팀의 발신자 ID 정책을 사용 하 여 발신자 ID (전화 라인 ID 라고도 함)를 변경 하거나 차단할 수 있습니다. 기본적으로 팀 사용자는 PSTN 휴대폰으로 전화를 걸거나 PSTN 발신자의 전화 번호를 볼 수 있으며,이 경우 팀에 게 전화를 걸 때 볼 수 있습니다. 발신자 ID 정책을 사용 하 여 조직의 팀 사용자에 대 한 대체 전화 번호를 표시 하거나 수신 번호를 표시 되지 않도록 차단할 수 있습니다.

예를 들어 사용자가 전화를 거는 경우 발신자 ID를 변경 하 여 사용자의 전화 번호 대신 조직의 기본 전화 번호를 표시할 수 있습니다.

**Voice**  >  Microsoft 팀 관리 센터에서 음성**발신자 id 정책** 으로 이동해 서 발신자 id 정책을 관리할 수 있습니다. 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.

## <a name="create-a-custom-caller-id-policy"></a>사용자 지정 발신자 ID 정책 만들기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **발신자 ID 정책**으로 이동 합니다.
2. **추가**를 클릭 합니다. <br>
![관리 센터의 새 발신자 ID 정책 페이지 스크린샷](media/caller-id-policies-add-policy.png)
3. 정책의 이름과 설명을 입력합니다.
4. 여기에서 원하는 설정을 선택 합니다.

    - **들어오는 발신자 Id 차단**:이 설정을 사용 하면 들어오는 전화의 발신자 id가 표시 되지 않도록 차단할 수 있습니다.
    - **발신자 ID 정책 재정의**: 사용자가 번호를 피호출자에 표시 하는 것과 관련 하 여 정책의 설정을 재정의할 수 있도록 하려면이 설정을 사용 합니다. 즉, 사용자가 자신의 발신자 ID를 표시할지 여부를 선택할 수 있습니다. 자세한 내용은 [아웃 바운드 발신자 ID의 최종 사용자 제어](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)를 참조 하세요.
    - **발신자 id를 다음으로 바꿉니다**: 다음 중 하나를 선택 하 여 사용자에 게 표시할 발신자 id를 설정 합니다.

        - **사용자의 번호**: 사용자의 번호를 표시 합니다. 
        - **서비스 번호**: 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.
        - **익명**: 발신자 ID를 익명으로 표시 합니다.

    - **발신자 id를 다음 서비스 번호로 바꾸기**: 사용자의 발신자 id를 바꿀 서비스 번호를 선택 합니다. 이 옵션은 **발신자 ID를 (으)로 바꾸기**에서 **서비스 번호** 를 선택한 경우에만 사용할 수 있습니다.

5. **저장**을 클릭합니다.

## <a name="edit-a-caller-id-policy"></a>발신자 ID 정책 편집

만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다. 

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **발신자 ID 정책**으로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 원하는 설정을 변경한 다음 **저장**을 클릭 합니다.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>사용자에 게 사용자 지정 발신자 ID 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>관련 항목

[새로운 CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[팀에서 사용자에 게 정책 할당](assign-policies.md)
