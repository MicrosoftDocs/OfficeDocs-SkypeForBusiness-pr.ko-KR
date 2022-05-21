---
title: 직접 라우팅에 대한 긴급 통화 라우팅 정책 관리
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
description: Microsoft Teams 긴급 통화 라우팅 정책을 사용하고 관리하여 긴급 번호를 설정하고 긴급 통화 라우팅 방법을 지정하는 방법을 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624122"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>직접 라우팅에 대한 긴급 통화 라우팅 정책 관리

조직에서 [직접 라우팅을](direct-routing-landing-page.md) 배포한 경우 Microsoft Teams 긴급 통화 라우팅 정책을 사용하여 긴급 번호를 설정하고 긴급 통화 라우팅 방법을 지정할 수 있습니다. 긴급 통화 라우팅 정책은 정책이 할당된 사용자에 대해 향상된 응급 서비스를 사용할 수 있는지 여부, 응급 서비스를 호출하는 데 사용되는 번호(예: 미국 911) 및 응급 서비스 호출을 라우팅하는 방법을 결정합니다. 

> [!Note]
> **이러한 통화 라우팅 정책은 직접 라우팅에만 적용됩니다. 통화 플랜 또는 운영자 연결 적용되지 않습니다.**

Microsoft Teams 관리 센터에서 또는 Windows PowerShell 사용하여 **VoiceEmergency**  >  정책으로 이동하여 긴급 통화 라우팅 정책을 관리합니다. 정책은 사용자 및 [네트워크 사이트에](cloud-voice-network-settings.md) 할당할 수 있습니다.

사용자의 경우 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 받게 됩니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 바꾸거나 삭제할 수는 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 통화 라우팅 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책은 사용자에게 할당된 정책을 재정의합니다.

## <a name="create-a-custom-emergency-call-routing-policy"></a>사용자 지정 긴급 통화 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **VoiceEmergency** >  정책으로 이동한 다음 **통화 라우팅 정책 탭을** 클릭합니다.
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.
4. 동적 긴급 통화를 사용하도록 설정하려면 **동적 긴급 통화를** 켭니다. 동적 긴급 통화가 활성화되면 Teams 서비스에서 정책 및 위치 정보를 검색하고 해당 정보를 긴급 통화의 일부로 포함합니다.
5. 하나 이상의 긴급 번호를 정의합니다. 이렇게 하려면 **긴급 번호** 아래에서 **추가** 를 클릭한 다음 다음을 수행합니다.
    1. **긴급 다이얼 문자열**: 긴급 다이얼 문자열을 입력합니다. 이 다이얼 문자열은 통화가 긴급 통화이며 경로 패턴이 이 다이얼 문자열과 정확히 일치해야 임을 나타냅니다. 
        > [!NOTE]
        > **직접 라우팅의 경우 Teams 클라이언트는 더 이상 긴급 다이얼 문자열 앞에 "+"가 있는 긴급 전화를 보내지 않습니다. 긴급 다이얼 문자열과 일치하는 음성 경로 패턴이 이러한 변경 사항을 반영하는지 확인합니다.**
    2. **응급 다이얼 마스크**: 각 긴급 번호에 대해 0개 이상의 긴급 다이얼 마스크를 지정할 수 있습니다. 다이얼 마스크는 긴급 다이얼 문자열의 값으로 변환하려는 번호입니다. 이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며 여전히 통화가 응급 서비스에 도달합니다. <br>예를 들어 유럽 대부분의 응급 서비스 번호인 긴급 다이얼 마스크로 112를 추가하고 911을 긴급 다이얼 문자열로 추가합니다. 방문하는 유럽의 Teams 사용자는 911이 미국 긴급 번호라는 것을 알지 못할 수 있으며 112로 전화를 걸면 911로 전화됩니다. 여러 다이얼 마스크를 정의하려면 각 값을 세미콜론으로 구분합니다. 예를 들어 112;212입니다.
    3. **PSTN 사용량 레코드**: PSTN(공중 전화망) 사용 레코드를 선택합니다. PSTN 사용량 레코드는 사용할 권한이 있는 사용자의 긴급 통화를 라우팅하는 데 사용되는 경로를 결정하는 데 사용됩니다. 이 사용과 관련된 경로는 긴급 통화 전용 SIP(Session Initiation Protocol) 트렁크 또는 긴급 통화를 가장 가까운 PSAP(공공 안전 응답 지점)로 라우팅하는 ELIN(긴급 위치 식별 번호) 게이트웨이를 가리킵니다.

    > [!NOTE]
    > 다이얼 문자열 및 다이얼 마스크는 정책 내에서 고유해야 합니다. 즉, 정책의 경우 여러 긴급 번호를 정의할 수 있으며 다이얼 문자열에 대해 여러 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열과 다이얼 마스크는 한 번만 사용해야 합니다.

6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallRoutingPolicy를 참조하세요](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>긴급 통화 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **VoiceEmergency** >  정책으로 이동한 다음 **통화 라우팅 정책 탭을** 클릭합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 대로 변경한 다음 **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallRoutingPolicy를 참조하세요](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 라우팅 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)도 참조하세요.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 통화 라우팅 정책 할당

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 할당할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **LocationsNetwork** >  **토폴로지** 로 이동하고 **네트워크 사이트** 탭을 클릭합니다.
2. 이름 왼쪽을 클릭하여 사이트를 선택한 다음 **편집** 을 클릭합니다.
3. **긴급 통화 라우팅 정책** 에서 정책을 선택한 다음 **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 라우팅 정책을 할당합니다.

이 예제에서는 Site1 사이트에 긴급 통화 라우팅 정책 1이라는 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>관련 항목

[Teams 긴급 통화 정책 관리](manage-emergency-calling-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
