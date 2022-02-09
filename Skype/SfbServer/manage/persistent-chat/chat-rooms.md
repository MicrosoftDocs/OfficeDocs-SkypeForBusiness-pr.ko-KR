---
title: 2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 채팅방 관리
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '요약: 2015년 8월에 영구 채팅 서버 채팅방을 관리하는 비즈니스용 Skype 서버 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 02b933d1fcd73f87ac3d04e0618bae2e03306bfb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398912"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 채팅방 관리
 
**요약:** 2015년 8월에 영구 채팅 서버 채팅방을 관리하는 비즈니스용 Skype 서버 방법을 배워야 합니다.
  
범주를 올바르게 사용하여 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 범주는 채팅방을 만들거나 참가할 수 있는 대상을 정의합니다. 채팅방을 관리하기 전에 비즈니스용 Skype 서버 [2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)의 영구 채팅 범주, 채팅방 및 사용자 역할을 읽고 비즈니스용 Skype 서버 [2015](categories.md)의 영구 채팅 서버에서 범주를 관리해야 합니다.
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요](/microsoftteams/upgrade-start-here). 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

Windows PowerShell 명령줄 인터페이스를 사용하여 채팅방을 구성하고 관리하거나 비즈니스용 Skype 구성원인 경우 비즈니스용 Skype 클라이언트를 사용하여 채팅방을 구성하고 관리할 수 있습니다. 이 항목에서는 명령줄 인터페이스를 사용하여 채팅방을 관리하는 Windows PowerShell 대해 설명합니다. 비즈니스용 Skype 클라이언트를 사용하여 채팅방을 관리하려는 경우 클라이언트 도움말을 참조하세요. 
  
채팅방은 보통과 강당의 두 가지 유형 중 하나일 수 있습니다. 일반 대화방에서는 모든 구성원이 메시지를 게시하고 읽을 수 있습니다. 강당은 발표자만 게시할 수 있지만 모든 사람이 읽을 수 있는 대화방 유형입니다.
  
Who 액세스하고 채팅방을 관리할 수 있는 방법은 다음과 같이 사용자 역할에 따라 다를 수 있습니다.
  
- 사용자는 메시지를 게시하고 읽을 수 있도록 대화방의 구성원이 되어야 합니다.
    
- 발표자는 강당 회의실에 게시할 수 있습니다.
    
- 관리자는 데이터베이스가 너무 크게 증가하지 않도록 방지하기 위해 채팅방에서 이전 콘텐츠(예: 특정 일 수 이전에 게시된 콘텐츠)를 삭제할 수 있습니다. 관리자는 특정 채팅방에 대해 부적절한 것으로 간주되는 메시지를 제거하거나 바꿀 수도 있습니다.
    
- 메시지 작성자를 포함하여 최종 사용자는 채팅방의 콘텐츠를 삭제할 수 없습니다.
    
- 채팅방 관리자는 방을 사용할 수 없는 경우를 포함하여 모든 채팅방 속성을 변경할 수 있습니다. 그러나 관리자는 방을 삭제하거나 방의 범주를 변경할 수 없습니다. 
    
- 채팅방을 만든 후에 관리자만 삭제할 수 있습니다.
    
다음 cmdlet을 사용하여 채팅방을 구성하고 관리할 Windows PowerShell 있습니다.
  

|**Cmdlet**|**설명**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |새 대화방 만들기  <br/> |
|Set-CsPersistentChatRoom  <br/> |기존 방에 대한 설정을 구성합니다. 방에 사용자 및 사용자 그룹 할당  <br/> |
|Get-CsPersistentChatRoom  <br/> |방에 대한 정보 검색  <br/> |
|Clear-CsPersistentChatRoom  <br/> |방 또는 메시지 지우기  <br/> |
|Remove-CsPersistentChatRoom  <br/> |방 제거  <br/> |
|Remove-CsPersistentChatMessage  <br/> |방에서 메시지 제거  <br/> |
   
