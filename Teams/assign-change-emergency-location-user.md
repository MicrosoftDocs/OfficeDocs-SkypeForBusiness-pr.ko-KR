---
title: 사용자의 응급 위치 할당 또는 변경
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자에 대한 긴급 위치를 할당하거나 변경하는 방법에 대해 알아보고 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36be65ef14cfe0fc97ce49dfa9227fe50daa18f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588380"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>사용자의 응급 위치 할당 또는 변경

통화 계획을 설정할 때 각 전화 번호 또는 사용자에게 긴급 위치를 할당해야 합니다. 유럽 국가에서는 전화 번호를 Microsoft 365 또는 Office 365 전화 번호를 전송할 때 전화 번호와 Microsoft 365 Office 365. 미국의 경우 긴급 위치가 사용자에게 할당될 때 전화 번호와 연결됩니다. 할당된 사용자가 새 위치로 이동하는 경우 비상 주소를 변경할 수 있습니다. 긴급 주소 및 위치에 대한 자세한 내용은 긴급 위치, 장소 및 통화 [라우팅이란? 을 참조하세요.](./what-are-emergency-locations-addresses-and-call-routing.md)
  
통화 계획 및 비용에 대한 자세한 내용은 추가 Teams [라이선스 를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
관리자 센터 또는 PowerShell을 사용하여 사용자에 대한 Microsoft Teams 위치를 할당하거나 변경할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 전화  >  **클릭합니다.**

2. 숫자 **전화** 페이지에서 숫자 탭을  클릭하고 목록에서 사용자 번호를 선택한 다음 **편집을 클릭합니다.**

3. 편집 **창의** 긴급 **위치 아래에서** 다음 중 하나를 합니다.

   - 긴급 위치를 할당하려면 긴급 위치를 검색하고 선택합니다.

   - 사용자에게 이미 할당된 긴급 위치를 변경하려면 **X를** 클릭하여 기존 위치를 제거한 다음, 할당할 위치를 검색하고 선택합니다.

4. 전화 번호 정보가 있는 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄기** 기본적으로 이 설정은 설정되어 있습니다.

5. 적용 **을 클릭합니다.**

## <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>관련 주제

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [사용자에게 응급 위치의 장소 할당 또는 변경](assign-change-emergency-place-user.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)