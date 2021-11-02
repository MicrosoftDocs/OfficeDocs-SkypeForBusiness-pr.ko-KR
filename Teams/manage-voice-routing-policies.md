---
title: 직접 라우팅에 대한 호출 라우팅 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 통화 라우팅 정책을 만들고 관리하는 방법을 Microsoft Teams.
ms.openlocfilehash: dec6f19dea1f2a44f1c550bf4ae6b9c4f4dedc77
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634937"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>직접 라우팅에 대한 호출 라우팅 정책 관리

조직에서 직접 라우팅을 배포한 경우 전화 라우팅 정책을 사용하여 사용자가 Teams PSTN(공용 전환 전화 네트워크)에 전화를 걸 수 있도록 허용합니다. [](direct-routing-landing-page.md)

통화 라우팅 정책(음성 라우팅 정책이라고도 하는)은 PSTN 사용 레코드에 대한 컨테이너입니다. 음성 라우팅 정책을 만들고 관리 센터에서 음성 Microsoft Teams 또는 음성을 사용하여 음성 라우팅 정책을  >   Windows PowerShell.

전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 얻습니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다.

사용자에게 음성 라우팅 정책을 할당해도 사용자가 PSTN 통화를 할 수 Teams. 또한 직접 라우팅을 전화 시스템 사용자를 사용하도록 설정하고 다른 구성 단계를 완료해야 합니다. 자세한 내용은 직접 라우팅 구성 [을 참조합니다.](direct-routing-configure.md)

## <a name="create-a-custom-call-routing-policy"></a>사용자 지정 호출 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 라우팅 정책으로 이동한 다음  >   **추가를 클릭합니다.**<br>
    ![관리 센터의 음성 라우팅 정책 추가 Microsoft Teams 스크린샷](media/manage-voice-routing-policies.png) 
2. 정책의 이름과 설명을 입력합니다.
3. **PSTN 사용** 레코드에서 **PSTN** 사용량 추가를 클릭한 다음 추가할 레코드를 선택합니다. 새 PSTN 사용 레코드를 만들어야 하는 경우 추가를 **클릭합니다.**
4. 여러 PSTN 사용 레코드를 추가한 경우 원하는 순서대로 정렬합니다.
5. 완료되면 적용 을 **클릭합니다.**
6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsOnlineVoiceRoutingPolicy 를 참조합니다.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-call-routing-policy"></a>통화 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 라우팅 정책으로  >  **이동하세요.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. **PSTN 사용 레코드 추가/제거를** 클릭하고 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineVoiceRoutingPolicy 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-call-routing-policy-to-users"></a>사용자에게 사용자 지정 호출 라우팅 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsOnlineVoiceRoutingPolicy 를 참조합니다.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 개요](teams-powershell-overview.md)

[직접 라우팅에 대한 호출 라우팅 구성](direct-routing-voice-routing.md)

[직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)