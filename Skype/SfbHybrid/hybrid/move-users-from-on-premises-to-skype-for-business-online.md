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
description: 비즈니스용 Skype Online으로 사용자를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: ddf25614afae48ef647dc325e53ccbab8ac2e5d0
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963026"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동

사용자가 온-프레미스에서 비즈니스용 Skype Online으로 이동 하면 사용자는 비즈니스용 Skype Online과 상호 작용 하 여 기능을 합니다. 온-프레미스에 있던 모든 연락처는 비즈니스용 Skype 온라인에서 사용할 수 있으며, 앞으로 구성 된 모든 기존 모임은 링크가 비즈니스용 Skype Online을 가리키도록 업데이트 됩니다. 사용자가 오디오 회의를 사용할 수 있도록 설정 된 경우 모임에는 전화 접속 좌표도 포함 됩니다.  온-프레미스 환경에서 비즈니스용 Skype Online으로 사용자를 이동 하려면 둘 다 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용 합니다. 

사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 클라우드로 사용자를 이동 해야 합니다.
 
## <a name="move-users-with-move-csuser"></a>사용자를 이동 하는 사용자 이동 

이동-CsUser는 온-프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다. [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 테 넌 트 뿐만 아니라 온-프레미스 환경 둘 다에도 충분 한 권한이 있어야 합니다. 두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 필요한 office 365 관리 역할이 있는 office 365 계정에 대 한 자격 증명을 지정할 수 있습니다.

CsUser를 사용 하 여 온라인으로 사용자를 이동 하려면 다음을 수행 합니다.

- Identity 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.
- -Target 매개 변수를 "sipfed.online.lync.com>" 값과 함께 지정 합니다. <span>com "입니다.
- 온-프레미스 및 Office 365 모두에 충분 한 사용 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365에서 충분 한 사용 권한을 가진 계정을 제공 합니다.
- Office 365에서 사용 권한이 있는 계정이 "설정"으로 끝나지 않는 경우 <span>com "을 선택한 다음 [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여-HostedMigrationOverrideUrl 매개 변수를 지정 해야 합니다.

 > [!NOTE]
 > 테 넌 트에 대 한 올바른 HostedMigrationOverrideUrl 값을 확인 해야 합니다. 이 작업은 레거시 비즈니스용 Skype 관리 센터를 탐색 하 여 쉽게 수행할 수 있습니다. 접두사-XXXXXXX.online.lync.com 및 append/HostedMigration/hostedmigrationservice.svc.를 확인 합니다. 예를 들어 https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc 값을 확인 한 후에는 아래에 표시 된 $url 변수에 사용 합니다.

다음 cmdlet 시퀀스를 사용 하 여 비즈니스용 Skype Online으로 사용자를 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 확인에 대 한 입력으로 제공 된다고 가정 합니다.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

관리자 계정이 MFA (다단계 인증) 인 경우-Credential 매개 변수를 지정 하지 마십시오. 관리자가 자격 증명을 입력 하 라는 메시지가 표시 됩니다.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 사용자 이동 

1. 비즈니스용 Skype 서버 제어판 앱을 엽니다.
2. 왼쪽 탐색 영역에서 **사용자**를 선택 합니다.
3. **찾기를** 사용 하 여 비즈니스용 Skype 온라인으로 이동할 사용자를 찾습니다.
4. 사용자를 선택 하 고 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 비즈니스용 Skype Online으로 이동을**선택 합니다.
5. 마법사에서 **다음**을 클릭합니다.
6. 메시지가 표시 되 면 onmicrosoft.com로 끝나고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.
7. **다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.
8. 성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 주 제어판 앱의 위쪽에 제공 됩니다.

## <a name="see-also"></a>참고 항목

[CsUser 이동](https://docs.microsoft.com/powershell/module/skype/move-csuser)
