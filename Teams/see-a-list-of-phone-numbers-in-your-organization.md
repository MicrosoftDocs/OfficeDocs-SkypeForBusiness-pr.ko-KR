---
title: 조직의 전화 번호 목록 보기
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 관리 센터를 사용하여 Microsoft Teams 모든 전화 번호 목록과 사용자에게 할당되거나 할당되지 않은 모든 번호 목록을 볼 수 있습니다.
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432490"
---
# <a name="see-a-list-of-telephone-numbers"></a>전화 번호 목록 보기 

오디오 회의 또는 통화 큐와 같은 사용자 또는 [](deploy-audio-conferencing-teams-landing-page.md) 음성 애플리케이션에 할당할 수 있는 다양한 유형의 전화 [번호가 있습니다.](plan-auto-attendant-call-queue.md) 자세한 내용은 조직의 [전화 번호 관리를 참조하세요.](/microsoftteams/manage-phone-numbers-landing-page)

이 문서는 통화 계획 및 운영자 커넥트. 직접 라우팅에 대한 자세한 내용은 전화 번호 구성 및 엔터프라이즈 음성 및 [음성 을 사용하도록 설정 을 참조하세요.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>조직의 모든 전화 번호를 확인

조직의 모든 전화 번호 목록을 확인하면 다음을 참조하세요.

1. 관리 센터 **Microsoft Teams 로 이동하세요.**

2. 왼쪽 탐색에서 **Voice** 전화  >  **로 이동합니다.**

3. 할당된 전화 번호를 보시고,  할당 상태 열을 참조하여 번호가 할당된 서비스 유형도 보여줍니다.

4. 보기를 필터링하려면 필터 아이콘을 클릭합니다. 필터 **창에서** 드롭다운 목록을 사용하여 보기를 다음으로 필터링할 수 있습니다.

   - **설정한** 숫자 범위입니다. 가장 낮은 숫자 또는 가장 높은 숫자로 검색할 수 있습니다.

   - 지정한 숫자로 시작하는 숫자입니다.

   - 번호 **정품 인증 상태 입니다.**

   - 숫자 **형식 입니다.**

   - 전화 상태 **입니다.**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>사용자에게 할당된 모든 전화 번호를 표시하기 위해

사용자를 설정하는 경우 사용자에게 이미 할당된 전화 번호 목록과 사용자에게 할당할 수 있는 전화 번호 목록을 볼 수 있습니다.

1. 관리 센터 **Microsoft Teams 로 이동하세요.**

2. 왼쪽 탐색에서 **Voice** 전화  >  **로 이동합니다.**

    > [!IMPORTANT]
    > 관리 센터의  왼쪽 탐색에 음성 옵션이 표시될 Microsoft Teams 먼저 적어도 Enterprise **E5** 라이선스, 추가 전화 시스템 추가 기능 라이선스 하나 또는 오디오  회의 추가 기능 **라이선스** 1개 이상을 구입해야 합니다.

3. 할당된 숫자를 빠르게 정렬하려면 할당 상태 열 **제목을** 클릭합니다. 또는 필터 아이콘을 클릭한 다음 보기를 필터링하여 사용자에게 이미 할당된 전화 번호 또는 사용자에게 할당할 수 있는 할당되지 않은 번호를 볼 수 있습니다. 다음을 통해 필터링할 수 있습니다.

   - **사용자에게 할당**
   - **컨퍼런스 브리지에 할당** 
   - **음성 앱에 할당(자동 전화 교환/통화 큐)**
   - **부적당하지 않은**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>음성 사용자에게 할당된 모든 전화 번호를 표시하기 위해

조직에서 전화를 걸고 받을 사용자를 설정하는 경우 먼저 전화 번호를 받은 다음 사용자에게 할당해야 합니다. 전화 번호를 받고 나면 번호 할당의 활성화 상태를 볼 수 있습니다.
  
1. 관리 센터 **Microsoft Teams 로 이동하세요.**

2. 왼쪽 탐색에서 **Voice** 전화  >  **로 이동합니다.**

3. 필터 아이콘을 클릭하여 활성화 상태로 **보기를 필터링합니다.** 다음을 통해 필터링할 수 있습니다.

   - **정품 인증**
   - **할당 보류 중**
   - **할당이 실패했습니다.**
   - **업데이트 보류 중**
   - **업데이트가 실패했습니다.**

## <a name="using-the-teams-powershell-module"></a>PowerShell Teams 사용

이전 섹션에서 Teams PowerShell 모듈을 사용하여 동일한 정보를 얻을 수 있지만 버전 1.1.6 이상이 필요합니다. 여기에는 온라인 비즈니스용 Skype 통합이 포함됩니다. 모듈에 대한 자세한 내용은 [PowerShell Microsoft Teams 참조하세요.](teams-powershell-overview.md)

조직에 대해 사용하는 모든 전화 번호 목록을 표시하기 위해 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) cmdlet을 사용하세요. 예를 들어 각 전화 번호와 해당 상태를 표시하기 위해 다음 명령을 실행합니다.

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

사용자에게 할당된 모든 전화 번호를 표시하기 위해 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet을 사용 합니다. 예를 들어 전화 번호가 할당된 모든 사용자를 표시하기 위해 다음 명령을 실행합니다.

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>관련 항목

[조직의 전화 번호 관리](manage-phone-numbers-landing-page.md)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)