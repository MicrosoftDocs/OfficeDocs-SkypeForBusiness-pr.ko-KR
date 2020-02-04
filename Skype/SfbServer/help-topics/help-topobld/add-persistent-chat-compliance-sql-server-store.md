---
title: 영구 채팅 준수 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 영구 채팅 서버 또는 영구적 채팅 서버 준수 기능에 대 한 데이터베이스를 제공 하는 준수 SQL Server 저장소를 구성 합니다.
ms.openlocfilehash: 64697fbe9783bbdf356a28882f7cf53e7e96ef94
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698073"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>영구 채팅 준수 SQL Server 저장소 추가
 
영구 채팅 서버 또는 영구적 채팅 서버 준수 기능에 대 한 데이터베이스를 제공 하는 준수 SQL Server 저장소를 구성 합니다.
  
 **Sql server 스토어**: 기존 SQL server를 선택 하 고 필요에 따라 영구 채팅 인스턴스를 사용할 수도 있습니다.
  
**새로 만들기** 를 클릭 하 여 새 SQL Server를 정의 하 고 필요에 따라 영구 채팅 준수 데이터에 새 인스턴스를 만듭니다.
  
Sql server **스토어 미러링 사용** 확인란을 선택 하 여 sql server 데이터베이스를 구성 하 고 지속적인 채팅 준수 데이터에 미러된 데이터베이스를 제공 하는 선택적 인스턴스를 구성할 수 있습니다.
  
영구 채팅 준수 SQL Server에 대 한 SQL server 미러 역할을 하는 목록 미러링 sql server **저장소** 의 sql server 및 선택적 인스턴스를 선택 합니다.
  
**새로 만들기** 를 클릭 하 여 새 sql server를 정의 하 고 선택적으로 영구 채팅 SQL server 미러링에 대 한 새 인스턴스를 만듭니다.
  
장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다. 미러링 모니터 서버는 영구 채팅 서버에 대 한 데이터를 미러링 또는 호스팅하지 않으며, 미러링된 구성에서 한 SQL Server만 언제 든 지 활성 SQL 서버를 사용할 수 있도록 합니다.
  
**새로 만들기** 를 클릭 하 여 새 sql server 미러링 (선택적으로 지속적인 채팅 준수 SQL server 미러링 모니터에 대 한 인스턴스)을 정의 합니다.
  
이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.
  
이 풀의 백업 SQL Server 저장소 구성에 대 한 옵션을 모두 입력 하 고 영구 채팅 서버 풀 정의를 진행 하려면 **다음** 을 클릭 합니다.
  
모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.
  
이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[영구 채팅 서버에 대한 준수 서비스 구성](../../manage/persistent-chat/configure-compliance.md)
