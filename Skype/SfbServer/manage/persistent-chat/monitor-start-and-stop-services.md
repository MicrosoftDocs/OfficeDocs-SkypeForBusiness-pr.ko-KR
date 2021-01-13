---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스 모니터링, 시작 및 중지
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
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스를 시작, 중지 및 모니터링하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814138"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅 서비스 모니터링, 시작 및 중지
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스를 시작, 중지 및 모니터링하는 방법을 학습합니다.
  
영구 채팅 서비스 및 영구 채팅 준수 서비스는 비즈니스용 Skype 서버 토폴로지의 일부로, 다음 cmdlet을 사용하여 모니터링, 중지 및 시작할 수 있습니다.
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Windows 서비스로 실행되는 비즈니스용 Skype 서버 2015 구성 요소에 대한 자세한 정보를 반환합니다.  <br/> |
|start-CsWindowsService  <br/> |서비스를 시작합니다.  <br/> |
|stop-CsWindowsService  <br/> |서비스를 중지합니다.  <br/> |
   
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. Teams에서 동일한 기능을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

cmdlet 사용 방법에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)
  

