---
title: 2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 범주 관리
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '요약: 2015년 8월에 영구 채팅 서버 범주를 관리하는 비즈니스용 Skype 서버 방법을 설명하는 문서입니다.'
ms.openlocfilehash: e9892f032d5af24d1394fddc6965ead6e769472e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776198"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 범주 관리
 
**요약:** 2015년 8월에 영구 채팅 서버 범주를 관리하는 비즈니스용 Skype 서버 방법을 배워야 합니다.
  
범주는 채팅방 구성을 위한 논리적 구조입니다. 범주는 채팅방을 만들거나 채팅방에 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다. 채팅방 범주에는 채팅방이 포함되지만 다른 범주는 포함되지 않습니다. 각 범주는 이름, 설명 등의 메타데이터로 해당 콘텐츠를 설명합니다. 범주에는 범주에 속하는 채팅방의 동작을 제어하기 위해 설정할 수 있는 속성이 있습니다. 예를 들어 채팅방에서 초대 또는 파일 업로드를 허용하는지 또는 채팅 기록을 포함할지 여부 
  
범주를 올바르게 사용하여 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 영구 채팅 서버 관리자는 각 범주에 대해 AllowedMembers 및 Creators를 정의하고 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수 있습니다. 예를 들어 범주의 AllowedMembers를 contoso.com 해당 범주의 채팅방에 구성원으로 Contoso의 모든 그룹 또는 사용자를 추가할 수 있습니다. 범주의 허용 구성원을 Sales로 설정하면 이 메일 그룹의 그룹 및 사용자만 해당 범주의 채팅방에 구성원으로 추가할 수 있습니다. Creators 속성을 사용하면 해당 범주에서 대화방을 만들 수 있는 대상을 제어할 수 있습니다. 채팅방을 만든 후 AllowedMembers 그룹의 모든 사용자가 채팅방의 지속적인 관리 작업(예: 구성원 변경 및 승인)에 대한 관리자로 지정될 수 있습니다.
  
범주에 대해 AllowedMembers 및 Creators를 정의하면 다음과 같은 이점이 있습니다.
  
- 이 범주의 모든 채팅방은 범주 수준에서 설정된 제한에 의해 바인딩됩니다. 이 기능을 사용하여 비즈니스 필요성 및 액세스 정책에 따라 채팅방을 나누는 데 사용할 수 있습니다.
    
- 작성자 목록에 있는 사용자는 해당 범주에 새 대화방을 만들 수 있습니다. 조직의 제한된 수의 직원이 채팅방을 만들 수 있는 시스템을 구현하려는 경우 이 컨트롤을 사용하여 해당 요구 사항을 충족할 수 있습니다. 
    
범주의 작성자로 식별되는 사용자, US(조직 구성 단위) 및 사용자 그룹은 범주에 방을 만들 수 있는 개인 및 그룹뿐입니다. 범주를 만든 후 범주의 AllowedMembers 목록에서 사용자, OUS 및 사용자 그룹을 채팅방 관리자 및 구성원으로 선택하여 채팅방을 관리하고 채팅방에 참가할 수 있습니다. 
  
범주를 구성하기 전에 [2015년](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)8월 에서 영구 채팅 범주, 채팅방 및 사용자 역할을 비즈니스용 Skype 서버 합니다.
  
제어판 또는 cmdlet을 사용하여 범주를 구성하고 관리할 Windows PowerShell 있습니다.

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>제어판을 사용하여 범주 구성

1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 열고 관리 URL을 입력합니다.
    
3. 왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **범주** 를 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.
    
4. **범주** 페이지에서 **새로 만들기** 또는 **편집** 을 클릭합니다.
    
5. 서비스 **선택에서** 범주를 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다. 서비스는 영구 채팅 클라이언트가 범주가 속하는 풀을 식별하는 데 사용하는 영구 채팅 서버 풀입니다. 범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 풀로 이동하거나 공유할 수 없습니다.
    
