---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: cd3d207816f352a33fb3fd228e7249d9e5d836b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818609"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 만들기
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법에 대해 알아봅니다.
  
비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 만들 수 있습니다.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 만들기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.
    
4. **모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
    - 사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다. 사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다. 사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
    - 풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다. 서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다. 결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.
    
5. 대기실를 통해 PSTN (공개 교환 전화 네트워크)에서 전화 접속 하는 참가자를 라우팅하려면 **pstn 발신자의 로비 사용 안 함** 확인란의 선택을 취소 합니다. 기본적으로 PSTN에서 전화를 거는 참가자는 모임으로 직접 이동 합니다.
    
6. 모임에서 발표자가 될 수 있는 사용자를 구성 하려면 **발표자로 지정**에서 다음 중 하나를 수행 합니다.
    
   - 이끌이 이외의 사용자가 발표자가 될 수 없도록 하려면 **없음**을 클릭 합니다.
    
   - 조직의 구성원 인 참가자만 발표자로 지정할 수 있도록 하려면 **회사**를 클릭 합니다. 이는 기본 설정입니다.
    
   - 모든 참가자가 발표자로 지정 하도록 허용 하려면 **모든 사용자**를 클릭 합니다.
    
7. 모임을 예약할 때 주최자가 회의 유형을 선택 하도록 하려면 **기본적으로 지정 된 회의 유형** 확인란의 선택을 취소 합니다. 기본적으로 회의 유형은 자동으로 지정 됩니다.
    
8. 익명 (인증 되지 않은) 사용자가 자동으로 허용 되지 않도록 하려면 **기본적으로 익명 사용자** 허용 확인란의 선택을 취소 합니다. 기본적으로 익명 사용자는 자동으로 모임에 참석할 수 있습니다.
    
9. 참가자에 게 전송 되는 모임 초대를 사용자 지정 하려면 다음을 실행 합니다. Url 및 사용자 지정 바닥글 텍스트에 대 한 최대 길이는 1KB 것을 참고 하세요. **도움말 URL**을 제외한 사용자 지정에 대 한 값을 지정 하지 않으면 모임에 포함 되지 않습니다. 사용자 지정 도움말 URL을 포함 하지 않으면 비즈니스용 Skype에 대 한 기본 도움말 URL이 초대에 표시 됩니다. 
    
   - 모임 초대에 표시 되는 로고를 사용자 지정 하려면 **로고 URL**에 로고의 위치를 입력 합니다. 로고는 188 x 30 픽셀 크기의 GIF 또는 JPG 이미지 여야 합니다. 
    
   - 모임 초대에 표시 되는 도움말 텍스트를 사용자 지정 하려면 **도움말 URL**에 도움말 텍스트의 위치를 입력 합니다.
    
   - 모임 초대에 표시 되는 법률 텍스트를 사용자 지정 하려면 **legal 텍스트 URL**에 법률 텍스트의 위치를 입력 합니다.
    
   - 모임 초대에 표시 되는 바닥글 텍스트를 사용자 지정 하려면 **사용자 지정 바닥글 텍스트**에 텍스트를 입력 합니다.
    
10. **커밋**을 클릭합니다.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 만들기

모임 구성 설정을 만들려면 **새 CsMeetingConfiguration** cmdlet을 사용 합니다.
  
다음 명령은 Redmond 사이트에 대 한 새 모임 구성 설정 집합을 만듭니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 모임 구성 설정에는 해당 속성에 대 한 기본값이 사용 됩니다.
  
다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어 기본적으로 모든 사용자가 발표자로 모임에 참가 하도록 허용 하는 모임 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

여러 매개 변수를 포함 하 여 여러 속성 값을 설정할 수 있습니다. 예를 들어 다음 명령은 모든 사람을 발표자로 모임에 입장할, PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기 하도록 강제 합니다.
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

전체 매개 변수 목록을 비롯 한 자세한 내용은 [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)를 참조 하세요.
  

