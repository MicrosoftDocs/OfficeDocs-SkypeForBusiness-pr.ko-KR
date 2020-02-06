---
title: 영구 채팅 서버의 채팅방 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 채팅방을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: b19b230aa4b83e9bd1b84b6be50a27cf665de788
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817284"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버의 채팅방 관리
 
**요약:** 비즈니스용 Skype Server 2015에서 영구 채팅 서버 채팅방을 관리 하는 방법에 대해 알아봅니다.
  
다양 한 범주를 사용 하 여 채팅방을 만들고 관리 하는 것이 훨씬 쉬워졌습니다. 범주는 채팅방을 만들거나 참가할 수 있는 사람을 정의 합니다. 채팅방을 관리 하기 전에 비즈니스용 [Skype server 2015의 영구 채팅 범주, 채팅방 및 사용자 역할](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) 을 읽고 비즈니스용 [skype Server 2015에서 영구 채팅 서버의 범주를 관리](categories.md)하세요.
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

Windows PowerShell 명령줄 인터페이스를 사용 하거나 채팅방의 구성원 인 경우 비즈니스용 Skype 클라이언트를 사용 하 여 채팅방을 구성 하 고 관리할 수 있습니다. 이 항목에서는 Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 관리 하는 방법에 대해 설명 합니다. 비즈니스용 Skype 클라이언트를 사용 하 여 채팅방을 관리 하려는 경우 클라이언트 도움말을 참조 하세요. 
  
채팅방은 일반 및 Auditorium 두 가지 유형 중 하나가 될 수 있습니다. 일반 채팅방에서 모든 구성원이 메시지를 게시 하 고 읽을 수 있습니다. Auditorium는 발표자만 게시할 수 있는 채팅방의 한 종류로, 모든 사람이 읽을 수 있습니다.
  
채팅방을 액세스 하 고 관리 하는 사람은 다음과 같이 사용자 역할에 따라 달라 집니다.
  
- 사용자가 메시지를 게시 하 고 읽을 수 있으려면 채팅방의 구성원 이어야 합니다.
    
- 발표자는 Auditorium 채팅방에 게시할 수 있습니다.
    
- 관리자는 모든 채팅방에서 이전 콘텐츠 (예: 특정 날짜 이전에 게시 된 콘텐츠)를 삭제 하 여 데이터베이스가 너무 커지지 않도록 할 수 있습니다. 또한 관리자는 특정 채팅방에 적합 하지 않은 것으로 간주 되는 메시지를 제거 하거나 바꿀 수 있습니다.
    
- 메시지 작성자를 비롯 한 최종 사용자는 채팅방에서 콘텐츠를 삭제할 수 없습니다.
    
- 채팅방 관리자는 채팅방을 사용 하지 않도록 설정 하는 등의 모든 채팅방 속성을 변경할 수 있습니다. 그러나, 관리자는 채팅방을 삭제 하거나 룸 범주를 변경할 수 없습니다. 
    
- 관리자만이 채팅방을 만든 후 삭제할 수 있습니다.
    
다음 Windows PowerShell cmdlet을 사용 하 여 채팅방을 구성 하 고 관리할 수 있습니다.
  

|**은**|**설명**|
|:-----|:-----|
|새로운 CsPersistentChatRoom  <br/> |새 채팅방 만들기  <br/> |
|Set-CsPersistentChatRoom  <br/> |기존 방에 대 한 설정을 구성 합니다. 룸에 사용자 및 사용자 그룹 지정  <br/> |
|Get-CsPersistentChatRoom  <br/> |채팅방에 대 한 정보 검색  <br/> |
|일반-CsPersistentChatRoom  <br/> |채팅방에서 채팅방 또는 메시지 지우기  <br/> |
|제거-CsPersistentChatRoom  <br/> |채팅방 제거  <br/> |
|제거-CsPersistentChatMessage  <br/> |채팅방에서 메시지 제거  <br/> |
   
