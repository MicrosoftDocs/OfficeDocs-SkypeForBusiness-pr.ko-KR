---
title: 긴급 전화 라우팅 정책 관리
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 긴급 통화 라우팅 정책을 사용 및 관리하여 긴급 번호를 설정하고 긴급 통화를 라우팅하는 방법을 지정하는 방법을 배워야 합니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804678"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Microsoft Teams에서 긴급 통화 라우팅 정책 관리

조직에서 전화 시스템 [](direct-routing-landing-page.md) 직접 라우팅을 배포한 경우 Microsoft Teams의 긴급 통화 라우팅 정책을 사용하여 긴급 번호를 설정하고 긴급 통화가 라우팅되는 방법을 지정할 수 있습니다. 긴급 통화 라우팅 정책은 정책이 할당된 사용자에 대해 향상된 응급 서비스를 사용할 수 있는지 여부, 긴급 서비스를 호출하는 데 사용되는 번호(예: 미국의 911) 및 응급 서비스에 대한 통화 라우팅 방법을 확인합니다.

Microsoft Teams 관리 센터의 음성 긴급 정책으로 또는 통화를 사용하여 긴급 통화 라우팅 정책을  >   Windows PowerShell. 정책은 사용자 및 네트워크 사이트에 [할당할 수 있습니다.](cloud-voice-network-settings.md)

사용자의 경우 전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역 정책을 자동으로 얻게 됩니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 통화 라우팅 정책을 할당한 경우 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 다시 지정합니다.

## <a name="create-a-custom-emergency-call-routing-policy"></a>사용자 지정 긴급 통화 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 라우팅 정책  >   **탭을** 클릭합니다.
2. 추가를 **클릭합니다.**
3. 정책의 이름과 설명을 입력합니다.
4. 동적 긴급 통화를 사용하려면 동적 긴급 통화를 **켜야 합니다.** 동적 긴급 통화를 사용하도록 설정하면 Teams는 서비스에서 정책 및 위치 정보를 검색하고 해당 정보를 긴급 통화의 일부로 포함합니다.
5. 하나 이상의 긴급 번호를 정의합니다. 이렇게하려면 긴급 **번호에서** 추가를 클릭하고 다음을 합니다. 
    1. **긴급 전화 문자열:** 긴급 전화 문자열을 입력합니다. 이 다이얼 문자열은 통화가 긴급 통화인 경우를 나타냅니다.
        > [!NOTE]
        > 직접 라우팅의 경우 긴급 전화 문자열 앞에 "+"가 있는 긴급 통화를 보내는 Teams 클라이언트에서 전환합니다. 전환이 완료될 때까지 비상 전화 문자열과 일치하는 음성 경로 패턴은 911 및 +911과 같이 앞에 "+"가 없는 문자열에 대해 일치해야 합니다. 예를 들어 ^ \\ +?911 또는 .*입니다.
    2. **응급 다이얼 마스크:** 각 긴급 번호에 대해 0개 이상의 응급 다이얼 마스크를 지정할 수 있습니다. 다이얼 마스크는 긴급 다이얼 문자열 값으로 변환하려는 번호입니다. 이렇게 하면 대체 긴급 전화로 전화를 걸 수 있으며 통화 연결 긴급 서비스를 계속 사용할 수 있습니다. <br>예를 들어 112를 유럽 대부분의 긴급 서비스 번호인 응급 다이얼 마스크로 추가하고 911을 응급 전화 문자열로 추가합니다. 방문하는 유럽의 Teams 사용자는 911이 미국의 긴급 번호인지 모를 수 있으며, 112에 전화를 걸면 911로 전화를 걸 수 있습니다. 여러 다이얼 마스크를 정의하기 위해 각 값을 세미코론으로 구분합니다. 예: 112;212.
    3. **PSTN 사용 레코드:** PSTN(Public Switched Telephone Network) 사용 레코드를 선택합니다. PSTN 사용 레코드는 사용할 권한이 있는 사용자의 긴급 통화를 라우팅하는 데 사용되는 경로를 결정하는 데 사용됩니다. 이 사용과 연결된 경로는 긴급 통화 전용 SIP(세션 시작 프로토콜) 트렁크 또는 긴급 통화를 가장 가까운 PSAP(공공 안전 응답 지점)로 라우팅하는 ELIN(긴급 위치 식별 번호) 게이트웨이로 연결해야 합니다.

    > [!NOTE]
    > 전화 걸기 문자열 및 다이얼 마스크는 정책 내에서 고유해야 합니다. 즉, 정책의 경우 여러 긴급 번호를 정의하고 다이얼 문자열에 여러 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열 및 다이얼 마스크는 한 번만 사용되어야 합니다.

6. **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallRoutingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-call-routing-policy"></a>긴급 통화 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만드는 모든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 라우팅 정책  >   **탭을** 클릭합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallRoutingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 라우팅 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallRoutingPolicy도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 통화 라우팅 정책 할당

[Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 라우팅 정책을 할당합니다.

이 예제에서는 Site1 사이트에 긴급 통화 라우팅 정책 1이라는 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>관련 항목

[Teams에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
