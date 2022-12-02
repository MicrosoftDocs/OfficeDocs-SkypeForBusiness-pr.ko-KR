---
title: Microsoft Teams 모임에서 전화 번호 마스킹
author: heidip
ms.author: heidip
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
ms.openlocfilehash: 7072d1853a49d9e7ebc59e360c971874ed6549a3
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242272"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 모임에서 전화 번호 마스킹

개인 정보 보호를 강화하기 위해 오디오 회의를 사용하여 Teams 모임에 접속하는 참가자의 전화 번호가 내부 참가자에게 완전히 표시됩니다. 숫자는 조직 외부의 참가자로부터 마스킹됩니다. 이 설정은 모든 조직의 기본값입니다. 마스킹된 번호는 다음 이미지와 같이 표시됩니다.

![마스킹된 전화 번호의 예입니다.](media/hiddenPhoneNum.png)

특정 업계 사용 사례의 경우 관리자는 테넌트에서 구성된 모임에서 오디오 회의 참가자의 전화 번호가 표시되는 방식을 선택할 수 있습니다. 관리자는 다음 세 가지 옵션 중에서 선택할 수 있습니다.

- 전화 번호는 외부 참가자만 마스킹됩니다. 모임 이끌이의 테넌트에서 속한 참가자는 여전히 전체 전화 번호를 볼 수 있습니다.
- 전화 번호는 이끌이를 제외한 모임의 모든 사용자로부터 마스킹됩니다.
- 전화 번호는 마스크가 해제되어 모임의 모든 사용자가 볼 수 있습니다.

이 설정은 전화 번호가 노출되는 모임의 모든 화면에 적용됩니다.

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Teams 관리 센터를 사용하여 전화 번호 마스킹 설정

Teams 관리 센터에서 PSTN(공용 전화망) 마스킹 설정을 변경하려면 관리자 권한으로 Teams 관리 센터에 로그인하고 왼쪽 탐색 패널에서 **모임** > **회의 브리지** 를 선택한 다음 **브리지 설정을** 선택합니다. **마스킹된 호출자 ID 표시** 는 브리지 설정 창 아래쪽의 드롭다운이며 다음을 선택할 수 있습니다.

- 조직 외부 참가자에게
- 모든 모임 참가자에게
- 사용 안 함

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell을 사용하여 전화 번호 마스킹 설정

PowerShell에서 PSTN 마스킹 설정을 변경하려면 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) cmdlet의 매개 변수를 사용 가능한 옵션 중 하나로 설정합니다 **`MaskPstnNumbersType`**.

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
