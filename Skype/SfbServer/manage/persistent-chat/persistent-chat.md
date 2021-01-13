---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
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
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버를 관리하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832888"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리
 
**요약:** 영구 채팅 서버를 관리하는 방법을 비즈니스용 Skype 서버 2015에 대해 자세히 알아보습니다.
  
조직에 대해 영구 채팅 서버를 설정할 때 배포 중에 초기 구성을 지정합니다. 그러나 영구 채팅 서버 지원을 구현하는 방법을 변경하려는 경우도 있습니다. 예를 들어 조직 내의 특정 팀 또는 그룹에 대해 다르게 영구 채팅 서버 지원 및 컨트롤을 설정해야 할 수 있습니다. 이 섹션에서는 영구 채팅 서버 배포를 사용자 지정하는 데 도움이 되는 정보와 절차를 제공합니다. 영구 채팅 서버에 대해 구성할 수 있는 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 2015의 영구 채팅 서버 [계획(Plan for Persistent Chat Server)을 참조하세요.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) 영구 채팅 서버 배포에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015에서](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)영구 채팅 서버 배포를 참조하세요. 

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. Teams에서 동일한 기능을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
  
제어판을 사용하거나 cmdlet을 사용하여 영구 채팅 서버를 Windows PowerShell 있습니다. 
  
제어판을 사용:
  
1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.
    
3. 왼쪽 탐색 모음에서 영구 **채팅을 클릭합니다.**
    
다음 표에는 영구 채팅 Windows PowerShell 사용할 수 있는 cmdlet이 요약되어 있습니다. 사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)
  

|**Cmdlet**|**설명**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |새 범주를 만듭니다.  <br/> |
|Set-CsPersistentChatCategory  <br/> |기존 범주에 대한 설정 구성  <br/> |
|Get-CsPersistentChatCategory  <br/> |범주에 대한 정보 검색  <br/> |
|Remove-CsPersistentChatCategory  <br/> |범주 제거  <br/> |
|New-CsPersistentChatRoom  <br/> |새 대화방을 만듭니다.  <br/> |
|Set-CsPersistentChatRoom  <br/> |기존 방에 대한 설정을 구성합니다. 방에 사용자 및 사용자 그룹 할당  <br/> |
|Get-CsPersistentChatRoom  <br/> |방에 대한 정보를 검색합니다.  <br/> |
|Clear-CsPersistentChatRoom  <br/> |방 또는 방의 메시지 지우기  <br/> |
|Remove-CsPersistentChatRoom  <br/> |방 제거  <br/> |
|Remove-CsPersistentChatMessage  <br/> |방에서 메시지 제거  <br/> |
|New-CsPersistentChatAddin  <br/> |새 추가 기능 생성  <br/> |
|Set-CsPersistentChatAddin  <br/> |기존 추가 기능의 설정 구성  <br/> |
|Get-CsPersistentChatAddin  <br/> |추가 기능 관련 정보 검색  <br/> |
|Remove-CsPersistentChatAddin  <br/> |추가 기능 제거  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |준수 구성 설정의 기존 컬렉션을 수정합니다.  <br/> |
|Export-CsPersistentChatData  <br/> |영구 채팅 데이터베이스에서 데이터 내보내기  <br/> |
|Import-CsPersistentChatData  <br/> |이전 버전의 Lync Server에서 내보운 데이터 가져오기  <br/> |
   

