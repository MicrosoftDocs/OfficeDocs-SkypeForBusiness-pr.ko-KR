---
title: 영구 채팅 일반 설정 확장기
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
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 다음 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 일반 설정을 편집할 수 있습니다.
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215999"
---
# <a name="persistent-chat-general-settings-expander"></a>영구 채팅 일반 설정 확장기
 
다음 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 **일반** 설정을 편집할 수 있습니다.
  
 **일반**
  
- **FQDN**: 영구 채팅 서버 또는 영구 채팅 서버 풀의 정규화 된 도메인 이름을 정의 하려면이 설정을 편집 합니다.
    
- **영구 채팅 풀의 표시 이름**:이 설정을 정의 하 여 서버 또는 풀에 대해 사용자에 게 친숙 하 고 사용자가 읽을 수 있는 설정을 제공 합니다. 이 설정을 사용 하면 정규화 된 도메인 이름을 이해 하기 어려울 때 보다 사용자가 지정 된 영구 채팅 서버 또는 영구 채팅 서버 풀을 표시 이름에 따라 보다 쉽게 연결할 수 있습니다.
    
- **영구 채팅 포트**: 영구 채팅에 사용할 포트를 지정 합니다.
    
다음 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 **연결** 설정을 편집 합니다.
  
 **연결이**
  
- **Sql server 저장소**: sql server 저장소 및 선택적 명명 된 인스턴스를 목록에서 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 기본 SQL Server 저장소에 대해 미러링을 사용 하도록 설정 하려면 **Sql server 저장소 미러링 사용** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링을 사용 하도록 선택한 경우 **미러링 SQL Server 저장소**목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 기본 SQL Server 저장소의 자동 장애 조치 (failover)를 사용 하려면 **Sql server 미러링 모니터 서버를 사용 하 여 자동 장애 조치 (failover) 설정** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링 모니터 서버에서 자동 장애 조치 (failover)를 사용 하도록 설정한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기** 를 클릭 하 여 미러링 모니터 저장소에 대 한 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- SQL Server 재해 복구를 사용 하도록 설정 하려면 **백업 SQL Server 저장소를 사용 하 여 재해 복구** 사용 확인란을 선택 합니다.
    
    재해 복구를 사용 하도록 설정한 경우 **백업 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 백업 SQL Server 미러링 저장소에 대해 미러링을 사용 하도록 설정 하려면 **Sql server 저장소 미러링 사용** 확인란을 선택 합니다.
    
    백업 SQL Server 저장소 미러링을 사용 하도록 선택한 경우 목록 **백업 SQL server 저장소 미러에서**저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 백업 SQL Server 저장소의 자동 장애 조치 (failover)를 사용 하려면 **Sql server 미러링 모니터 서버를 사용 하 여 자동 장애 조치 (failover) 설정** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링 모니터 서버에서 자동 장애 조치 (failover)를 사용 하도록 설정한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기** 를 클릭 하 여 미러링 모니터 저장소에 대 한 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 준수 데이터베이스를 사용 하도록 설정 하려면 **준수 사용** 확인란을 선택 합니다.
    
    준수를 사용 하도록 설정한 경우 **준수 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 준수 SQL Server 저장소에 대해 미러링을 사용 하도록 설정 하려면 **Sql server 저장소 미러링 사용** 확인란을 선택 합니다.
    
    준수 SQL Server 저장소 미러링을 사용 하도록 설정한 경우 **준수 Sql server 저장소 미러**목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 준수 SQL Server 저장소의 자동 장애 조치 (failover)를 사용 하려면 **Sql server 미러링 모니터 서버를 사용 하 여 자동 장애 조치 (failover) 설정** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링 모니터 서버에서 자동 장애 조치 (failover)를 사용 하도록 설정한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기** 를 클릭 하 여 미러링 모니터 저장소에 대 한 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 준수를 사용 하도록 설정한 경우 **백업 준수 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 준수 SQL Server 저장소에 대해 미러링을 사용 하도록 설정 하려면 **Sql server 저장소 미러링 사용** 확인란을 선택 합니다.
    
    준수 SQL Server 저장소 미러링을 사용 하도록 설정한 경우 **백업 준수 SQL server 저장소 미러**목록에서 저장소와 인스턴스를 선택 합니다.
    
    새로 **만들기** 를 클릭 하 여 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- 백업 준수 SQL Server 저장소의 자동 장애 조치 (failover)를 사용 하려면 **Sql server 미러링 모니터 서버를 사용 하 여 자동 장애 조치 (failover) 설정** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링 모니터 서버에서 자동 장애 조치 (failover)를 사용 하도록 설정한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기** 를 클릭 하 여 미러링 모니터 저장소에 대 한 새 SQL Server 저장소 및 선택적 인스턴스를 정의 합니다.
    
- **파일 저장소** 목록에서 파일 저장소 위치를 선택 하거나 **새로** 만들기를 클릭 하 여 새 파일 저장소를 만듭니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015 토폴로지에 영구 채팅 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 합니다.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
