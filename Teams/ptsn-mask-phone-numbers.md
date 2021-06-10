---
title: 모임에서 전화 Microsoft Teams 마스크
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 모임에서 전화 번호를 마스킹하는 Microsoft Teams 자세히 알아보세요.
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117716"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>모임에서 전화 Microsoft Teams 마스크

개인 정보 보호를 강화하기 위해 오디오 회의를 사용하여 모임에 Teams 참가자의 전화 번호가 내부 참가자에게 완전히 표시됩니다. 이 숫자는 조직 외부의 참가자로부터 마스킹됩니다. 이 설정은 모든 조직의 기본값입니다. 마스크된 숫자는 다음 이미지와 같이 표시됩니다.

![마스크된 전화 번호의 예](media/hiddenPhoneNum.png)

특정 산업 사용 사례의 경우 관리자는 테넌트에서 구성된 모임에 오디오 회의 참가자의 전화 번호가 나타나는 방법을 선택할 수 있습니다. 관리자는 다음 세 가지 옵션 중 선택할 수 있습니다.

- 전화 외부 참가자만 마스킹됩니다. 모임 이끌이의 테넌트에 속한 참가자는 여전히 전체 전화 번호를 볼 수 있습니다.
- 전화 이끌이를 제외한 모든 모임에서 숫자가 마스킹됩니다.
- 전화 숫자는 가시화되지 않습니다. 따라서 모임의 모든 사람이 볼 수 있습니다.

이 설정은 전화 번호가 노출되는 모임의 모든 표면에 적용됩니다.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell을 사용하여 전화 번호 마스킹 설정

PSTN(공용 전환 전화 네트워크) 마스킹 설정을 변경하기 위해 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 사용 가능한 옵션 중 하나로 설정합니다.

외부 참가자에서만 전화 번호를 마스크하기 위해 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

모임의 모든 참가자(이끌이 제외)의 전화 번호를 마스크하기 위해 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

전화 번호 마스킹을 사용하지 않도록 설정하고 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```