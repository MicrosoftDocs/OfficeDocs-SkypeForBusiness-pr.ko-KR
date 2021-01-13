---
title: Microsoft Teams에서 긴급 통화 정책 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 긴급 통화 정책을 사용 및 관리하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 일들을 정의하는 방법을 배워야 합니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1e516252317a0e5f14e705b674255048fb3defb5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804688"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams에서 긴급 통화 정책 관리

조직에서 통화 [](set-up-calling-plans.md) 요금제 또는 [](direct-routing-landing-page.md)배포된 전화 시스템 직접 라우팅을 사용하는 경우 Microsoft Teams의 긴급 통화 정책을 사용하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 일에 대해 정의할 수 있습니다. 정책이 할당된 사용자가 긴급 서비스를 호출할 때 알릴 사용자 및 알림을 제공하는 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 센터에 자동으로 알리고 긴급 통화를 듣도록 정책 설정을 구성할 수 있습니다.  

Microsoft Teams 관리 센터에서 음성 긴급 정책으로 또는 통화를 사용하여 긴급  >   통화 정책을 Windows PowerShell. 정책은 사용자 및 네트워크 사이트에 [할당할 수 있습니다.](cloud-voice-network-settings.md)

사용자의 경우 전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역 정책을 자동으로 얻게 됩니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 통화 정책을 할당한 경우 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 다시 지정합니다.

## <a name="create-a-custom-emergency-calling-policy"></a>사용자 지정 긴급 통화 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 정책  >   **탭을** 클릭합니다.
2. 추가를 **클릭합니다.**
3. 정책의 이름과 설명을 입력합니다.
4. 응급 전화가 걸려 오면 조직 내 다른 사용자에게 일반적으로 보안 센터에 알리는 방법을 설정할 수 있습니다. 이렇게하려면 알림 모드에서 **다음** 중 하나를 선택합니다.
    - **알림 보내기만:** 지정한 사용자 및 그룹에 Teams 채팅 메시지가 전송됩니다.
    - **전화 회의 중이지만** 음소거됩니다. Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹으로 보내지며 발신자와 PSAP 운영자 간의 대화에서 듣기(참여하지는 못합니다)할 수 있습니다.
    - **전화 회의가** 진행 중이면(출시 **예정)** Teams 채팅 메시지가 지정한 사용자 및 그룹에게 전송됩니다. 발신자 및 PSAP 운영자 간의 대화를 듣고 참여하기 위해 음성을 들을 수 있습니다.
5.  전화 회의를  선택했지만 음소거된 알림 모드인 경우 긴급 통화 알림 상자에 전화를 걸 번호에 사용자 또는 그룹의 PSTN 전화 번호를 입력하여 전화를 걸고 긴급 통화에 참가할 수 있습니다.  예를 들어, 조직의 보안 데스크 번호를 입력합니다. 긴급 전화가 걸려오면 전화를 받고 통화를 들을 수 있는 사람.
6. 긴급 전화가 걸려 오면 알릴 하나 이상의 사용자 또는 그룹(예: 조직의 보안 데스크)을 검색하여 선택합니다.  알림은 사용자, 메일 그룹 및 보안 그룹의 전자 메일 주소로 보낼 수 있습니다. 최대 50명까지 알림을 사용할 수 있습니다.
7. 적용을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>긴급 통화 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 모든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 정책  >   **탭을** 클릭합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**
3. 원하는 내용을 변경한 다음 적용을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 통화 정책 할당

[Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 정책을 할당합니다.

다음 예제에서는 Contoso 긴급 통화 정책 1이라는 정책을 Site1 사이트에 할당하는 방법을 보여줍니다.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>관련 항목

[Teams에서 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
