---
title: 영구 채팅 서버의 범주 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: f0c85c2246c85c93f96e6c13cef0a5d4360213cb
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992003"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버의 범주 관리
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 범주를 관리 하는 방법에 대해 알아봅니다.
  
범주는 채팅방을 구성 하는 논리적 구조입니다. 범주는 채팅방을 만들거나 참가할 수 있는 사용자 및 사용자 그룹을 제어 하는 기본 Acl (액세스 제어 목록) 집합을 정의 합니다. 채팅방 범주에는 채팅방이 들어 있지만 다른 범주는 포함 되지 않습니다. 각 범주는 Name과 Description과 같은 메타데이터를 사용해서 해당 콘텐츠를 기술합니다. 범주에는 자신에 게 속하는 채팅방의 동작을 제어 하기 위해 설정할 수 있는 속성이 있습니다. 예를 들어 채팅방에서 초대 또는 파일 업로드를 허용 하는지 여부 또는 채팅 기록을 포함할 수 있습니다. 
  
다양 한 범주를 사용 하 여 채팅방을 만들고 관리 하는 것이 훨씬 쉬워졌습니다. 영구 채팅 서버 관리자는 각 범주에 대해 AllowedMembers 및 작성자를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 예를 들어 범주의 AllowedMembers를 contoso.com로 설정한 경우 Contoso의 모든 그룹 또는 사용자를 해당 범주의 채팅방에 추가할 수 있습니다. 범주에 허용 되는 구성원을 Sales로 설정한 경우이 메일 그룹의 그룹과 사용자만 구성원으로 추가 하 여 해당 범주의 채팅방을 이동할 수 있습니다. 작성자 속성을 사용 하 여 해당 범주에서 채팅방을 만들 수 있는 사람을 제어 합니다. 채팅방을 만든 후에는 AllowedMembers 그룹의 모든 사용자를 해당 채팅방에서 진행 중인 관리 작업에 대 한 관리자로 지정할 수 있습니다 (예: 구성원 변경 및 승인).
  
범주에 대해 AllowedMembers 및 작성자를 정의 하면 다음과 같은 이점이 있습니다.
  
- 이 범주의 모든 채팅방은 범주 수준에 설정 된 제한 사항에 의해 바인딩됩니다. 이 방법을 사용 하 여 비즈니스 요구 및 액세스 정책에 따라 채팅방을 구분할 수 있습니다.
    
- 작성자 목록에 있는 사용자는 해당 범주에 새 채팅방을 만들 수 있습니다. 조직에서 제한 된 인원의 사용자가 채팅방을 만들 수 있는 시스템을 구현 하려는 경우이 컨트롤을 사용 하 여 해당 요구 사항을 충족 시킬 수 있습니다. 
    
범주에 대 한 작성자로 식별 된 사용자, 조직 구성 단위 (Ou) 및 사용자 그룹은 범주에서 방을 만들 수 있는 개인과 그룹 뿐입니다. 범주를 만든 후에는 범주의 AllowedMembers 목록에서 사용자, Ou 및 사용자 그룹을 선택 하 여 채팅방에 관리 하 고 참여할 수 있습니다. 
  
범주를 구성 하기 전에 [비즈니스용 Skype 서버 2015의 영구 채팅 범주, 채팅방, 사용자 역할](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)을 읽어 보세요.
  
제어판을 사용 하거나 Windows PowerShell cmdlet을 사용 하 여 범주를 구성 하 고 관리할 수 있습니다.

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>제어판을 사용 하 여 범주 구성

1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.
    
2. **시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.
    
3. 왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **범주**를 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.
    
4. **범주** 페이지에서 **새로 만들기** 또는 **편집**을 클릭합니다.
    
5. **서비스 선택**에서 범주가 생성 되어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 이 서비스는 영구 채팅 클라이언트가 범주가 속해 있는 풀을 식별 하는 데 사용 하는 영구 채팅 서버 풀입니다. 범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 풀로 이동 하거나 공유할 수 없습니다.
    
