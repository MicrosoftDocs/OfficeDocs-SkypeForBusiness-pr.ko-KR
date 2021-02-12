---
title: Microsoft Teams에서 발신자 ID 정책 관리
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
description: Microsoft Teams에서 발신자 ID 정책을 사용하여 조직의 Teams 사용자의 발신자 ID를 변경하거나 차단하는 방법을 배워야 합니다.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255531"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft Teams에서 발신자 ID 정책 관리

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

관리자는 Microsoft Teams에서 발신자 ID 정책을 사용하여 발신자 ID(호출 라인 ID라고도 하는 호출자 ID)를 변경하거나 차단할 수 있습니다. 기본적으로 Teams 사용자의 전화 번호는 사용자가 PSTN 전화로 전화를 걸 때 볼 수 있으며, Teams 사용자로 전화를 걸 때 PSTN 발신자 전화 번호를 볼 수 있습니다. 발신자 ID 정책을 사용하여 조직의 Teams 사용자의 대체 전화 번호를 표시하거나 들어오는 번호가 표시되지 못하게 차단할 수 있습니다.

예를 들어 사용자가 전화를 걸 때 발신자 ID를 변경하여 사용자의 전화 번호 대신 조직의 기본 전화 번호를 표시할 수 있습니다.

Microsoft Teams 관리 센터에서 **음성** 발신자 ID 정책으로 진행하여 발신자 ID 정책을  >   관리합니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.

## <a name="create-a-custom-caller-id-policy"></a>사용자 지정 호출자 ID 정책 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 발신자  >  **ID 정책으로 이동하세요.**
2. **추가** 를 클릭합니다. <br>
![관리 센터의 새 발신자 ID 정책 페이지의 스크린샷](media/caller-id-policies-add-policy.png)
3. 정책의 이름과 설명을 입력합니다.
4. 여기에서 원하는 설정을 선택합니다.

    - **수신 발신자 ID** 차단: 수신 호출의 발신자 ID가 표시되지 못하게 차단하기 위해 이 설정을 켜야 합니다.
    - **호출자 ID** 정책 다시 적용: 사용자가 발신자 번호 표시와 관련하여 정책의 설정을 다시 설정할 수 있도록 이 설정을 켜야 합니다. 즉, 사용자가 발신자 ID를 표시할지 여부를 선택할 수 있습니다. 자세한 내용은 아웃바운드 호출자 ID의 최종 [사용자 제어를 참조하세요.](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)
    - **호출자 ID를**: 다음 중 하나를 선택하여 사용자에게 표시될 호출자 ID를 설정합니다.

        - **사용자 번호:** 사용자의 번호를 표시합니다. 
        - **서비스 번호:** 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.
        - **익명:** 호출자 ID를 익명으로 표시됩니다.

    - **호출자 ID를** 이 서비스 번호로 바꾸기: 사용자의 호출자 ID를 바꿀 서비스 번호를 선택 합니다. 호출자 ID를 으로 바꾸기에서 서비스 번호를 선택한 경우 이 **옵션을 사용할 수 있습니다.** 

5. **저장** 을 클릭합니다.

## <a name="edit-a-caller-id-policy"></a>호출자 ID 정책 편집

전역 정책 또는 만드는 모든 사용자 지정 정책을 편집할 수 있습니다. 

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 발신자  >  **ID 정책으로 이동하세요.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 설정을 변경한 다음 저장을 **클릭합니다.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>사용자에게 사용자 지정 호출자 ID 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>관련 항목

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
