---
title: 영구 채팅 준수 백업 SQL Server 저장소 추가
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 영구 채팅 서버 또는 영구 채팅 서버 준수 SQL Server 저장소에 대해 백업 데이터베이스를 제공 하는 백업 준수 SQL Server 저장소를 구성 합니다.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218699"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>영구 채팅 준수 백업 SQL Server 저장소 추가
 
영구 채팅 서버 또는 영구 채팅 서버 준수 SQL Server 저장소에 대해 백업 데이터베이스를 제공 하는 백업 준수 SQL Server 저장소를 구성 합니다.
  
 **SQL server 저장소**: 기존 SQL server를 선택 하 고 필요에 따라 영구 채팅 인스턴스를 선택할 수도 있습니다.
  
**새로 만들기** 를 클릭 하 여 새 SQL Server를 정의 하 고 영구 채팅 백업 준수 데이터에 대 한 새 인스턴스를 선택 합니다.
  
Sql Server 데이터베이스 및 영구 채팅 백업 준수 데이터에 대 한 미러링된 데이터베이스를 제공할 선택적 인스턴스를 구성 하려면 **이 확인란을** 선택 합니다.
  
영구 채팅 백업 준수 SQL Server에 대 한 SQL server 미러로 사용할 sql server 및 선택적 인스턴스를 **미러링 sql server 저장소** 목록에서 선택 합니다.
  
**새로 만들기** 를 클릭 하 여 새 sql server를 정의 하 고 영구 채팅 SQL Server 미러링에 대 한 새 인스턴스를 선택 합니다.
  
장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다. 미러링 모니터 서버는 영구 채팅 서버에 대 한 데이터를 미러 하거나 호스팅하지 않으며, 미러링된 구성에서 하나의 SQL 서버만 언제 든 지 활성 SQL Server가 됩니다.
  
**새로 만들기** 를 클릭 하 여 새 SQL server 감시를 정의 합니다 (선택적으로 영구 채팅 백업 준수 SQL Server 미러링 모니터 서버에 대 한 인스턴스).
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.
  
이 풀의 백업 SQL Server 저장소 구성에 대 한 옵션을 모두 입력 한 후 영구 채팅 서버 풀 정의를 계속 하려면 **다음** 을 클릭 합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대 한 준수 서비스 구성](../../manage/persistent-chat/configure-compliance.md)
  
[비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 합니다.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
