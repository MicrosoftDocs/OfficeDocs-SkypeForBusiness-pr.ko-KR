---
title: 아웃바운드 호출 제한 - PSTN 호출 오디오 회의 &
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
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
description: 관리자는 사용자가 수행할 수 있는 오디오 회의 및 최종 사용자 PSTN 호출의 유형을 제어할 수 있습니다.
ms.openlocfilehash: fd7dc24d7a920e5fb2c151600c3a6604381044e6
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674810"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>오디오 회의 및 사용자 PSTN 통화의 아웃바운드 전화 제한 정책

관리자는 아웃바운드 통화 컨트롤을 사용하여 조직의 사용자가 수행할 수 있는 오디오 회의 및 최종 사용자 PSTN(공중 전화망) 통화 유형을 제한할 수 있습니다.

아웃바운드 호출 컨트롤은 사용자 단위 또는 테넌트별로 적용할 수 있으며, 각 유형의 아웃바운드 호출을 독립적으로 제한하는 다음 두 가지 컨트롤을 제공합니다. 기본적으로 두 컨트롤은 모두 국제 및 국내 아웃바운드 호출을 허용하도록 설정됩니다.

|컨트롤|설명|컨트롤 옵션|
|:-----|:-----|:-----|
|PSTN 호출 오디오 회의|아웃바운드 유형을 제한합니다. </br>내에서 허용되는 호출 </br>사용자가 구성한 모임입니다.|모든 대상(기본값)</br>이끌이와 동일한 국가 또는 지역에서 </br> [영역 A 국가 또는 지역](audio-conferencing-zones.md) 만 </br>허용 안 함|
|최종 사용자 PSTN 호출|호출 유형을 제한합니다. </br>that can be made by a user.|국제 및 국내(기본값)</br>국내</br>없음|

영역 A로 간주되는 국가 및 지역을 확인하려면 [오디오 회의 국가 및 지역 영역을](audio-conferencing-zones.md) 참조하세요.

   > [!NOTE]
   > 전화 걸기 번호가 모임 이끌이(오디오 회의의 경우) 또는 최종 사용자(최종 사용자 PSTN 통화의 경우)에 대해 Microsoft 365 또는 Office 365 설정된 동일한 국가에 있는 경우 국내로 간주됩니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>오디오 회의 아웃바운드 호출 제한

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **사용자를** 선택한 다음 사용 가능한 사용자 목록에서 사용자의 표시 이름을 선택합니다.

2. 다음으로 **오디오 회의** **이동하여 편집** 을 선택합니다.

3. **모임의 전화 접속** 에서 원하는 전화 걸기 제한 옵션을 선택합니다.

4. **저장** 을 선택합니다.

### <a name="using-powershell"></a>PowerShell 사용

아웃바운드 호출 제한은 각각에 대한 제한 특성이 있는 OnlineDialOutPolicy라는 단일 정책에 의해 제어됩니다. 정책을 사용자 지정할 수 없으며, 설정의 각 조합에 대해 미리 정의된 정책 인스턴스가 있습니다.

Get-CSOnlineDialOutPolicy cmdlet을 사용하여 아웃바운드 호출 정책을 보고 설정에 다음 명령을 사용할 수 있습니다.

**다음 cmdlet을 사용하여 사용자별 수준에서 정책을 설정합니다**. (Get cmdlet처럼 Grant cmdlet에는 "Online"이라는 단어가 포함되어 있지 않습니다.)

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**다음 cmdlet을 사용하여 테넌트 수준에서 정책을 설정합니다**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

전화 접속 정책이 할당되지 않은 테넌트의 모든 사용자는 이 정책을 받게 됩니다. 다른 사용자는 현재 정책을 유지합니다.

**다음 cmdlet을 사용하여 테넌트 수준에서 현재 정책을 확인합니다**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

다음 표에서는 각 정책에 대한 개요를 제공합니다.

|PowerShell cmdlet|설명|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    컨퍼런스의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수도 있습니다.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    컨퍼런스의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    회의의 사용자는 전화를 걸 수 없습니다. 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    컨퍼런스의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로만 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로만 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    전화 회의의 사용자는 전화를 걸 수 없으며 이 사용자는 국내 PSTN 번호로만 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    회의의 사용자는 전화를 걸 수 없으며 이 사용자는 긴급 번호 외에 PSTN 번호에 대한 아웃바운드 전화를 걸 수 없습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    회의의 사용자는 [Zone A 국가 및 지역에](audio-conferencing-zones.md)만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    회의의 사용자는 [Zone A 국가 및 지역에](audio-conferencing-zones.md)만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호에 대한 아웃바운드 호출만 할 수 있습니다.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    회의의 사용자는 [영역 A 국가 및 지역에](audio-conferencing-zones.md)만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호에 대한 아웃바운드 호출을 할 수 없습니다.    |
