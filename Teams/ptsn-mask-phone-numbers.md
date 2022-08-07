---
title: Microsoft Teams 모임에서 전화 번호 마스킹
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 모임에서 전화 번호를 마스킹하는 방법 알아보기
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270823"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 모임에서 전화 번호 마스킹

개인 정보 보호를 강화하기 위해 오디오 회의를 사용하여 Teams 모임에 참가하는 참가자의 전화 번호가 내부 참가자에게 완전히 표시됩니다. 숫자는 조직 외부의 참가자로부터 마스킹됩니다. 이 설정은 모든 조직의 기본값입니다. 마스킹된 번호는 다음 이미지와 같이 표시됩니다.

![마스킹된 전화 번호의 예입니다.](media/hiddenPhoneNum.png)

특정 업계 사용 사례의 경우 관리자는 테넌트에 구성된 모임에서 오디오 회의 참가자의 전화 번호가 표시되는 방식을 선택할 수 있습니다. 관리자는 다음 세 가지 옵션 중에서 선택할 수 있습니다.

- 전화 번호는 외부 참가자만 마스킹됩니다. 모임 이끌이의 테넌트에 속한 참가자는 여전히 전체 전화 번호를 볼 수 있습니다.
- 전화 번호는 이끌이를 제외한 모임의 모든 사용자로부터 마스킹됩니다.
- 전화 번호는 마스크를 해제하여 모임의 모든 사용자가 볼 수 있도록 합니다.

이 설정은 전화 번호가 노출되는 모임의 모든 화면에 적용됩니다.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell을 사용하여 전화 번호 마스킹 설정

PSTN(공중 전화망) 마스킹 설정을 변경하려면 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 사용 가능한 옵션 중 하나로 설정합니다 **`MaskPstnNumbersType`**.

외부 참가자의 전화 번호만 마스킹하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

모임의 모든 참가자(이끌이 제외)의 전화 번호를 마스킹하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

전화 번호 마스킹을 사용하지 않도록 설정하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
