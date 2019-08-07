---
title: 오디오 회의 및 사용자 PSTN 통화에 대 한 아웃 바운드 통화 제한 정책
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 관리자는 오디오 회의의 종류와 사용자가 설정할 수 있는 최종 사용자 PSTN 통화를 제어할 수 있습니다.
ms.openlocfilehash: 84601ed50d265bcd48b48b05e5625fcf86c34c7c
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183728"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>오디오 회의 및 사용자 PSTN 통화에 대 한 아웃 바운드 통화 제한 정책

관리자는 아웃 바운드 통화 컨트롤을 사용 하 여 조직의 사용자가 수행할 수 있는 오디오 회의 및 최종 사용자 PSTN 통화 유형을 제한할 수 있습니다. 

아웃 바운드 통화 컨트롤은 사용자별로 적용할 수 있으며 다음 두 가지 컨트롤을 제공 하 여 각 유형의 아웃 바운드 호출을 독립적으로 제한할 수 있습니다. 기본적으로 두 컨트롤 모두 국제 및 국내 아웃 바운드 통화를 허용 하도록 설정 됩니다. 

|Ctrl|설명|제어 옵션|
|:-----|:-----|:-----|
|오디오 회의 PSTN 통화|아웃 바운드 유형을 제한 합니다. </br>내에서 허용 되는 통화 </br>사용자가 구성한 모임|국제 및 국내 (기본값)</br>국내</br>없음|
|최종 사용자 PSTN 통화|통화 유형을 제한 합니다. </br>사용자가 설정할 수 있습니다.|국제 및 국내 (기본값)</br>국내</br>없음|

   > [!NOTE]
   > 전화를 거는 번호가 모임 이끌이 (오디오 회의의 경우) 또는 최종 사용자 (최종 사용자 PSTN 통화의 경우)에 설정 된 같은 365 국가에 있는 경우에는 통화가 국내으로 간주 됩니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>오디오 회의 발신 전화 제한 

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. 페이지 맨 위에서 **편집**을 클릭 합니다.

3. **오디오 회의**옆에 있는 **편집**을 클릭 합니다.

4. **모임에서 전화 걸기 사용 권한**에서 원하는 전화 걸기 제한 옵션을 선택 합니다.

5. **저장**을 클릭 합니다. 

![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘

1.  **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2.  작업 창에서 **편집**을 클릭 합니다.

3.  **이 사용자의 모임에서 전화를 걸 수 있는 제한**에서 원하는 전화 걸기 제한 옵션을 선택 합니다.

    ![전화 걸기 옵션에 대 한 제한 사항](media/restrictions-to-dial-outs.png)

5. **저장**을 클릭 합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**PowerShell 사용**

아웃 바운드 통화 제한은 각에 대 한 제한 특성이 있는 OnlineDialOutPolicy 이라는 단일 정책에 의해 제어 됩니다. 정책은 사용자 지정할 수 없으며, 설정의 각 조합에 대해 미리 정의 된 정책 인스턴스가 있습니다. 

CSOnlineDialOutPolicy cmdlet을 사용 하 여 아웃 바운드 호출 정책을 보고 CSDialOutPolicy cmdlet을 사용 하 여 사용자에 게 할당할 수 있습니다. (Get cmdlet을 사용할 때 Grant cmdlet에 "Online" 이라는 단어가 포함 되지 않는다는 점에 유의 하세요.) 

다음 표에서는 각 정책에 대해 간략하게 설명 합니다.

|||
|:-----|:-----|
|Id = ' tag: DialoutCPCandPSTNInternational '    |    전화 회의에 참가 한 사용자는 국제 및 국내 번호로 통화할 수 있으며,이 사용자는 국제/국내 번호로 아웃 바운드 통화를 할 수도 있습니다.    |
|Id = ' tag: DialoutCPCDomesticPSTNInternational '  |    회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 국제 및 국내 번호로 아웃 바운드 통화를 할 수 있습니다.    |
|    Id = ' tag: DialoutCPCDisabledPSTNInternational '    |    회의 사용자가 전화를 걸 수 없습니다. 이 사용자는 국제 및 국내 번호로 아웃 바운드 통화를 할 수 있습니다.    |
|    Id = ' tag: DialoutCPCInternationalPSTNDomestic '    |    전화 회의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.    |
|    Id = ' tag: DialoutCPCInternationalPSTNDisabled '    |    전화 회의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며,이 사용자는 비상 번호로 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.    |
|    Id = ' tag: DialoutCPCandPSTNDomestic '    |    회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.    |
|    Id = ' tag: DialoutCPCDomesticPSTNDisabled '    |    회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 비상 번호 이외의 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.    |
|    Id = ' tag: DialoutCPCDisabledPSTNDomestic '    |    회의 중인 사용자는 전화를 걸 수 없으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.    |
|    Id = ' tag: DialoutCPCandPSTNDisabled '    |    회의 중 사용자는 전화를 걸 수 없으며,이 사용자는 비상 번호 이외의 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.    |