6. **새 범주** 에서 다음을 수행합니다.
    
   - **이름** 에서 새 방 범주의 이름을 지정합니다.
    
   - **설명** 에서 방 범주의 자세한 설명을 입력합니다(예: Contoso의 방 범주).
    
   - 이 범주에 속하는 대화방에 대해 초대를 사용하도록 설정할 수 있는지 여부를 제어하려면 초대 사용 확인란을 선택하거나 **선택을** 취소합니다. 선택한 경우 이 범주의 방에 초대가 있을 수 있습니다. 선택을 취소하면 이 범주의 방에 초대가 허용되지 않습니다. 채팅방에 초대가 있는 경우 새 구성원이 방에 추가되면 영구 채팅 클라이언트에서 새 채팅방에 대한 알림이 표시됩니다.
    
   - 해당 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 이 확인란을 선택하는 경우 해당 범주의 방에서 파일 업로드를 사용하거나 사용하지 않도록 설정할 수 있습니다. 이 확인란의 선택을 취소하는 경우에는 해당 범주의 방에서 파일을 업로드할 수 없습니다.
    
   - 채팅 기록을 제어하려면 채팅 기록 사용 확인란을 **선택하거나** 선택을 취소합니다. 이 확인란을 선택하는 경우 방의 채팅 내용이 영구적으로 보존되고, 그렇지 않으면 채팅 메시지가 영구적으로 보존되지 않습니다. 준수를 사용하도록 설정한 경우에는 방의 채팅 내용이 준수에 저장되지만 사용자는 이전 메시지에 액세스할 수 없게 됩니다. 이 옵션은 채팅 기록을 유지하지 않고도 실시간으로 진행되는 공동 작업을 위해 지정된 채팅방에 사용할 수 있습니다.
    
7. **범주 편집** 에서 다음을 수행합니다.
    
   - 구성원 **자격의**  허용 구성원 섹션에서 범주에 속하는 채팅방의 구성원으로 추가될 수 있는 사용자 및 기타 Active Directory 도메인 서비스 계정(사용자, 메일 그룹, 조직 구성 단위 등)을 추가하거나 제거합니다. 특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.
    
   - 구성원 **자격의** **거부된** 구성원 섹션에서 방에서 거부되는 구성원과 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.
    
   - 구성원 **자격의** **작성자 섹션에서** 범주의 작성자와 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다. 작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 할당할 권한이 있는 사용자입니다.
    
8. **커밋** 을 클릭합니다.
    
## <a name="configure-categories-by-using-windows-powershell"></a>다음을 사용하여 범주를 Windows PowerShell

다음 cmdlet을 사용하여 범주를 Windows PowerShell 수 있습니다.
  

|**Cmdlet**|**설명**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |새 범주 만들기  <br/> |
|Set-CsPersistentChatCategory  <br/> |기존 범주에 대한 설정 구성  <br/> |
|Get-CsPersistentChatCategory  <br/> |범주에 대한 정보 검색  <br/> |
|Remove-CsPersistentChatCategory  <br/> |범주 제거  <br/> |
   
범주에 대해 다음 매개 변수를 구성할 수 있습니다.
  
- EnableFileUpload. 범주의 채팅방에 파일 업로드를 허용합니다.
    
- EnableInvitations. 범주에 대한 초대를 사용할 수 있습니다. AllowedMembers 목록의 사용자는 새 채팅방을 만들 때 새 채팅방에 참가하도록 초대를 자동으로 받게 됩니다.
    
- ChatHistory. 채팅 기록 기능을 활성화 또는 비활성화합니다.
    
- 작성자. 범주 내에서 대화방을 만들 수 있는 사용자를 지정합니다.
    
- AllowedMembers. 범주 내에서 대화방에 액세스할 수 있는 사용자를 지정합니다.
    
- DeniedMembers. 범주 내에서 채팅방에 액세스할 수 없는 사용자를 나열합니다.
    
모든 매개 변수를 포함하여 cmdlet 구문에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015 Management Shell을 참조하십시오.](../management-shell.md)
  
### <a name="create-a-new-category"></a>새 범주 만들기

**New-CsPersistentChatCategory** cmdlet을 사용하여 새 범주를 만들 수 있습니다. 예를 들어 다음 명령은 풀 풀에 HelpDesk라는 새 범주를 atl-cs-001.contoso.com. 이 예제에서는 파일 업로드를 사용하도록 설정합니다.
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>기존 범주 구성

**Set-CsPersistentCategory** cmdlet을 사용하여 기존 범주를 구성할 수 있습니다.
  
예를 들어 다음 명령은 user1을 AllowedMember 및 Creator로 지정하고, user2는 범주의 방에 액세스할 수 없습니다.
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>범주에 대한 정보 얻기

**Get-CsPersistentChatCategory** cmdlet을 사용하여 범주에 대한 정보를 얻을 수 있습니다. 예를 들어 다음 명령은 조직의 모든 영구 채팅 범주에 대한 정보를 반환합니다.
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>범주 제거

**Remove-CsPersistentChatCategory** cmdlet을 사용하여 범주를 제거할 수 있습니다. 범주를 제거하기 전에 먼저 범주 아래에 있는 모든 채팅방을 삭제하거나 대화방을 새 범주로 이동해야 합니다. 예를 들어 다음 명령은 ID가 "atl-cs-001.contoso.com\helpdesk"인 범주를 제거합니다.
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
