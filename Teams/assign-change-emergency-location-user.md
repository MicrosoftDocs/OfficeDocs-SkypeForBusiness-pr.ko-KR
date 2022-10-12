---
title: 사용자의 응급 위치 할당 또는 변경
author: CarolynRowe
ms.author: crowe
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
description: 이 문서에서는 조직의 사용자에 대한 긴급 위치를 할당하거나 변경하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a43ca031b8787d62639e141c3f733acdb402f85a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551654"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>사용자의 응급 위치 할당 또는 변경

[PSTN 연결 옵션](pstn-connectivity.md)에 관계없이 Microsoft 통화 플랜, 운영자 연결, Teams Phone Mobile 또는 직접 라우팅을&mdash;선택&mdash;하려면 각 전화 번호 또는 사용자에게 긴급 위치를 할당해야 합니다.

그러나 PSTN 연결 옵션에 따라 사용자의 응급 위치를 관리하고 할당하는 방법은 다를 수 있습니다. 자세한 내용은 [긴급 통화 관리를 참조하세요](what-are-emergency-locations-addresses-and-call-routing.md).

이 문서에서는 사용자의 긴급 위치를 할당하거나 변경하는 방법을 설명합니다. 

이 문서는 통화 플랜, 운영자 연결 및 Teams Phone Mobile에 적용됩니다.
  
Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 사용자의 긴급 위치를 할당하거나 변경할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **전화 번호를** 클릭합니다.

2. **전화 번호** 페이지에서 **숫자** 탭을 클릭하고 목록에서 사용자 번호를 선택한 다음 **편집** 을 클릭합니다.

3. **편집** 창의 **긴급 위치에서** 다음 중 하나를 수행합니다.

   - 긴급 위치를 할당하려면 긴급 위치를 검색하고 선택합니다.

   - 사용자에게 이미 할당된 긴급 위치를 변경하려면 **X** 를 클릭하여 기존 위치를 제거한 다음 할당할 위치를 검색하여 선택합니다.

4. 전화 번호 정보를 사용하여 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 **Email 사용자를** 끄거나 켭니다. 기본적으로 이 기능은 켜집니다.

5. **적용** 을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)를 참조하세요. 

    
## <a name="related-topics"></a>관련 주제

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [사용자에게 응급 위치의 장소 할당 또는 변경](assign-change-emergency-place-user.md)
- [조직의 응급 위치에 대한 장소 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)