**New-CsPersistentChatRoom** cmdlet을 사용하여 채팅방을 만들고 **Set-CsPersistentChatRoom** cmdlet을 사용하여 채팅방에 사용자를 추가하는 등 기존 채팅방을 구성합니다. 채팅방에 대해 다음 매개 변수를 구성할 수 있습니다.
  
- 사용 안 하게 합니다. 대화방을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다. 
    
- 초대. 대화방 구성원으로 추가될 때 사용자에게 알리는 데 사용되는 대화방 초대를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 상속되는 초대의 기본 설정으로, 채팅방이 속한 범주에 구성된 초대 설정을 채택했습니다. 채팅방 수준에서 초대 설정을 false로 구성하면 범주 설정을 에지할 수 있습니다. 
    
- 개인 정보. 대화방이 열기, 닫기 또는 비밀인지를 지정할 수 있습니다. 열려 있는 방은 누구나 검색하고 액세스할 수 있습니다. 모든 사람이 닫힌 방을 검색할 수 있지만 구성원만 액세스할 수 있습니다. 비밀 방은 방의 구성원만 검색하고 액세스할 수 있습니다. 기본적으로 각 새 방은 처음에 Closed로 구성됩니다.
    
- 유형. 대화방이 구성원이 게시한 메시지를 허용하는 일반 방인지 또는 발표자만 게시한 메시지를 수락하는 강당 방인지를 지정할 수 있습니다.
    
- Addin. 이전에 구성한 추가 기능을 채팅방에 연결하여 참가하는 동안 구성원이 URL 콘텐츠를 볼 수 있습니다.
    
**Set-CsPersistentChatRoom** cmdlet을 사용하면 위의 매개 변수 외에도 다음과 같이 사용자를 채팅방에 할당할 수 있습니다.
  
- 구성원. 대화방의 구성원 자격을 구성합니다. 사용자의 SIP 주소를 지정하여 단일 cmdlet을 사용하여 개별 또는 여러 구성원을 추가하거나 제거할 수 있습니다. 사용자를 대량으로 추가할 수 있도록 Active Directory 조직 구성 단위 또는 메일 그룹을 지정할 수도 있습니다.
    
- 관리자. 대화방에 관리자를 할당할 수 있습니다. 관리자에게는 다른 설정과 함께 채팅방 구성원 자격을 정의할 수 있는 권한이 있습니다.
    
- 발표자. 강당 대화방에 발표자를 할당할 수 있습니다. 
    
  모든 매개 변수를 포함한 구문에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015 Management Shell을 참조합니다](../management-shell.md).
  
## <a name="create-a-new-room"></a>새 방 만들기

**New-CsPersistentChatRoom** cmdlet을 사용하여 새 방을 만들 수 있습니다. 예를 들어 다음 명령은 풀 그룹에서 ITChatRoom이라는 새 채팅방을 atl-cs-001.contoso.com. 이 예에서는 채팅방이 IT 범주에 추가됩니다.
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**참고:** 다음 중 하나에 해당하면 PersistentChatPoolFqdn이 필요하지 않습니다. 
  
- 영구 채팅 서버 풀은 하나뿐입니다.
    
- 범주에 풀 FQDN을 제공합니다.
    
- 추가하는 채팅방에 풀 FQDN을 제공합니다.
    
## <a name="configure-an-existing-room"></a>기존 방 구성

**Set-CsPersistentChatRoom** cmdlet을 사용하여 기존 방을 구성할 수 있습니다. 예를 들어 다음 명령은 user1을 구성원 및 발표자로, user2를 testCat Auditorium 방의 관리자로 할당합니다.
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 다음 예제에서는 Active Directory의 NorthAmericaUsers OU에 있는 모든 사용자를 NorthAmerica 대화방에 추가합니다.
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

다음 예제에서는 Finance 메일 그룹의 모든 구성원을 동일한 대화방에 추가합니다.
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>방 사용 또는 사용 안 하도록 설정

