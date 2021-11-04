---
title: 영구 채팅 준수 백업 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 영구 채팅 서버 또는 SQL Server 채팅 서버 준수 저장소에 대한 백업 데이터베이스를 제공할 백업 준수 SQL Server 구성합니다.
ms.openlocfilehash: 8d70a8f82c58d0a66fef00695b3677305e5e6a9e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747864"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>영구 채팅 준수 백업 SQL Server 저장소 추가
 
영구 채팅 서버 또는 SQL Server 채팅 서버 준수 저장소에 대한 백업 데이터베이스를 제공할 백업 준수 SQL Server 구성합니다.
  
 **SQL Server 저장소:** 기존 SQL Server 영구 채팅에 대한 인스턴스를 선택합니다.
  
새로 **추가를** 클릭하여 새 SQL Server 영구 채팅 백업 준수 데이터에 대한 새 인스턴스를 정의합니다.
  
영구 **채팅 SQL Server** 준수 데이터에 대한 미러 데이터베이스를 제공할 SQL Server 데이터베이스 및 선택적 인스턴스를 구성하려면 SQL Server 저장소 미러링 사용 확인란을 선택합니다.
  
영구 채팅  백업 준수 SQL Server 대한 SQL Server 및 선택적 인스턴스를 SQL Server 미러링 목록에서 SQL Server.
  
새로 **고침을** 클릭하여 새 SQL Server 영구 채팅 및 미러링에 대한 새 SQL Server 정의합니다.
  
장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다. 미러링된 서버는 영구 채팅 서버에 대한 데이터를 미러링하거나 호스팅하지 않지만 미러된 구성에서 SQL Server 하나만 활성 SQL Server 합니다.
  
새로 **고침을** 클릭하여 미러링 SQL Server 미러링 SQL Server 인스턴스에 대한 새 미러링 SQL Server 정의합니다.
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로** 를 클릭합니다.
  
이 **풀의** 백업 저장소 구성에 대한 옵션을 모두 입력한 후 SQL Server 다음을 클릭하여 영구 채팅 서버 풀 정의를 진행합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소** 를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말** 을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[2015년 비즈니스용 Skype 서버 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항 비즈니스용 Skype 서버 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015년 8월에 영구 채팅 서버에 대한 준수 비즈니스용 Skype 서버 구성](../../manage/persistent-chat/configure-compliance.md)
  
[2015년 8월 영구 채팅 서버에 대한 고가용성 비즈니스용 Skype 서버 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
