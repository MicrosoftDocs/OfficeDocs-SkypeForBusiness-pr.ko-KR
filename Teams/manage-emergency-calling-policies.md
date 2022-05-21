---
title: Microsoft Teams 긴급 통화 정책 관리
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
description: 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 작업을 정의하기 위해 Microsoft Teams 긴급 통화 정책을 사용하고 관리하는 방법을 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 66ff287911a22de8b65ed356cd07833a2bbbb0ca
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624102"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams 긴급 통화 정책 관리

조직에서 [PSTN 연결 옵션](pstn-connectivity.md)으로 Microsoft 통화 플랜, 운영자 연결 또는 직접 라우팅을 사용하는 경우 Microsoft Teams 긴급 통화 정책을 사용하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 작업을 정의할 수 있습니다.

정책이 할당된 사용자가 응급 서비스를 호출할 때 알릴 사용자와 알림을 받을 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화를 수신하도록 정책 설정을 구성할 수 있습니다.  

Microsoft Teams 관리 센터에서 또는 Windows PowerShell 사용하여 **VoiceEmergency**  >  정책으로 이동하여 긴급 통화 정책을 관리합니다. 정책은 사용자 및 [네트워크 사이트에](cloud-voice-network-settings.md) 할당할 수 있습니다.

사용자의 경우 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 받게 됩니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 바꾸거나 삭제할 수는 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 통화 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책은 사용자에게 할당된 정책을 재정의합니다.

## <a name="create-a-custom-emergency-calling-policy"></a>사용자 지정 긴급 통화 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **VoiceEmergency** >  정책으로 이동한 다음 **통화 정책** 탭을 클릭합니다.
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.
4. 최종 사용자가 회사 네트워크 외부의 네트워크 위치에서 작업할 때 긴급 주소를 구성할 수 있도록 **외부 위치 조회 모드** 를 설정하세요.
5. 긴급 통화가 이루어질 때 조직의 사용자(일반적으로 보안 데스크)에 알리는 방법을 설정합니다. 이렇게 하려면 **알림 모드** 에서 다음 중 하나를 선택합니다.
    - **알림 보내기만**: 지정한 사용자 및 그룹에 Teams 채팅 메시지가 전송됩니다.
    - **음소거됨으로 회의 중이고 음소거 해제할 수 없음**: Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹에 전송되며 호출자와 PSAP 연산자 간의 대화에서 수신 대기(참가하지 않음)할 수 있습니다.
    - **음소거로 회의되었지만 음소거 해제할 수 있습니다**. Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹에 전송되며, 음소거를 해제하여 발신자와 PSAP 연산자 간의 대화에 참여하고 수신 대기할 수 있습니다.
5.  **응급 서비스 고지 사항을** 설정하여 최종 사용자에게 긴급 위치를 확인하도록 상기시키는 배너를 표시합니다.
6.  **음소거 알림 모드에서 회의** 중 하나를 선택한 경우 **긴급 통화 알림 상자에 전화 걸기 번호** 상자에서 전화 및 긴급 통화에 참가할 사용자 또는 그룹의 PSTN 전화 번호를 입력할 수 있습니다. 예를 들어 조직의 보안 데스크 번호를 입력합니다. 긴급 전화가 걸려 올 때 전화를 받은 다음 통화에서 수신 대기할 수 있습니다. 모드가 음소거 모드로 설정되었지만 음소거 해제할 수 있는 경우에도 PSTN 휴대폰을 음소거 **해제할 수** 없습니다.
7. 조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색하여 선택하여 긴급 통화가 이루어질 때 알립니다.  알림을 사용자, 메일 그룹 및 보안 그룹의 이메일 주소로 보낼 수 있습니다. 최대 50명의 사용자에게 알림을 받을 수 있습니다.
8. **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallingPolicy를 참조하세요](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>긴급 통화 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **VoiceEmergency** >  정책으로 이동한 다음 **통화 정책** 탭을 클릭합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 대로 변경한 다음 **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallingPolicy를](/powershell/module/skype/set-csteamsemergencycallingpolicy) 참조하세요.

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)도 참조하세요.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 통화 정책 할당

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 만든 사용자 지정 정책을 할당할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **LocationsNetwork** >  **토폴로지** 로 이동하고 **네트워크 사이트** 탭을 클릭합니다.
2. 이름 왼쪽을 클릭하여 사이트를 선택한 다음 **편집** 을 클릭합니다.
3. **긴급 통화 정책** 에서 정책을 선택한 다음 **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용
[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 정책을 할당합니다.

다음 예제에서는 Contoso 긴급 통화 정책 1이라는 정책을 Site1 사이트에 할당하는 방법을 보여줍니다.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>관련 항목

[Teams 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
