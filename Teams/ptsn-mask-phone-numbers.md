---
title: Microsoft Teams 모임에서 전화 번호 마스크
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
description: Microsoft Teams 모임에서 전화 번호를 마스크하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726797"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 모임에서 전화 번호 마스크

개인 정보 보호를 강화하기 위해 오디오 회의를 사용하여 Teams 모임에 전화 접속하는 참가자의 전화 번호가 내부 참가자에게 완전히 표시됩니다. 이 숫자는 조직 외부의 참가자로부터 마스킹됩니다. 이 설정은 모든 조직의 기본값입니다. 마스크된 숫자는 다음 이미지와 같이 표시됩니다.

![마스크된 전화 번호의 예](media/hiddenPhoneNum.png)

특정 산업 사용 사례의 경우 관리자는 테넌트에서 구성된 모임에 오디오 회의 참가자의 전화 번호가 나타나는 방법을 선택할 수 있습니다. 관리자는 다음 세 가지 옵션 중 선택할 수 있습니다.

- 전화 번호는 외부 참가자에서만 마스킹됩니다. 모임 이끌이의 테넌트에 속한 참가자는 여전히 전체 전화 번호를 볼 수 있습니다.
- 전화 번호는 이끌이를 제외한 모임의 모든 사람이 마스킹됩니다.
- 전화 번호는 마스킹되지 않은 경우 모임의 모든 사람이 볼 수 있습니다.

이 설정은 전화 번호가 노출되는 모임의 모든 표면에 적용됩니다.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell을 사용하여 전화 번호 마스킹 설정

PSTN(공용 전환 전화 네트워크) 마스킹 설정을 변경하기 위해 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 사용 가능한 옵션 중 하나로 설정합니다.

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
