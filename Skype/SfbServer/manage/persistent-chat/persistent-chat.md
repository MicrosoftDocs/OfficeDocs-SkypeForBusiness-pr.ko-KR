---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 1702cc9891c34085f8de269d5e91723378c54ada
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197954"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리 하는 방법에 대해 알아봅니다.
  
조직에 대해 영구 채팅 서버를 설정 하는 경우 배포 중에 초기 구성을 지정 합니다. 그러나 영구 채팅 서버 지원을 구현 하는 방법을 변경 해야 하는 경우도 있을 수 있습니다. 예를 들어 조직 내 특정 팀 또는 그룹에 대해 영구 채팅 서버 지원과 컨트롤을 다르게 설정 해야 할 수 있습니다. 이 섹션에서는 영구 채팅 서버 배포를 사용자 지정 하는 데 도움이 되는 정보와 절차에 대해 설명 합니다. 영구 채팅 서버에 대해 구성할 수 있는 기능 및 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)을 참조 하세요. 영구 채팅 서버 배포에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)를 참조 하세요. 

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 
  
제어판을 사용 하거나 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버를 관리할 수 있습니다. 
  
제어판을 사용 하려면 다음을 실행 합니다.
  
1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.
    
2. **시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.
    
3. 왼쪽 탐색 모음에서 **영구 채팅**을 클릭 합니다.
    
다음 표에는 영구 채팅 서버를 관리 하는 데 사용할 수 있는 Windows PowerShell cmdlet이 요약 되어 있습니다. 사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.
  

|**은**|**설명**|
|:-----|:-----|
|새로운 CsPersistentChatCategory  <br/> |새 범주 만들기  <br/> |
|Set-CsPersistentChatCategory  <br/> |기존 범주에 대 한 설정 구성  <br/> |
|Get-CsPersistentChatCategory  <br/> |범주에 대 한 정보를 검색 합니다.  <br/> |
|제거-CsPersistentChatCategory  <br/> |범주 제거  <br/> |
|새로운 CsPersistentChatRoom  <br/> |새 채팅방을 만듭니다.  <br/> |
|Set-CsPersistentChatRoom  <br/> |기존 채팅방에 대 한 설정을 구성 합니다. 룸에 사용자 및 사용자 그룹 지정  <br/> |
|Get-CsPersistentChatRoom  <br/> |채팅방에 대 한 정보를 검색 합니다.  <br/> |
|일반-CsPersistentChatRoom  <br/> |채팅방 또는 대화방에서 메시지 지우기  <br/> |
|제거-CsPersistentChatRoom  <br/> |채팅방을 제거 합니다.  <br/> |
|제거-CsPersistentChatMessage  <br/> |채팅방에서 메시지를 제거 합니다.  <br/> |
|New-CsPersistentChatAddin  <br/> |새 추가 기능을 만듭니다.  <br/> |
|Set-CsPersistentChatAddin  <br/> |기존 추가 기능에 대 한 설정을 구성 합니다.  <br/> |
|Get-CsPersistentChatAddin  <br/> |추가 기능에 대 한 정보를 검색 합니다.  <br/> |
|제거-CsPersistentChatAddin  <br/> |추가 기능을 제거 합니다.  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |준수 구성 설정의 기존 컬렉션을 수정 합니다.  <br/> |
|Export-CsPersistentChatData  <br/> |영구 채팅 데이터베이스에서 데이터 내보내기  <br/> |
|가져오기-CsPersistentChatData  <br/> |이전 버전의 Lync Server에서 내보낸 데이터를 가져옵니다.  <br/> |
   

