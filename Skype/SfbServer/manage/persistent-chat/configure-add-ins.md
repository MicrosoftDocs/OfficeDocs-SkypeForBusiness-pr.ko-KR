---
title: 영구 채팅방에 대해 추가 기능 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버 채팅방의 추가 기능을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 4614387149eb264d5c59ca7a0642408093312a18
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197872"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>영구 채팅방에 대해 추가 기능 구성
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 채팅방의 추가 기능을 구성 하는 방법에 대해 알아봅니다.
  
추가 기능은 Url을 채팅방과 연결 하 여 채팅방의 환경을 확장 하는 데 사용 됩니다. 이러한 Url은 클라이언트 대화 확장 창에 표시 됩니다. 일반적인 추가 기능에는 주식 시세 표시기가 채팅방에 게시 되는 경우를 가로채는 Silverlight 응용 프로그램을 가리키는 URL이 포함 될 수 있으며, 확장성 창에 주식 기록이 표시 됩니다. 다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.
  
 사용자가 클라이언트에서 추가 기능을 볼 수 있으려면 먼저 등록 된 추가 기능 목록에 추가 기능을 추가 하 고 채팅방 관리자 또는 작성자가 채팅방과 추가 기능을 연결 해야 합니다.
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>제어판을 사용 하 여 채팅방에 대 한 추가 기능 구성

제어판을 사용 하 여 채팅방의 추가 기능을 구성 하려면 다음을 수행 합니다.
  
1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.
    
2. **시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.
    
3. 왼쪽 탐색 모음에서 **영구 채팅**을 클릭한 다음 **추가 기능**을 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.
    
4. **추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.
    
5. **서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 추가 기능은 한 풀에서 다른 풀로 이동하거나 여러 풀 간에 공유할 수 없습니다.
    
6. **새 추가 기능**에서 다음을 수행합니다.
    
   - **이름**에 새 추가 기능 이름을 지정합니다.
    
   - **URL**에 추가 기능과 연결할 URL을 지정합니다. Url은 http 및 https 프로토콜로 제한 됩니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 추가 기능 구성

다음 Windows PowerShell cmdlet을 사용 하 여 채팅방에 대 한 추가 기능을 구성할 수 있습니다. 사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.
  

|**은**|**설명**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |새 추가 기능 만들기  <br/> |
|Set-CsPersistentChatAddin  <br/> |기존 추가 기능에 대 한 설정 구성  <br/> |
|Get-CsPersistentChatAddin  <br/> |추가 기능에 대 한 정보 검색  <br/> |
|제거-CsPersistentChatAddin  <br/> |추가 기능 제거  <br/> |
   
### <a name="create-a-new-add-in"></a>새 추가 기능 만들기

**새 CsPersistentChatAddin** cmdlet을 사용 하 여 새 추가 기능을 만들 수 있습니다.
  
예를 들어 다음 명령을 사용 하 여 풀 atl-cs-001.contoso.com에 대 한 새 추가 기능 (이름 ITPersistentChatAddin)을 만듭니다. URL 매개 변수 및 매개 변수 값 http://atl-cs-001.contoso.com/itchat 은 추가 기능 웹 페이지의 위치를 지정 합니다.
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>기존 추가 기능에 대 한 설정 구성

**Set-CsPersistentChatAddIn** cmdlet을 사용 하 여 기존 추가 기능에 대 한 설정을 구성할 수 있습니다. 예를 들어 다음 명령은 영구 채팅 추가 기능 ITPersistentChatAddin에 할당 된 URL을 수정 합니다. 이 경우에는 URL이 다음과 같이 변경 됩니다.http://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>추가 기능에 대 한 정보 검색

**CsPersistentChatAddin** cmdlet을 사용 하 여 추가 기능에 대 한 정보를 얻을 수 있습니다. 예를 들어 다음 명령은 조직에서 사용 하도록 구성 된 모든 영구 채팅 추가 기능에 대 한 정보를 반환 합니다.
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>추가 기능 제거

**제거-CsPersistentChatAddIn** cmdlet을 사용 하 여 추가 기능을 제거할 수 있습니다. 예를 들어 다음 명령은 풀 atl-cs-001.contoso.com에서 찾을 수 있는 영구 채팅 추가 기능을 제거 합니다.
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