영구 채팅방의 주제가 더 이상 관련이 없는 경우 사용자가 대화방을 사용하지 못하도록 만들 수 있습니다. 대화방을 사용하지 않도록 설정하면 모든 구성원이 대화방에서 즉시 연결이 끊어집니다. 대화방을 사용하지 않도록 설정하면 사용자가 대화방에 다시 추가하거나 채팅방 검색에서 채팅방을 찾을 수 없습니다.
  
대화방 기록이 유지되는 경우 채팅방을 사용하지 않도록 설정하면 콘텐츠가 보존됩니다. 그러나 대화방이 비활성화된 상태로 유지되는 동안에는 해당 콘텐츠가 검색에 나타나지 않습니다. 나중에 대화방을 사용하도록 설정하면 사용자가 대화방을 사용하지 않도록 설정하기 전에 게시된 메시지를 검색할 수 있습니다. 채팅방 기록 구성에 대한 자세한 내용은 [Manage categories in Persistent Chat Server in 비즈니스용 Skype 서버 참조하십시오](categories.md). 
  
대화방을 사용하지 않도록 설정하면 해당 구성원 자격 목록 및 기타 설정이 보존됩니다. 관리자는 사용하지 않도록 설정한 방을 사용하도록 설정할 수 있으며 설정을 수동으로 다시 만들 필요가 없습니다.
  
**Set-CsPersistentChatRoom** cmdlet을 사용하고 Disabled 매개 변수를 True로 설정하여 회의실을 사용하지 않도록 설정할 수 있습니다.
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

대화방을 사용하도록 설정하려면 Disabled 매개 변수를 False로 설정하세요.
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>회의실에 대한 정보 얻기

조직에서 사용하도록 구성된 방에 대한 정보를 얻도록 **Get-CsPersistentChatRoom** cmdlet을 사용하면 됩니다.
  
다음 명령은 조직에서 사용하도록 구성된 모든 채팅방에 대한 정보를 반환합니다.
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>방에서 모든 콘텐츠 제거

**Clear-CsPersistentChatRoom** cmdlet을 사용하여 방에서 콘텐츠를 제거할 수 있습니다. 예를 들어 다음 명령은 2015년 3월 1일 또는 그 이전의 채팅방에 추가된 모든 콘텐츠를 영구 채팅방 ITChatRoom에서 제거합니다.
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>방에서 메시지 제거

영구 채팅 데이터베이스에서 메시지를 하나 이상 제거하고 **, 필요한 경우 Remove-CsPersistentChatMessage** cmdlet을 사용하여 메시지를 기본 메시지 또는 관리자 제공 메시지로 바꿀 수 있습니다. 예를 들어 다음 명령은 사용자가 게시한 ITChatRoom 대화방에서 모든 메시지를 kenmyer@contoso.com.
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

다음 예제에서는 제거된 메시지를 더 이상 사용할 수 없습니다.
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>방 제거

**Remove-CsPersistentChatRoom** cmdlet을 사용하여 방을 제거할 수 있습니다.
  
예를 들어 다음 명령은 대화방 RedmondChatRoom을 제거합니다.
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>한 범주에서 다른 범주로 방 이동

대화방 관리자에게 다른 범주  의 작성자 권한이 있는 경우 방을 한 범주에서 다른 범주로 이동할 수 있습니다. 방은 삭제되지 않고 다시 만들어집니다. 데이터베이스 내의 연결에 대한 변경입니다.
  
채팅방 범주를 변경하는 경우는 드물지만 주의해야 합니다. 범주는 해당 채팅방에 대해 허용되는 구성원 자격을 결정하므로 채팅방을 다른 범주로 이동하면 새 범주에 따라 더 이상 지원되지 않는 모든 SACL(시스템 액세스 제어 목록)이 삭제됩니다. 예를 들어 사용자가 방의 구성원이 아니고 새 범주에서 더 이상 허용된 구성원이 아 없는 경우 방 구성원이 수정되고 사용자가 방에서 제거됩니다.
  