6. **새 범주**에서 다음을 수행합니다.
    
   - **이름**에 새로운 채팅방 범주에 대한 이름을 지정합니다.
    
   - **설명**에 채팅방 범주에 대한 자세한 설명을 제공합니다(예: 한미 교역에 대한 채팅방 범주).
    
   - 이 범주에 속한 채팅방에 대해 초대를 사용할 수 있는지 여부를 제어 하려면 **초대 사용** 확인란을 선택 하거나 선택을 취소 합니다. 선택 하는 경우이 범주의 채팅방에서 초대를 보내거나 해제할 수 있습니다. 이 확인란을 선택 취소 하면이 범주의 채팅방에서 초대를 할 수 없습니다. 룸에 대 한 초대가 있는 경우 룸에 새 구성원을 추가할 때 영구 채팅 클라이언트에서 새 룸에 대 한 알림을 받습니다.
    
   - 이 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 확인란을 선택하면 이 범주의 채팅방에서 파일 업로드를 설정 또는 해제할 수 있으며, 확인란의 선택을 취소하면 이 범주의 채팅방에서 파일 업로드를 사용할 수 없습니다.
    
   - 채팅 기록을 제어 하려면 **채팅 기록 사용** 확인란을 선택 하거나 선택을 취소 합니다. 확인란을 선택하면 채팅방 채팅이 영구적으로 저장되고, 그렇지 않으면 채팅 메시지가 저장되지 않습니다. 준수 기능이 설정된 경우 채팅방 채팅이 준수 기능으로 저장되지만 사용자가 이전 메시지에 액세스할 수 없습니다. 이 옵션은 채팅 기록이 필요 하지 않은 실시간 ad hoc 공동 작업에 대해 지정 된 채팅방에 사용할 수 있습니다.
    
7. **범주 편집**에서 다음을 수행합니다.
    
   - **구성원 자격**의 허용 된 **구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 추가 하거나 제거 하 여 범주에 속하는 채팅방의 구성원으로 추가할 수 있도록 허용 합니다. 특정 범주에서 허용된 계정은 채팅방의 구성원만 디렉터리에서 채팅방을 검색할 수 있도록 채팅방이 숨겨져 있지 않은 한 해당 범주에서 채팅방을 검색할 수 있습니다.
    
   - **구성원 자격**의 거부 된 **구성원** 섹션에서 룸에서 거부 되는 구성원과 연결 된 사용자 및 기타 Active Directory 주도자를 추가 하거나 제거 합니다.
    
   - **멤버 자격**의 **작성자** 섹션에서 해당 범주에 대 한 작성자와 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다. 작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 지정할 권한이 있는 사용자입니다.
    
8. **커밋**을 클릭합니다.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 범주 구성

다음 Windows PowerShell cmdlet을 사용 하 여 범주를 구성할 수 있습니다.
  

|**은**|**설명**|
|:-----|:-----|
|새로운 CsPersistentChatCategory  <br/> |새 범주 만들기  <br/> |
|Set-CsPersistentChatCategory  <br/> |기존 범주에 대 한 설정 구성  <br/> |
|Get-CsPersistentChatCategory  <br/> |범주에 대 한 정보 검색  <br/> |
|제거-CsPersistentChatCategory  <br/> |범주 제거  <br/> |
   
범주에 대해 다음 매개 변수를 구성할 수 있습니다.
  
- EnableFileUpload. 범주에 있는 채팅방에 파일 업로드를 허용 합니다.
    
- 초대장을 EnableInvitations 범주에 대 한 초대를 사용 하도록 설정 합니다. AllowedMembers 목록의 사용자는 새 채팅방을 만들 때 새 채팅방에 참가 하기 위한 초대를 자동으로 받습니다.
    
- ChatHistory. 채팅 기록 기능을 사용 하거나 사용 하지 않도록 설정 합니다.
    
- 제작자. 범주 내에서 채팅방을 만들 수 있는 사용자를 지정 합니다.
    
- AllowedMembers. 범주 내에서 채팅방에 액세스할 수 있는 사용자를 지정 합니다.
    
- DeniedMembers. 범주 내에서 채팅방에 액세스할 수 없는 사용자를 나열 합니다.
    
모든 매개 변수를 포함 하 여 cmdlet 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.
  
### <a name="create-a-new-category"></a>새 범주 만들기

**새 CsPersistentChatCategory** cmdlet을 사용 하 여 새 범주를 만들 수 있습니다. 예를 들어 다음 명령은 풀 atl-cs-001.contoso.com에 기술 지원팀 이라는 새 범주를 만듭니다. 이 예제에서는 파일 업로드를 사용할 수 있습니다.
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>기존 범주 구성

**Set-CsPersistentCategory** cmdlet을 사용 하 여 기존 범주를 구성할 수 있습니다.
  
예를 들어 다음 명령은 user1이 AllowedMember이 고 작성자 인 반면, %2은 (는) 범주에 있는 채팅방에 대 한 액세스를 거부 하도록 지정 합니다.
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>범주에 대 한 정보 가져오기

**CsPersistentChatCategory** cmdlet을 사용 하 여 범주에 대 한 정보를 얻을 수 있습니다. 예를 들어 다음 명령은 조직의 모든 영구 채팅 범주에 대 한 정보를 반환 합니다.
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>범주 제거

**제거-CsPersistentChatCategory** cmdlet을 사용 하 여 범주를 제거할 수 있습니다. 범주를 제거 하기 전에 먼저 모든 채팅방을 삭제 하거나 채팅방을 새 범주로 이동 해야 합니다. 예를 들어 다음 명령을 실행 하면 "atl-cs-001-com\helpdesk" 라는 Id를 가진 범주가 제거 됩니다.
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
