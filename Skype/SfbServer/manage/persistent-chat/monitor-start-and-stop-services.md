---
title: 영구 채팅 서비스 모니터링, 시작, 중지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스를 시작, 중지 및 모니터링 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197956"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>영구 채팅 서비스 모니터링, 시작, 중지
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스를 시작, 중지 및 모니터링 하는 방법에 대해 알아봅니다.
  
영구 채팅 서비스 및 영구 채팅 준수 서비스는 비즈니스용 Skype 서버 토폴로지에 포함 되어 있으므로 다음 cmdlet을 사용 하 여 모니터링, 중지 및 시작이 가능 합니다.
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Windows 서비스로 실행 되는 비즈니스용 Skype 서버 2015 구성 요소에 대 한 자세한 정보를 반환 합니다.  <br/> |
|시작-CsWindowsService  <br/> |서비스를 시작 합니다.  <br/> |
|CsWindowsService 중지  <br/> |서비스를 중지 합니다.  <br/> |
   
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

Cmdlet을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.
  