**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방에 사용자를 추가 하는 것을 포함 하 여 기존 채팅방을 구성 하는 대화방 및 **집합-CsPersistentChatRoom** cmdlet을 만듭니다. 채팅방에 대해 다음 매개 변수를 구성할 수 있습니다.
  
- 비활성화. 채팅방을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 
    
- 보도록. 채팅방 구성원으로 추가 되었을 때 사용자에 게 알리는 데 사용 되는 채팅방 초대를 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 초대에 대 한 기본 설정으로 채팅 채팅방에서 자신이 속한 범주에 구성 된 초대 설정을 적용 합니다. 채팅방 수준에서 초대 설정을 false로 구성 하면 범주 설정을 재정의할 수 있습니다. 
    
- 프라이버시. 채팅방이 열려 있는지, 닫혔는지, 비밀 인지를 지정할 수 있습니다. 모든 사용자가 열거나 회의실을 검색 하 고 액세스할 수 있습니다. 모든 사용자가 채팅방을 검색할 수 있지만 구성원만 액세스할 수 있습니다. 채팅방의 구성원만 비밀 방을 검색 하 고 액세스할 수 있습니다. 기본적으로 새 공간은 모두 닫힌 것으로 초기 구성 됩니다.
    
- 입력할. 채팅방이 구성원이 게시 한 메시지를 허용 하는 일반 채팅방 인지 아니면 발표자만 게시 한 메시지를 허용 하는 Auditorium 채팅방을 지정 하는 데 사용 됩니다.
    
- 기능이. 이전에 구성한 추가 기능을 채팅방과 연결 하 여 참여 중에 구성원이 URL 콘텐츠를 볼 수 있도록 합니다.
    
위의 매개 변수 외에도 **CsPersistentChatRoom** cmdlet을 사용 하 여 사용자를 채팅방에 다음과 같이 할당할 수 있습니다.
  
- 멤버만. 채팅방에 대 한 구성원 자격을 구성 합니다. 사용자의 SIP 주소를 지정 하 여 단일 cmdlet을 사용 하 여 개인 또는 다중 구성원을 추가 하거나 제거할 수 있습니다. 사용자를 대량으로 추가 하는 것을 허용 하기 위해 Active Directory 조직 구성 단위 또는 메일 그룹도 지정할 수 있습니다.
    
- Review. 채팅방에 관리자를 지정할 수 있습니다. 관리자는 다른 설정에 따라 채팅방의 구성원을 정의할 수 있는 권한을 갖습니다.
    
- 명의. Auditorium 채팅방에 발표자를 배정할 수 있습니다. 
    
  모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.
  
## <a name="create-a-new-room"></a>새 채팅방 만들기

**새 CsPersistentChatRoom** cmdlet을 사용 하 여 새 방을 만들 수 있습니다. 예를 들어 다음 명령은 pool atl-cs-001.contoso.com에서 새 채팅방을 만듭니다. 이 예제에서는 채팅방이 IT 범주에 추가 됩니다.
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**참고:** 다음 중 하나가 참이 면 PersistentChatPoolFqdn 필요 하지 않습니다. 
  
- 영구 채팅 서버 풀이 하나 밖에 없습니다.
    
- 범주에 풀 FQDN을 제공 합니다.
    
- 공간을 추가 하는 풀 FQDN을 제공 합니다.
    
## <a name="configure-an-existing-room"></a>기존 채팅방 구성

**Set-CsPersistentChatRoom** cmdlet을 사용 하 여 기존 방을 구성할 수 있습니다. 예를 들어 다음 명령은 testCat Auditorium 방에 대해 구성원 및 발표자로 user1을 할당 하 고 관리자로 서,이를 이름으로 지정 합니다.
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 다음 예에서는 active Directory의 NorthAmericaUsers OU에 있는 모든 사용자를 NorthAmerica 채팅방에 추가 합니다.
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

다음 예에서는 재무 메일 그룹의 모든 구성원을 같은 채팅방에 추가 합니다.
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>회의실을 사용 하지 않거나 사용 하도록 설정

