---
title: 2013에서 PIN이 않은 모임 참가 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '요약: 2016년 8월에 PIN이 지원되지 않은 모임 참가 옵션을 구성하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: b6e31c3befbabacac26595ea0cd73d8ca575816013d30f17ae4b2ea785934f28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320210"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>2013에서 PIN이 않은 모임 참가 비즈니스용 Skype 서버
 
**요약:** 2016년 8월 1일부로 설정하여 PIN이 지원되지 않은 모임 참가 옵션을 구성하는 비즈니스용 Skype 서버.
  
전화 접속 발신자는 모임 참가를 시도할 때 CAA(Conference 자동 전화 교환) 서비스는 발표자에 통화가 아직 연결되지 않은 경우&#x2014; 발신자에 리더 PIN을 입력하지 않은 경우 대기실과 다른 보류 펜에 발신자 번호를 배치합니다. PIN 없는 모임 참가 옵션을 사용하면 전화 접속 발신자는 통화의 첫 번째 사용자인 경우에도 리더 PIN을 입력하지 않고도 모임에 참가할 수 있습니다. 
  
이 기능을 구성할 때 다음에 유의하십시오.
  
- 비공개 모임에만 적용됩니다.
    
- PSTN 발신자는 인증된 사용자의 존재 없이 비공개 모임에 계속 참석할 수 있습니다.
    
- 설정이 변경된 후 기존의 모든 비공개 모임과 새 비공개 모임에 적용됩니다.
    
- 이끌이의 사이트 또는 전역 수준에서 사용하도록 설정될 수 있습니다.
    
- 대기실을 무시할 수 있는 사용자에 대한 옵션은 다음 중 하나에 대해 설정할 수 있습니다. 
    
  - **발신자에 대한 조직의 모든 사람이 직접 연결됩니다.**
    
  - **발신자에** 대한 모든 사용자(제한 없음)가 직접 연결됩니다(기본 설정입니다.)
    
- PIN이 연결되지 않은 조인을 사용하도록 구성된 경우 CAA 서비스는 여전히 리더 PIN을 묻는 메시지를 제공합니다. 사용자는 PIN 입력 여부에 따라 모임에 참가할 수 있습니다. 그러나 리더 PIN을 입력할 수 있는 기능을 유지하면 전화 접속 발신자에서 리더로 인증하고 필요한 경우 모임을 관리할 수 있습니다.
    
## <a name="configure-pin-less-meeting-join"></a>PIN이 적은 모임 참가 구성

사용자에 대해 PIN이 아닌 모임 참가를 사용하도록 설정하려면 다음과 같이 AllowAnonymousPstnActivation 매개 변수와 [함께 Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet을 사용합니다.
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

예를 들어 다음 명령은 Redmond 사이트에 대해 PIN이 적은 모임 참가를 사용할 수 있습니다.
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

보안을 위해 PIN이 설정되지된 모임 참가가 설정되어 있는 경우 ConferencingPolicy가 다음과 같이 설정되어 있는지를 보장하여 익명 사용자가 전화를 걸지 못하도록 제한할 수 있습니다.
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

자세한 내용은 [Set-CsConferencingPolicy를 참조하세요.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
