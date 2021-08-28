---
title: 직접 라우팅에 대한 긴급 음성 라우팅 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 긴급 전화가 라우팅되는 방법을 지정하기 위해 Microsoft Teams 음성 라우팅 정책을 사용 및 관리하는 방법에 대해 자세히 알아보고 있습니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 5f6d3f45c2a3a97980bec3eb17ee1f6b35952fe5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619444"
---
# <a name="manage-emergency-voice-routing-policies-for-direct-routing"></a>직접 라우팅에 대한 긴급 음성 라우팅 정책 관리

조직에서 직접 라우팅을 전화 시스템 경우 해당 조직에서 긴급 음성 라우팅 정책을 사용하여 Microsoft Teams 긴급 번호를 설정하고 긴급 통화가 라우팅되는 방법을 지정할 수 있습니다. [](direct-routing-landing-page.md) 긴급 음성 라우팅 정책은 정책에 할당된 사용자, 응급 서비스를 호출하는 데 사용되는 번호(예: 미국 911) 및 응급 서비스에 대한 호출이 라우팅되는 방법을 결정하는 향상된 응급 서비스를 사용하도록 설정하는지 여부를 확인합니다.

관리 센터의 Voice Emergency 정책으로 Microsoft Teams 또는 음성을 사용하여 긴급 음성 라우팅 정책을  >   Windows PowerShell. 정책은 사용자 및 네트워크 사이트에 [할당될 수 있습니다.](cloud-voice-network-settings.md)

사용자의 경우 전역(Org-wide default) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 얻습니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 음성 라우팅 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.

## <a name="create-a-custom-emergency-voice-routing-policy"></a>사용자 지정 긴급 음성 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 Microsoft Teams 음성 긴급 정책으로 이동한 다음 라우팅 정책 호출  >   **탭을 클릭합니다.**
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.
4. 동적 긴급 호출을 사용하도록 설정하려면 동적 긴급 호출 **을 를 켜야 합니다.** 동적 긴급 호출을 사용하도록 Teams 서비스에서 정책 및 위치 정보를 검색하고 해당 정보를 긴급 호출의 일부로 포함합니다.
5. 하나 이상의 긴급 번호를 정의합니다. 이렇게하려면 긴급 번호에서 **추가** **를** 클릭한 다음 다음을 클릭합니다.
    1. **긴급 다이얼 문자열**: 긴급 다이얼 문자열을 입력합니다. 이 다이얼 문자열은 호출이 긴급 호출인 경우를 나타냅니다.
        > [!NOTE]
        > 직접 라우팅의 경우 긴급 전화 Teams 앞에 "+"를 사용하여 긴급 전화를 보내는 클라이언트에서 전환합니다. 전환이 완료될 때까지 비상 다이얼 문자열과 일치하는 음성 경로 패턴은 911 및 +911과 같은 이전 "+"이 없는 문자열에 대해 일치하도록 해야 합니다. 예를 들어 ^ \\ +?911 또는 .*입니다.
    2. **긴급 다이얼 마스크**: 각 긴급 번호에 대해 0개 이상의 긴급 다이얼 마스크를 지정할 수 있습니다. 다이얼 마스크는 긴급 다이얼 문자열의 값으로 변환하려는 숫자입니다. 이렇게 하면 대체 긴급 번호에 전화를 걸 수 있으며 통화 도달 응급 서비스를 계속 사용할 수 있습니다. <br>예를 들어 112를 유럽 대부분의 응급 서비스 번호인 비상 다이얼 마스크로 추가하고 911을 긴급 다이얼 문자열로 추가합니다. Teams 유럽의 한 사용자가 911이 미국의 긴급 번호인지 알지 못하고 112에 전화를 걸면 911에 전화를 걸 수 있습니다. 여러 다이얼 마스크를 정의하기 위해 각 값을 세미코론으로 구분합니다. 예를 들어 112;212.
    3. **PSTN 사용 레코드:** PSTN(공용 전환 전화 네트워크) 사용 레코드를 선택합니다. PSTN 사용 레코드는 사용 권한이 부여된 사용자의 긴급 호출을 라우팅하는 데 사용되는 경로를 결정하는 데 사용됩니다. 이 사용과 연결된 경로는 긴급 통화 전용 SIP(세션 시작 프로토콜) 트렁크 또는 가장 가까운 PSAP(공공 안전 응답 지점)에 긴급 호출을 라우팅하는 ELIN(긴급 위치 식별 번호) 게이트웨이를 지적해야 합니다.

    > [!NOTE]
    > 전화 걸기 문자열 및 다이얼 마스크는 정책 내에서 고유해야 합니다. 즉, 정책의 경우 여러 긴급 번호를 정의할 수 있으며 다이얼 문자열에 대해 여러 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열 및 다이얼 마스크는 한 번만 사용되어야 합니다.

6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-voice-routing-policy"></a>긴급 음성 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. 관리 센터의 왼쪽 Microsoft Teams 음성 긴급 정책으로 이동한 다음 라우팅 정책 호출  >   **탭을 클릭합니다.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-users"></a>사용자에게 사용자 지정 긴급 음성 라우팅 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 음성 라우팅 정책 할당

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 호출 라우팅 정책을 할당합니다.

이 예제에서는 Site1 사이트에 긴급 통화 라우팅 정책 1이라는 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>관련 주제

[긴급 통화 정책 관리 Teams](manage-emergency-calling-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)