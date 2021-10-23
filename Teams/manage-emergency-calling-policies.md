---
title: 긴급 통화 정책 관리 Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: 조직에서 긴급 호출 정책을 Microsoft Teams 조직의 사용자가 긴급 통화를 할 때 발생하는 Teams 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 842fa95be2c9aecaa14b1902ed5b3feb4ca0da7a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536549"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>긴급 통화 정책 관리 Microsoft Teams

조직에서 Microsoft 통화 요금제, 운영자 커넥트 또는 직접 라우팅을 [PSTN](pstn-connectivity.md)연결 옵션으로 사용하는 경우 조직의 Microsoft Teams 사용자가 긴급 호출을 할 때 발생하는 Teams 정의할 수 있습니다.

정책을 할당한 사용자가 긴급 서비스를 호출할 때 알릴 사용자와 알림을 제공하는 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화에서 수신을 수신하도록 정책 설정을 구성할 수 있습니다.  

관리 센터의 음성 긴급 정책으로 Microsoft Teams 또는 전화 통화를 사용하여 긴급  >   통화 정책을 Windows PowerShell. 정책은 사용자 및 네트워크 사이트에 [할당될 수 있습니다.](cloud-voice-network-settings.md)

사용자의 경우 전역(Org-wide default) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 얻습니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 호출 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.

## <a name="create-a-custom-emergency-calling-policy"></a>사용자 지정 긴급 통화 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 긴급 정책으로 이동한 다음 통화 정책  >   **탭을 클릭합니다.**
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.
4. 조직 내 사용자(일반적으로 보안 데스크)에 긴급 호출이 걸릴 때 알리는 방법을 설정합니다. 이렇게하려면 알림 **모드에서** 다음 중 하나를 선택합니다.
    - **알림만 보내기**: Teams 채팅 메시지가 지정한 사용자 및 그룹에 전송됩니다.
    - **음소거** 및 음소거를 할 수 없는 회의: Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹으로 보내지며 발신자 및 PSAP 연산자 간의 대화에서 수신(참여하지는 않지만)할 수 있습니다.
    - **음소거로** 회의를 진행했지만 음소거를 Teams 채팅 메시지는 지정한 사용자 및 그룹으로 보내지며 발신자 및 PSAP 연산자 간의 대화를 듣고 참여하기 위해 음소거를 해지할 수 있습니다.
5.  음소거 알림 모드에서  회의 중 하나를 선택한 경우  긴급 통화 알림 상자에 전화를 걸 수 있는 번호 상자에서 통화하고 긴급 통화에 참가할 사용자 또는 그룹의 PSTN 전화 번호를 입력할 수 있습니다. 예를 들어 조직의 보안 데스크 수를 입력합니다. 긴급 통화가 걸려오면 전화를 받고 통화를 수신할 수 있는 사람입니다. 모드가 음소거된 컨퍼런스로 설정되어 있지만 음소거를 하여 음소거를 할 수 있는 경우에도 PSTN 휴대폰을 음소거할 **수 없습니다.**
6. 조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색하여 선택하여 긴급 통화가 언제 이행될지 알릴 수 있습니다.  알림은 사용자, 메일 그룹 및 보안 그룹의 전자 메일 주소로 보낼 수 있습니다. 최대 50명에게 알림을 할 수 있습니다.
7. 적용 **을 클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallingPolicy를 참조합니다.](/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>긴급 통화 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 긴급 정책으로 이동한 다음 통화 정책  >   **탭을 클릭합니다.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 내용을 변경한 다음 적용을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallingPolicy를 참조합니다.](/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에게 사용자 지정 긴급 호출 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy 를 참조합니다.](/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 호출 정책 할당

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 호출 정책을 할당합니다.

다음 예제에서는 Site1 사이트에 Contoso 긴급 통화 정책 1이라는 정책을 할당하는 방법을 보여줍니다.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>관련 항목

[긴급 통화 라우팅 정책 관리 Teams](manage-emergency-call-routing-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)