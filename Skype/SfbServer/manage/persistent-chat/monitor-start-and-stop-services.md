---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스 모니터링, 시작 및 중지
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '요약: 2015년 8월에 영구 채팅 서비스를 시작, 중지 및 모니터링하는 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 9d25654a222b956fa5c8a1902e5d3a90674829e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833384"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅 서비스 모니터링, 시작 및 중지
 
**요약:** 2015년 8월에 영구 채팅 서비스를 시작, 중지 및 모니터링하는 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
영구 채팅 서비스 및 영구 채팅 준수 서비스는 비즈니스용 Skype 서버 토폴로지의 일부로, 다음 cmdlet을 사용하여 모니터링, 중지 및 시작할 수 있습니다.
  
|Cmdlet|함수|
|:-----|:-----|
|get-CsWindowsService  <br/> |서비스로 실행되는 비즈니스용 Skype 서버 2015 구성 요소에 대한 자세한 Windows 반환합니다.  <br/> |
|start-CsWindowsService  <br/> |서비스를 시작합니다.  <br/> |
|stop-CsWindowsService  <br/> |서비스를 중지합니다.  <br/> |
   
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

cmdlet을 사용하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015 Management Shell 을 참조하십시오.](../management-shell.md)
  

