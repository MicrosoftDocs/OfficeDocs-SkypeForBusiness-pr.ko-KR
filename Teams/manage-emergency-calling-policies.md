---
title: Microsoft Teams에서 긴급 통화 정책 관리
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
description: Microsoft Teams에서 긴급 통화 정책을 사용하고 관리하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 작업을 정의하는 방법을 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 4b5d293cbbd588a564ff1a0118ab4d56f96c17a2
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414645"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams에서 긴급 통화 정책 관리

조직에서 Microsoft 통화 플랜, 운영자 연결, Teams 전화 모바일 또는 직접 라우팅을 [PSTN 연결 옵션](pstn-connectivity.md)으로 사용하는 경우 Microsoft Teams의 긴급 통화 정책을 사용하여 조직의 Teams 사용자가 긴급 전화를 걸 때 발생하는 작업을 정의할 수 있습니다.

정책을 할당받은 사용자가 응급 서비스를 호출할 때 알릴 사용자와 알림을 받는 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화를 수신하도록 정책 설정을 구성할 수 있습니다.  

Microsoft Teams 관리 센터에서 **음성** > **긴급 정책** 으로 이동하거나 Windows PowerShell 사용하여 긴급 통화 정책을 관리합니다. 정책은 사용자 및 [네트워크 사이트에](cloud-voice-network-settings.md) 할당할 수 있습니다.

사용자의 경우 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 가져옵니다. 전역 정책에서 설정을 편집할 수 있지만 이름을 바꾸거나 삭제할 수는 없습니다. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.

네트워크 사이트 및 사용자에게 긴급 통화 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책은 사용자에게 할당된 정책을 재정의합니다.

## <a name="create-a-custom-emergency-calling-policy"></a>사용자 지정 긴급 통화 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **긴급 정책** 으로 이동한 다음 **통화 정책** 탭을 클릭합니다.

2. **추가** 를 클릭합니다.

3. 정책의 이름과 설명을 입력합니다.

4. 최종 사용자가 회사 네트워크 외부의 네트워크 위치에서 작업할 때 긴급 주소를 구성할 수 있도록 **외부 위치 조회 모드** 를 켜기로 설정합니다.

5. 긴급 통화가 이루어질 때 조직의 사람들에게 알리는 방법(일반적으로 보안 데스크)을 설정합니다. 이렇게 하려면 **알림 모드** 에서 다음 중 하나를 선택합니다.

    - **알림만 보내기**: 지정한 사용자 및 그룹에 Teams 채팅 메시지가 전송됩니다.
    - **회의 중이지만 음소거됨**: Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹에 전송되며 발신자와 PSAP 운영자 간의 대화에서 수신 대기(참가할 수는 없음)할 수 있습니다.
    - **회의 중이며 대체되지 않음**: 지정한 사용자 및 그룹에 Teams 채팅 메시지가 전송되며 발신자와 PSAP 운영자 간의 대화를 듣고 참여하기 위해 음소거를 해제할 수 있습니다.

6.  **응급 서비스 고지 사항을** 설정하여 최종 사용자에게 긴급 위치를 확인하도록 알림 배너를 표시합니다.

7.  **음소거된 알림 모드에서 회의** 중 하나를 선택한 경우 **긴급 통화 알림을 위해 전화 걸기 번호** 상자에서 전화를 걸고 긴급 통화에 참가할 사용자 또는 그룹의 PSTN 전화 번호를 입력할 수 있습니다. 예를 들어 조직의 보안 데스크 번호를 입력합니다. 긴급 전화가 걸려 올 때 전화를 받고 통화에서 수신 대기할 수 있습니다. 모드가 음소거된 회의로 설정되어 있지만 음소거 해제할 수 있는 경우에도 PSTN 휴대폰 **을 음소거 해제할 수** 없습니다.

8. 조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색하여 선택하여 긴급 전화를 걸 때 알립니다.  알림을 사용자, 메일 그룹 및 보안 그룹의 이메일 주소로 보낼 수 있습니다. 최대 50명의 사용자에게 알림을 받을 수 있습니다.

9. **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsTeamsEmergencyCallingPolicy를](/powershell/module/skype/new-csteamsemergencycallingpolicy) 참조하세요.

## <a name="edit-an-emergency-calling-policy"></a>긴급 통화 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

전역 정책 또는 사용자가 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **긴급 정책** 으로 이동한 다음 **통화 정책** 탭을 클릭합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 대로 변경한 다음 **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallingPolicy를](/powershell/module/skype/set-csteamsemergencycallingpolicy) 참조하세요.

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)도 참조하세요.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 통화 정책 할당

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

만든 전역 정책 또는 사용자 지정 정책을 할당할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **네트워크 토폴로지** 로 이동하고 **네트워크 사이트** 탭을 클릭합니다.
2. 이름 왼쪽을 클릭하여 사이트를 선택한 다음 **편집** 을 클릭합니다.
3. **긴급 통화 정책** 에서 정책을 선택한 다음 **저장** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용
[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 정책을 할당합니다.

다음 예제에서는 Contoso 긴급 통화 정책 1이라는 정책을 Site1 사이트에 할당하는 방법을 보여  있습니다.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>관련 주제

[Teams에서 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