영구 채팅방의 항목이 더 이상 관련이 없다면 사용자가 채팅방을 사용 하지 않도록 설정할 수 있습니다. 채팅방을 사용 하지 않도록 설정 하면 모든 구성원이 채팅방에서 바로 연결이 해제 됩니다. 채팅방을 사용 하지 않도록 설정한 후에는 사용자가 다시 참가 하거나 채팅방 검색에서 찾을 수 없습니다.
  
채팅방의 기록이 유지 되는 경우 채팅방을 사용 하지 않도록 설정한 경우 콘텐츠가 보존 됩니다. 그러나 대화방을 사용할 수 없는 상태로 유지 하는 동안에는 검색에 해당 콘텐츠가 표시 되지 않습니다. 나중에 채팅방을 사용 하도록 설정 하는 경우 사용자는 채팅방을 사용 하지 않도록 설정 하기 전에 게시 된 메시지를 검색할 수 있습니다. 채팅방 기록 구성에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버의 범주 관리](categories.md)를 참조 하세요. 
  
채팅방을 사용 하지 않도록 설정한 경우, 해당 채팅방의 회원 가입 목록 및 기타 설정이 유지 됩니다. 관리자는 사용 하지 않도록 설정 된 채팅방을 사용할 수 있으며 설정을 수동으로 다시 만들 필요가 없습니다.
  
**CsPersistentChatRoom** cmdlet을 사용 하 고 Disabled 매개 변수를 True로 설정 하 여 채팅방을 사용 하지 않도록 설정할 수 있습니다.
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

채팅방을 사용 하도록 설정 하려면 Disabled 매개 변수를 False로 설정 합니다.
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>채팅방에 대 한 정보 가져오기

조직에서 사용 하도록 구성 된 채팅방에 대 한 정보를 얻으려면 **CsPersistentChatRoom** cmdlet을 사용 하면 됩니다.
  
다음 명령은 조직에서 사용 하도록 구성 된 모든 채팅방에 대 한 정보를 반환 합니다.
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>룸에서 모든 콘텐츠 제거

**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방에서 콘텐츠를 제거할 수 있습니다. 예를 들어 다음 명령은 2015 년 3 월 1 일 이전에 룸에 추가 된 영구 채팅방 공간에서 모든 콘텐츠를 제거 합니다.
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>채팅방에서 메시지 제거

영구 채팅 데이터베이스에서 하나 이상의 메시지를 제거 하 고 필요에 따라 **CsPersistentChatMessage** cmdlet을 사용 하 여 메시지를 기본 메시지 또는 관리자가 제공한 메시지로 바꿀 수 있습니다. 예를 들어 다음 명령을 사용 하 여 사용자 kenmyer@contoso.com에 의해 게시 된 모든 메시지를 It 채팅방 채팅방에서 제거 합니다.
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

다음 예제에서는 제거 된 메시지를 메시지가 더 이상 사용할 수 없는 메모로 바꿉니다.
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>채팅방 제거

**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방을 제거할 수 있습니다.
  
예를 들어 다음 명령은 채팅방 RedmondChatRoom를 제거 합니다.
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>한 범주에서 다른 범주로 채팅방 이동

채팅방 관리자에 다른 범주에 대 한 **작성자** 권한이 있는 경우 한 범주에서 다른 범주로 방을 이동할 수 있습니다. 룸은 삭제 되었다가 다시 생성 되지 않습니다. 데이터베이스 내의 연결을 변경 하는 것입니다.
  
채팅방 범주를 변경 하는 작업은 거의 필요 하지 않으며 주의 해야 합니다. 범주는 채팅방에 대해 허용 된 구성원 자격을 결정 하므로 채팅방을 다른 범주로 이동 하면 새 범주에서 더 이상 지원 되지 않는 모든 Sacl (시스템 액세스 제어 목록)이 제거 됩니다. 예를 들어 사용자가 채팅방의 구성원이 고 더 이상 새 범주에 허용 되지 않는 경우 룸 구성원 자격이 수정 되 고 사용자가 채팅방에서 제거 됩니다.
  

