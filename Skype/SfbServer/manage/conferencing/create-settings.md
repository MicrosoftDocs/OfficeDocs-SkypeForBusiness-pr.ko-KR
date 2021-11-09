---
title: 모임 구성 설정 만들기 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '요약: 이 문서에서 모임 구성 설정을 만드는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 1b0ba956e467f5b03036d8ef1d1629b4fc4dc517
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850031"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>모임 구성 설정 만들기 비즈니스용 Skype 서버
 
**요약:** 모임 구성 설정을 만드는 방법을 비즈니스용 Skype 서버.
  
모임 구성 설정은 제어판을 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모임 구성 비즈니스용 Skype 서버 만들기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
4. **모임 구성** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다.
    
    - 사이트 수준 정책을 만들려면 **사이트 구성** 을 클릭합니다. **사이트 선택** 검색 필드에 모임 참가 설정을 정의할 사이트의 이름 일부나 전체를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인** 을 클릭합니다.
    
    - 풀 수준 정책을 만들려면 **풀 구성** 을 클릭합니다. **서비스 선택** 검색 필드에 모임 참가 설정을 정의할 풀 서비스의 이름 일부나 전체를 입력합니다. 서비스 결과 목록에서 원하는 풀을 클릭하고 **확인** 을 클릭합니다.
    
5. PSTN(공중 전화망)에서 전화 접속한 참가자를 대기실을 거쳐 라우팅하려면 **PSTN 발신자 바이패스 대기실** 확인란의 선택을 취소합니다. 기본적으로 PSTN에서 전화 접속한 참가자는 모임으로 바로 이동됩니다.
    
6. 모임에서 발표자가 될 수 있는 사용자를 구성하려면 **발표자로 지정** 에서 다음 중 하나를 수행합니다.
    
   - 이끌이 이외의 다른 사용자를 발표자로 지정하지 않으려면 **없음** 을 클릭합니다.
    
   - 조직의 구성원인 참가자만 발표자로 지정하려면 **회사** 를 클릭합니다. 이것이 기본 설정입니다.
    
   - 모든 참가자를 발표자로 지정하려면 **모든 참가자** 를 클릭합니다.
    
7. 모임 예약 시 이끌이가 회의 유형을 선택하도록 하려면 **기본적으로 지정되는 전화 회의 유형** 확인란의 선택을 취소합니다. 회의 유형은 기본적으로 자동으로 지정됩니다.
    
8. 인증되지 않은 익명의 사용자를 자동으로 허용되지 않도록 하려면 **기본적으로 익명 사용자 허용** 확인란의 선택을 취소합니다. 기본적으로 익명 사용자는 모임에 자동으로 허용됩니다.
    
9. 참가자에게 전송된 모임 초대를 사용자 지정하기 위해 다음을 합니다. URL 및 사용자 지정 발자국 텍스트의 최대 길이는 1KB입니다. 도움말 **URL을** 제외하고 사용자 지정에 대한 값을 지정하지 않으면 모임에 포함되지 않습니다. 사용자 지정 도움말 URL을 포함하지 않는 경우 초대에 비즈니스용 Skype 도움말 URL이 표시됩니다. 
    
   - 모임 초대에 나타나는 로고를 사용자 지정하기 위해 로고 **URL에** 로고 위치를 입력합니다. 로고는 크기가 188 x 30픽셀인 GIF 또는 JPG 이미지입니다. 
    
   - 모임 초대에 나타나는 도움말 텍스트를 사용자 지정하기 위해 도움말 **URL에** 도움말 텍스트의 위치를 입력합니다.
    
   - 모임 초대에 나타나는 법적 텍스트를 사용자 지정하기 위해 법률 텍스트 **URL에** 법률 텍스트의 위치를 입력합니다.
    
   - 모임 초대에 나타나는 글자 텍스트를 사용자 지정하는 경우 사용자 지정 발자국 **텍스트에** 텍스트를 입력합니다.
    
10. **커밋** 을 클릭합니다.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모임 구성 비즈니스용 Skype 서버 만들기

모임 구성 설정을 만들하려면 **New-CsMeetingConfiguration** cmdlet을 사용합니다.
  
다음 명령은 Redmond 사이트에 대한 새 모임 구성 설정 집합을 만듭니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

이전 명령에 필수 Identity 매개 변수 외의 매개 변수가 지정되지 않은 경우 새 모임 구성 설정은 모든 속성에 대해 기본값을 사용합니다.
  
다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 기본적으로 모든 사람을 발표자로 지정하는 모임 구성 설정 컬렉션을 만들 때 다음과 같은 명령을 사용합니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

여러 매개 변수를 포함하여 여러 속성 값을 설정할 수 있습니다. 예를 들어 다음 명령은 모든 사용자를 발표자로 인정하고 PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기하게 합니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

전체 매개 변수 목록을 포함하여 자세한 내용은 [New-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)
