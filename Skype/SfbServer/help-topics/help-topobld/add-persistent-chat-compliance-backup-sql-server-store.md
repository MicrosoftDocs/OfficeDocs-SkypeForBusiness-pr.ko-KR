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
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 영구 채팅 서버 또는 영구 채팅 서버 준수 SQL Server 저장소에 대 한 백업 데이터베이스를 제공 하는 백업 준수 SQL Server 저장소를 구성 합니다.
ms.openlocfilehash: e557651c7c55a847de85be1ce724168fcc713a96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820700"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>영구 채팅 준수 백업 SQL Server 저장소 추가
 
영구 채팅 서버 또는 영구 채팅 서버 준수 SQL Server 저장소에 대 한 백업 데이터베이스를 제공 하는 백업 준수 SQL Server 저장소를 구성 합니다.
  
 **Sql server 스토어**: 기존 SQL server를 선택 하 고 필요에 따라 영구 채팅 인스턴스를 사용할 수도 있습니다.
  
**새로 만들기** 를 클릭 하 여 새 SQL Server를 정의 하 고, 선택적으로 영구 채팅 백업 준수 데이터에 대 한 새 인스턴스를 만듭니다.
  
Sql server **스토어 미러링 사용** 확인란을 선택 하 여 sql server 데이터베이스와 영구 채팅 백업 준수 데이터에 미러된 데이터베이스를 제공할 선택적 인스턴스를 구성 합니다.
  
목록 미러링 sql server **저장소** 에서 영구 채팅 백업 준수 sql server에 대 한 sql server 미러 역할을 하는 sql server 및 선택적 인스턴스를 선택 합니다.
  
**새로 만들기** 를 클릭 하 여 새 sql server를 정의 하 고 선택적으로 영구 채팅 SQL server 미러링에 대 한 새 인스턴스를 만듭니다.
  
장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다. 미러링 모니터 서버는 영구 채팅 서버에 대 한 데이터를 미러링 또는 호스팅하지 않으며, 미러링된 구성에서 한 SQL Server만 언제 든 지 활성 SQL 서버를 사용할 수 있도록 합니다.
  
**새로 만들기** 를 클릭 하 여 새 sql server 감시를 정의 합니다 (선택적으로 영구 채팅 백업 준수 SQL server 미러링 모니터에 대 한 인스턴스).
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.
  
이 풀의 백업 SQL Server 저장소 구성에 대 한 옵션을 모두 입력 하 고 영구 채팅 서버 풀 정의를 진행 하려면 **다음** 을 클릭 합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[영구 채팅 서버에 대한 준수 서비스 구성](../../manage/persistent-chat/configure-compliance.md)
  
[영구 채팅 서버를 위한 고가용성 및 재해 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
