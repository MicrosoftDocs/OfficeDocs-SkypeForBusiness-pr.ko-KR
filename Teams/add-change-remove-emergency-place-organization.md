---
title: 긴급 위치 추가, 변경, 제거
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
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 조직의 긴급 위치를 추가, 변경 또는 제거하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5421ff4e73d93c12244b3419342110b419f1b500
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614191"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>조직의 응급 위치에 대한 장소 추가, 변경 또는 제거

조직의 물리적 위치 수에 따라 건물, 층 및 사무실의 *장소를* 추가하여 보다 구체적인 긴급 위치를 만들 수 있습니다.

그러나 PSTN 연결 옵션에 따라 응급 위치 및 위치 요구 사항을 관리하는 방법이 달라질 수 있습니다. 자세한 내용은 [긴급 통화 관리를 참조하세요](what-are-emergency-locations-addresses-and-call-routing.md).

이 문서에서는 조직의 긴급 *위치를* 추가, 변경 또는 제거하는 방법을 설명합니다.

이 문서는 Microsoft 통화 플랜, 운영자 연결, Teams Phone Mobile 및 직접 라우팅에 적용됩니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 조직의 긴급 위치를 관리합니다.
  
## <a name="add-a-place-to-an-emergency-location"></a>긴급 위치에 장소 추가

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. 목록에서 위치를 추가할 위치의 이름을 클릭합니다.
3. **위치** 탭에서 **추가** 를 클릭합니다.
4. 장소 이름을 입력한 다음 **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[New-CsOnlineLisLocation을 참조하세요](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>긴급 위치의 위치 변경

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. 목록에서 위치를 변경할 위치의 이름을 클릭합니다.
3. **위치** 탭에서 변경할 위치를 선택한 다음 **편집** 을 클릭합니다.
4. 위치 정보를 업데이트한 다음 **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineLisLocation을 참조하세요](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>긴급 위치에서 장소 제거

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **위치** > **긴급 주소를** 클릭합니다.
2. 목록에서 위치를 제거할 위치의 이름을 클릭합니다.
3. **위치** 탭에서 제거할 위치를 선택한 다음 **삭제** 를 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Remove-CsOnlineLisLocation을 참조하세요](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>관련 주제

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)
- [긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)