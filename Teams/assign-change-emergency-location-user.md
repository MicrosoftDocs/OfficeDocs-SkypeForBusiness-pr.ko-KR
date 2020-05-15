---
title: 사용자의 응급 위치 할당 또는 변경
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자에 대 한 긴급 위치를 할당 하거나 변경 하는 방법에 대해 설명 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232479"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>사용자의 응급 위치 할당 또는 변경

통화 계획을 설정 하는 경우 각 전화 번호 또는 사용자에 게 긴급 위치를 할당 해야 합니다. 유럽 국가에서 비상 위치는 Office 365 또는 전화 번호를 Office 365로 전송할 때 전화 번호와 연결 됩니다. 미국에서 비상 위치는 사용자에 게 할당 될 때 전화 번호와 연결 됩니다. 사용자가 할당 한 새 위치로 이동 하는 경우 긴급 주소를 변경할 수 있습니다. 긴급 주소 및 위치에 대 한 자세한 내용은 [비상 전화 관리](what-are-emergency-locations-addresses-and-call-routing.md)를 참조 하세요.
  
통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 사용자에 대 한 긴급 위치를 할당 하거나 변경할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **전화 번호**를 클릭 합니다.

2. **전화 번호** 페이지의 목록에서 사용자 번호를 선택 하 고 **편집**을 클릭 합니다.

3. **편집** 창의 **응급 위치**에서 다음 중 하나를 수행 합니다.

   - 긴급 위치를 지정 하려면을 검색 하 고 긴급 위치를 선택 합니다.

   - 사용자에 게 이미 할당 된 비상 위치를 변경 하려면 **X** 를 클릭 하 여 기존 위치를 제거한 다음 할당 하려는 위치를 검색 하 여 선택 합니다.

4. **저장**을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)를 참조 하세요. 

    
## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [사용자에게 응급 위치의 장소 할당 또는 변경](assign-change-emergency-place-user.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)
- [Teams PowerShell 개요](teams-powershell-overview.md)
