---
title: 영구 채팅 풀에 대한 속성 및 옵션 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 다음 속성을 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 옵션을 구성 합니다.
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218549"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>영구 채팅 풀에 대한 속성 및 옵션 정의
 
다음 속성을 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 옵션을 구성 합니다.
  
 **영구 채팅 풀의 표시 이름**:이 영구 채팅 서버 또는 영구 채팅 서버 풀에 대해 표시 될 사용자에 게 친숙 한 이름을 정의 하는 필수 속성입니다.
  
 **영구 채팅 포트**:이 영구 채팅 서버 또는 영구 채팅 서버 풀이 수신 대기 하는 포트 번호를 정의 하는 필수 속성입니다.
  
 **준수 사용**: 선택적 영구 채팅 준수 기능 및 데이터베이스를 배포 하 고 구현 하려는 경우에는이 확인란을 선택 합니다.
  
 **백업 SQL server 저장소를 사용 하 여 재해 복구**를 사용 하도록 설정 하려면 다음을 수행 합니다. 다른 SQL server에 구성 된 백업 저장소의 영구 채팅 SQL Server 저장소에 대 한 재해 복구를 배포 하 고 구현 하려면이 확인란을 선택 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 고가용성 및 재해 복구 구성을](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)참조 하세요.
  
> [!NOTE]
> 이 옵션은 서버가 여러 개 포함된 풀에 대해서만 사용 가능합니다. 
  
 **이 풀을 사이트 \<site that this server or pool is being configured in\> 의 기본값으로 사용 **:이를 사이트에 대 한 기본 영구 채팅 서버 또는 영구 채팅 서버 풀로 사용할 수 있도록 하려면이 확인란을 선택 합니다. 기본 영구 채팅 서버 또는 사이트 당 pol 하나 있어야 합니다.
  
> [!NOTE]
> 토폴로지에 사이트가 여러 개 포함되는 경우에는 **이 풀을 모든 사이트의 기본 풀로 사용** 확인란도 표시됩니다.
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.
  
이 풀에 대 한 옵션을 모두 입력 한 후에 영구 채팅 서버 풀 정의를 계속 하려면 **다음** 을 클릭 합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015 토폴로지에 영구 채팅 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
