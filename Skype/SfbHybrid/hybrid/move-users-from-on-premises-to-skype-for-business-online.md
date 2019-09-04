---
title: 온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 비즈니스용 Skype Online으로 사용자를 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 74816ae4c67f62cabad018a344b4b1800bd84444
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715896"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동

사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동 하면 사용자가 비즈니스용 Skype Online과 상호 작용 하 여 기능을 사용할 수 있습니다. 온-프레미스 인 모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 앞으로 사용자가 구성한 모든 기존 모임은 링크가 비즈니스용 Skype Online을 가리키도록 업데이트 됩니다. 사용자가 오디오 회의를 사용 하도록 설정 된 경우 모임에는 전화 접속 좌표도 포함 됩니다.  온-프레미스 환경에서 비즈니스용 Skype Online으로 사용자를 이동 하려면 두 개의 온-프레미스 도구를 사용 하는 이동-CsUser cmdlet 또는 비즈니스용 Skype Server 제어판을 사용 합니다. 

사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 사용자를 클라우드로 이동 해야 합니다.
 
## <a name="move-users-with-move-csuser"></a>이동-CsUser와 사용자 이동 

이동-CsUser는 온-프레미스 비즈니스용 Business Management Shell PowerShell 창에서 사용할 수 있습니다. [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 테 넌 트 및 온-프레미스 환경 모두에 충분 한 권한이 있어야 합니다. 두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고, `-Credential` 매개 변수를 사용 하 여 Office 365에 대 한 자격 증명을 지정할 수 있습니다. 계정으로 필요한 Office 365 관리 역할을 사용 합니다.

이동-CsUser를 사용 하 여 사용자를 온라인으로 이동 하려면 다음을 수행 합니다.

- Id 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.
- -Target 매개 변수를 "sipfed. lync. 라는 값으로 지정 합니다. <span>com ".
- 온-프레미스 및 Office 365 모두에 충분 한 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365의 충분 한 사용 권한을 가진 계정을 제공 합니다.
- Office 365의 사용 권한이 있는 계정이 "설정"으로 끝나지 않는 경우 <span>com "에서 [필요한 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여-HostedMigrationOverrideUrl 매개 변수를 지정 해야 합니다.

 > [!NOTE]
 > 테 넌 트에 대 한 올바른 HostedMigrationOverrideUrl 값을 확인 해야 합니다. 이 작업은 레거시 비즈니스용 Skype 관리 센터를 탐색 하 여 쉽게 수행할 수 있습니다. 접두사-XXXXXXX.online.lync.com 및 append/HostedMigration/hostedmigrationservice.svc.를 확인 합니다. 예: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc 값을 확인 한 후 아래 표시 된 대로 $url 변수에 사용 합니다.

다음 cmdlet 시퀀스는 사용자를 비즈니스용 Skype Online으로 이동 하는 데 사용할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 가져오기 프롬프트에 대 한 입력으로 제공 되었다고 가정 합니다.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

관리자 계정이 MFA (다단계 인증) 인 경우-Credential 매개 변수를 지정 하지 마세요. 관리자에 게 자격 증명을 묻는 메시지가 표시 됩니다.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 사용자 이동 

1. 비즈니스용 Skype 서버 제어판 앱을 엽니다.
2. 왼쪽 탐색 창에서 **사용자**를 선택 합니다.
3. **찾기를** 사용 하 여 비즈니스용 Skype Online으로 이동할 사용자를 찾습니다.
4. 사용자를 선택한 다음 목록 위의 **동작** 드롭다운에서 **선택한 사용자를 비즈니스용 Skype Online으로 이동을**선택 합니다.
5. 마법사에서 **다음**을 클릭 합니다.
6. 메시지가 표시 되 면 onmicrosoft.com에 종료 되 고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.
7. **다음**을 클릭 하 고 **** 다음으로 한 번 더 사용자를 이동 합니다.
8. 성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 기본 제어판 앱의 맨 위에 제공 됩니다.

## <a name="see-also"></a>참고 항목

[CsUser 이동](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
