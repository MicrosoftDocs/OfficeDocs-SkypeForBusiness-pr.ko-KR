---
title: 아웃바운드 호출 제한 - 오디오 회의 & PSTN 호출
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 관리자는 사용자가 만들 수 있는 오디오 회의 및 최종 사용자 PSTN 호출 유형을 제어할 수 있습니다.
ms.openlocfilehash: 9e7f656cd51131237507cc184e021128a33d9268
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598412"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>오디오 회의 및 사용자 PSTN 통화의 아웃바운드 전화 제한 정책

관리자는 아웃바운드 호출 컨트롤을 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 및 PSTN(최종 사용자 공용 전환 전화 네트워크) 호출 유형을 제한할 수 있습니다.

아웃바운드 호출 컨트롤은 사용자별로 또는 테넌트별로 적용될 수 있으며, 각 아웃바운드 호출 유형을 독립적으로 제한하기 위해 다음 두 컨트롤을 제공할 수 있습니다. 기본적으로 두 컨트롤은 국제 및 국내 아웃바운드 호출을 허용하도록 설정됩니다.

|제어|설명|제어 옵션|
|:-----|:-----|:-----|
|오디오 회의 PSTN 호출|아웃바운드 형식 제한 </br>내에서 허용되는 호출 </br>사용자가 구성한 모임입니다.|모든 대상(기본값)</br>이끌이와 동일한 국가 또는 지역에서 </br> [영역 A 국가 또는 지역만](audio-conferencing-zones.md) </br>허용하지 않습니다.|
|최종 사용자 PSTN 호출|호출 유형을 제한합니다. </br>사용자가 만들 수 있습니다.|국제 및 국내(기본값)</br>국내선</br>없음|

영역 A로 간주되는 국가 및 지역을 찾으면 오디오 회의의 국가 및 지역을 [참조합니다.](audio-conferencing-zones.md)

   > [!NOTE]
   > 전화 걸기 번호가 모임의 이끌이(오디오 회의의 경우) 또는 최종 사용자(최종 사용자 PSTN 호출의 경우)에 대해 설정된 Microsoft 365 Office 365 국가에 있는 경우 통화가 국내로 간주됩니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>오디오 회의 아웃바운드 호출 제한

![Microsoft Teams ](media/teams-logo-30x30.png) **관리 센터를 사용하여 Microsoft Teams 로고**

1. 왼쪽 탐색에서 **사용자** 를 선택한 다음 사용 가능한 사용자 목록에서 사용자의 표시 이름을 선택합니다.

3. 오디오 **회의** 옆에 있는 편집을 **선택합니다.**

4. 모임에서 **전화** 접속에서 원하는 전화 접속 제한 옵션을 선택합니다.

5. **저장** 을 선택합니다.

![비즈니스용 skype 로고를 나타내는 아이콘](media/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 **오디오** 회의 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자를  >  선택합니다.

2. 작업 창에서 **편집을 선택합니다.**

3.  이 **사용자의 모임에서** 전화 접속 제한에서 원하는 전화 접속 제한 옵션을 선택합니다.

      ![전화 접속 옵션에 대한 제한 사항](media/restrictions-to-dial-outs.png)

4. **저장** 을 선택합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**PowerShell 사용**

아웃바운드 호출 제한은 각각에 대한 제한 특성이 있는 OnlineDialOutPolicy라는 단일 정책에 의해 제어됩니다. 정책을 사용자 지정할 수 없습니다. 설정의 각 조합에 대해 미리 정의된 정책 인스턴스가 있습니다.

Get-CSOnlineDialOutPolicy cmdlet을 사용하여 아웃바운드 호출 정책을 보고 설정에 다음 명령을 사용할 수 있습니다.

**다음 cmdlet을** 통해 사용자당 수준으로 정책을 설정합니다. (권한 부여 cmdlet에는 Get cmdlet에서처럼 "Online"이라는 단어가 포함되지 않습니다.)

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**다음 cmdlet을** 통해 테넌트 수준에서 정책을 설정합니다.

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

전화 접속 정책이 할당되지 않은 테넌트의 모든 사용자에게 이 정책이 표시됩니다. 다른 사용자는 현재 정책으로 유지됩니다.

다음 표에서는 각 정책에 대한 개요를 제공합니다.

|PowerShell cmdlet|설명|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    회의에 참석한 사용자는 전화를 걸 수 없습니다. 이 사용자는 국제 및 국내 번호로 아웃바운드 호출을 할 수 있습니다.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    회의의 사용자는 전화를 걸 수 없습니다. 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    회의의 사용자는 전화를 걸 수 없습니다. 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    회의의 사용자는 Zone [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    회의의 사용자는 Zone [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    회의의 사용자는 영역 [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
