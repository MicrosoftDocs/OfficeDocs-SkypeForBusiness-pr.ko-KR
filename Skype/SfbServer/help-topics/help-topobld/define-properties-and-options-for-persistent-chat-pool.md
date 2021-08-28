---
title: 영구 채팅 풀에 대한 속성 및 옵션 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 다음 속성을 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 옵션을 구성합니다.
ms.openlocfilehash: 242490ebe6be0f68e8c25e0c01b77088c15836d8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622440"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>영구 채팅 풀에 대한 속성 및 옵션 정의
 
다음 속성을 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 옵션을 구성합니다.
  
 **영구 채팅** 풀의 표시 이름: 이 영구 채팅 서버 또는 영구 채팅 서버 풀에 대해 표시할 사용자 이름을 정의하는 필수 속성입니다.
  
 **영구 채팅 포트:** 이 영구 채팅 서버 또는 영구 채팅 서버 풀이 수신할 포트 번호를 정의하는 필수 속성입니다.
  
 **준수 사용:** 선택적 영구 채팅 준수 기능 및 데이터베이스를 배포하고 구현하려면 이 확인란을 선택합니다.
  
 **백업 SQL Server** 저장소를 사용하여 재해 복구 사용: 다른 저장소의 구성된 백업 집합에서 영구 채팅 SQL Server 저장소의 재해 복구를 배포하고 구현하려면 이 확인란을 SQL Server. 자세한 내용은 [Configure high availability and disaster recovery for Persistent Chat Server in 비즈니스용 Skype 서버 2015을 참조하세요.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
  
> [!NOTE]
> 이 옵션은 서버가 여러 개 포함된 풀에 대해서만 사용 가능합니다. 
  
 **사이트의 기본 \<site that this server or pool is being configured in\>** 풀로 이 풀 사용: 사이트의 기본 영구 채팅 서버 또는 영구 채팅 서버 풀이면 이 확인란을 선택합니다. 사이트당 기본 영구 채팅 서버 또는 pol이 하나 있어야 합니다.
  
> [!NOTE]
> 토폴로지에 사이트가 여러 개 포함되는 경우에는 **이 풀을 모든 사이트의 기본 풀로 사용** 확인란도 표시됩니다.
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로** 를 클릭합니다.
  
이 **풀에** 대한 옵션 입력을 마친 후 다음을 클릭하여 영구 채팅 서버 풀 정의를 진행합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소** 를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말** 을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[2015년 비즈니스용 Skype 서버 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 토폴로지에서 영구 채팅 비즈니스용 Skype 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
