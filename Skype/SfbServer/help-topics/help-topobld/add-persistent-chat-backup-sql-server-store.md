---
title: 영구 채팅 백업 SQL Server 저장소 추가
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
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 영구 채팅 SQL Server 또는 영구 채팅 서버 풀에 대한 백업 데이터베이스를 제공할 백업 서버 저장소를 구성합니다.
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818738"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>영구 채팅 백업 SQL Server 저장소 추가
 
영구 채팅 SQL Server 또는 영구 채팅 서버 풀에 대한 백업 데이터베이스를 제공할 백업 서버 저장소를 구성합니다.
  
 **SQL Server 저장소:** 기존 SQL Server 영구 채팅 인스턴스를 선택합니다.
  
새로 **고치려면** 새 SQL Server 영구 채팅 백업 데이터에 대한 새 인스턴스(선택 사항)를 정의합니다.
  
저장소 SQL Server 사용 **확인란을** 선택하여 SQL Server 데이터베이스 및 영구 채팅 백업 데이터에 대한 미러된 데이터베이스를 제공할 선택적 인스턴스를 구성합니다.
  
영구 채팅  백업 SQL Server 대한 SQL Server 미러로 사용할 SQL Server 및 선택적 인스턴스를 저장하는 미러링 SQL Server.
  
새로 **고침을** 클릭하여 새 SQL Server 영구 채팅 서버 미러링에 대한 새 SQL Server 정의합니다.
  
장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다. 미러링된 서버는 영구 채팅 서버에 대한 데이터를 미러링하거나 호스팅하지 않지만 미러된 구성에서 SQL Server 한 번만 활성 SQL Server 합니다.
  
새로 **고침을** 클릭하여 미러링 SQL Server 미러링된 영구 채팅 백업에 대한 인스턴스를 선택적으로 SQL Server 정의합니다.
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로** 를 클릭합니다.
  
저장소 **구성을** 저장하고 영구 채팅 서버 풀 정의를 계속하려면 이 풀의 백업 SQL Server 옵션을 모두 입력한 후 다음을 클릭합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소** 를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말** 을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015에 대한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항(비즈니스용 Skype 서버 2015)](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[영구 채팅 서버의 고가용성 및 재해 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
