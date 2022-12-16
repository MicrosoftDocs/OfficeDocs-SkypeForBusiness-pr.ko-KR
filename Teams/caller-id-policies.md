---
title: Microsoft Teams에서 발신자 ID 정책 관리
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams에서 발신자 ID 정책을 사용하고 관리하여 조직의 Teams 사용자의 발신자 ID를 변경하거나 차단하는 방법을 알아봅니다.
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414706"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft Teams에서 발신자 ID 정책 관리

기본적으로 Teams 사용자가 PSTN 전화를 걸면 Teams 사용자의 전화 번호가 표시됩니다. 마찬가지로 PSTN 발신자가 Teams 사용자에게 전화를 걸면 PSTN 발신자의 전화 번호가 표시됩니다.

관리자는 호출자 ID 정책을 사용하여 호출자 ID(호출 회선 ID라고도 함)를 변경하거나 차단할 수 있습니다. 발신자 ID 정책을 사용하여 조직의 Teams 사용자에 대한 대체 전화 번호를 표시하거나, 아웃바운드 전화 번호를 차단하거나, 수신 번호가 표시되지 않도록 차단하거나, CNAM(통화 당사자 이름)을 설정할 수 있습니다. 예를 들어 사용자가 전화를 걸 때 발신자 ID를 변경하여 사용자의 전화 번호 대신 조직의 기본 전화 번호와 회사 이름을 표시할 수 있습니다.

Microsoft Teams 관리 센터에서 **음성** > **발신자 ID 정책으로 이동하여 발신자 ID 정책을** 관리합니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.

## <a name="create-a-custom-caller-id-policy"></a>사용자 지정 호출자 ID 정책 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **발신자 ID 정책** 으로 이동합니다.
2. **추가** 를 클릭합니다. <br>
![관리 센터의 새 호출자 ID 정책 페이지의 스크린샷](media/caller-id-policies-add-policy.png)
3. 정책의 이름과 설명을 입력합니다.
4. 여기에서 원하는 설정을 선택합니다.

    - **들어오는 호출자 ID 차단**: 들어오는 호출의 호출자 ID가 표시되지 않도록 하려면 이 설정을 켭니다.
    - **호출자 ID 정책 재정의**: 이 설정을 켜면 사용자가 호출자에게 번호를 표시하는 것과 관련된 정책의 설정을 재정의할 수 있습니다. 즉, 사용자는 호출자 ID를 표시할지 여부를 선택할 수 있습니다. 자세한 내용은 [아웃바운드 호출자 ID의 최종 사용자 제어를 참조하세요](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).
    - **호출자 ID를 로 바꿉** 니다. 다음 중 하나를 선택하여 사용자에게 표시할 호출자 ID를 설정합니다.

        - **사용자 번호**: 사용자의 번호를 표시합니다. 
        - **서비스 번호**: 호출자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.
        - **익명**: 호출자 ID를 익명으로 표시합니다.

    - **호출자 ID를 이 서비스 번호로 바꿉** 니다. 사용자의 호출자 ID를 바꿀 서비스 번호를 선택합니다. 호출 **자 ID** 바꾸기에서 **서비스 번호를** 선택한 경우 이 옵션을 사용할 수 있습니다.

5. **저장** 을 클릭합니다.

## <a name="edit-a-caller-id-policy"></a>호출자 ID 정책 편집

전역 정책 또는 사용자가 만든 사용자 지정 정책을 편집할 수 있습니다. 

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **발신자 ID 정책** 으로 이동합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 설정을 변경한 다음 **저장** 을 클릭합니다.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>사용자에게 사용자 지정 발신자 ID 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>관련 주제

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
