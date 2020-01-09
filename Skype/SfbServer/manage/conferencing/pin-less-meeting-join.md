---
title: 비즈니스용 Skype 서버에서 핀 덜 모임 참가 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '요약: 비즈니스용 Skype 서버에서 핀 없는 모임 참가 옵션을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 5b8ad452f54785a916ac70acd468458215135934
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991793"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 핀 덜 모임 참가 구성
 
**요약:** 비즈니스용 Skype 서버에서 핀 없는 모임 참가 옵션을 구성 하는 방법에 대해 알아봅니다.
  
전화 접속 발신자가 모임에 참가 하려고 시도 하는 경우, 컨퍼런스 자동 전화 교환 (CAA) 서비스는 해당 발신자가 아직 통화 중이 아니고 전화 접속 발신자가 지시선 핀을 입력 하지 않은 경우에는 대기실와는 다른 대기 &#x2014;을 놓습니다. 고정 없는 모임 참가 옵션을 사용 하면 전화 접속 발신자가 통화 중에 첫 번째 사용자 인 경우에도 지시선 PIN을 입력 하지 않고도 모임에 참가할 수 있습니다. 
  
이 기능을 구성할 때 다음 사항에 유의 하세요.
  
- 비공개 모임에만 적용 됩니다.
    
- PSTN 호출자가 인증 된 사용자 없이 비공개 모임에 유지할 수 있도록 합니다.
    
- 설정이 변경 되 면 기존 및 새 비공개 모임 모두에 적용 됩니다.
    
- 이끌이 사이트 또는 전역 수준에서 사용 하도록 설정할 수 있습니다.
    
- 대기실를 우회할 수 있는 사용자에 대 한 옵션은 다음 중 하나에 대해 설정할 수 있습니다. 
    
  - **호출자가 있는 조직의 모든 사용자에 게 직접 액세스**
    
  - **모든 사람이 (제한 없음) 호출자를 직접 가져옵니다** (이는 기본 설정).
    
- 핀이 없는 참가를 사용 하도록 구성 된 경우 CAA 서비스는 여전히 리더 PIN을 묻는 메시지를 표시 합니다. 사용자는 PIN이 입력 되었는지 여부에 상관 없이 모임에 참가할 수 있습니다. 그러나, 지시선 PIN을 입력 하는 기능을 통해 전화 접속 발신자가 리더를 인증 하 고 필요한 경우 모임을 관리할 수 있습니다.
    
## <a name="configure-pin-less-meeting-join"></a>핀 더 적은 모임 참가 구성

사용자에 대 한 핀 없는 모임 참가를 사용 하도록 설정 하려면 다음과 같이 AllowAnonymousPstnActivation 매개 변수와 함께 [CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet을 사용 합니다.
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

예를 들어 다음 명령을 사용 하 여 사이트 Redmond에 대 한 핀 덜 모임 참가를 허용 합니다.
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

고정이 아닌 모임 참가 연결이 설정 되어 있는 경우, ConferencingPolicy가 다음과 같이 설정 되도록 하 여 익명 사용자가 전화 걸기를 할 수 없도록 제한 하는 것이 좋습니다.
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)을 참조 하세요.
  

