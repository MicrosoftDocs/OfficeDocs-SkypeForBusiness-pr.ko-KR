---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 대화방에 대한 추가 기능을 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815084"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 대화방에 대한 추가 기능을 구성하는 방법을 자세히 알아보고,
  
추가 기능에서는 URL을 대화방과 연결하여 방 내 환경을 확장하는 데 사용됩니다. 이러한 URL은 클라이언트 대화 extensibility 창에 표시됩니다. 일반적인 추가 기능으로는 주식 시세 표시가 대화방에 게시될 때 가로채고 주식 기록을 Extensibility(Extensibility) 창에 표시하는 Silverlight 응용 프로그램을 지정하는 URL이 있을 수 있습니다. 또 다른 예로는 OneNote 2013 URL을 채팅방에 추가 기능으로 포함하여 "관심 항목" 또는 "오늘의 항목"과 같은 일부 공유 컨텍스트를 포함하는 경우를 들 수 있습니다.
  
 사용자가 클라이언트에서 추가 기능을 볼 수 있도록 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 대화방 관리자 또는 작성자는 채팅방을 추가 기능과 연결해야 합니다.
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. Teams에서 동일한 기능을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>제어판을 사용하여 채팅방에 대한 추가 기능 구성

제어판을 사용하여 채팅방에 대한 추가 기능을 구성합니다.
  
1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.
    
3. 왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **추가 기능** 을 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.
    
4. **추가 기능** 페이지에서 **새로 만들기** 를 클릭합니다.
    
5. 서비스 **선택에서** 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다. 추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.
    
6. **새 추가 기능** 에서 다음을 수행합니다.
    
   - **이름** 에서 새 추가 기능의 이름을 지정합니다.
    
   - **URL** 에서 추가 기능과 연결할 URL을 지정합니다. URL은 http 및 https 프로토콜로 제한됩니다.
    
7. **커밋** 을 클릭합니다.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>다음을 사용하여 추가 기능 Windows PowerShell

다음 cmdlet을 사용하여 채팅방에 대한 추가 기능을 Windows PowerShell 있습니다. 사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)
  

|**Cmdlet**|**설명**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |새 추가 기능 만들기  <br/> |
|Set-CsPersistentChatAddin  <br/> |기존 추가 기능의 설정 구성  <br/> |
|Get-CsPersistentChatAddin  <br/> |추가 기능 관련 정보 검색  <br/> |
|Remove-CsPersistentChatAddin  <br/> |추가 기능 제거  <br/> |
   
### <a name="create-a-new-add-in"></a>새 추가 기능 만들기

**New-CsPersistentChatAddin cmdlet을** 사용하여 새 추가 기능을 만들 수 있습니다.
  
예를 들어 다음 명령은 풀 이름 ITPersistentChatAddin을 사용하여 새 추가 기능을 atl-cs-001.contoso.com. URL 매개 변수와 매개 변수 값은 추가 기능 웹 페이지 위치를 http://atl-cs-001.contoso.com/itchat 지정합니다.
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>기존 추가 기능의 설정 구성

**Set-CsPersistentChatAddIn** cmdlet을 사용하여 기존 추가 기능의 설정을 구성할 수 있습니다. 예를 들어 다음 명령은 영구 채팅 추가 기능 ITPersistentChatAddin에 할당된 URL을 수정합니다. 이 경우 URL이 다음으로 변경됩니다. http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>추가 기능 관련 정보 검색

**Get-CsPersistentChatAddin cmdlet을** 사용하여 추가 기능 관련 정보를 얻을 수 있습니다. 예를 들어 다음 명령은 조직에서 사용하도록 구성된 모든 영구 채팅 추가 기능의 정보를 반환합니다.
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>추가 기능 제거

**Remove-CsPersistentChatAddIn** cmdlet을 사용하여 추가 기능을 제거할 수 있습니다. 예를 들어 다음 명령은 풀에서 찾은 영구 채팅 추가 기능 ITChatAddin을 atl-cs-001.contoso.com.
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


