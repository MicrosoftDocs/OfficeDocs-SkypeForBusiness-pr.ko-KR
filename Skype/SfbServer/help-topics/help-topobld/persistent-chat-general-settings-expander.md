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
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 이러한 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 일반 설정을 편집할 수 있습니다.
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819480"
---
# <a name="persistent-chat-general-settings-expander"></a>영구 채팅 일반 설정 확장기
 
이러한 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 **일반** 설정을 편집할 수 있습니다.
  
 **일반**
  
- **FQDN**: 영구 채팅 서버 또는 영구 채팅 서버 풀의 정규화 된 도메인 이름을 정의 하려면이 설정을 편집 합니다.
    
- **영구 채팅 풀의 표시 이름**: 서버 또는 풀에 대해 사용자에게 익숙하며 사용자가 읽을 수 있는 설정을 제공하려면 이 설정을 정의합니다. 이 설정을 사용 하면 정규화 된 도메인 이름을 이해 하는 것 보다 더 쉽게 사용자가 지정 된 영구 채팅 서버 또는 영구 채팅 서버 풀을 표시 이름에 맞게 연결 하 게 됩니다.
    
- **영구 채팅 포트**: 영구 채팅에 사용할 포트를 지정합니다.
    
이러한 속성을 구성 하거나 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 **연결** 설정을 편집할 수 있습니다.
  
 **연결**
  
- **SQL Server 저장소**: SQL Server 저장소 및 선택적 명명된 인스턴스를 목록에서 선택합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 기본 SQL Server 저장소에 미러링을 사용 하도록 설정 하려면 **Sql server 스토어 미러링 사용** 확인란을 선택 합니다.
    
    SQL Server 저장소 미러링을 사용 하도록 선택한 경우 목록 **미러링 SQL Server 저장소**에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 기본 SQL Server 저장소의 자동 장애 조치 (failover) **를 설정 하려면 Sql server 미러링 미러링 모니터를 사용 하 여 자동 장애 조치 사용 확인란을** 선택 합니다.
    
    SQL Server store 미러링 감시가 자동 장애 조치 (failover)를 사용 하도록 선택한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 미러링 모니터 서버 저장소에 대해 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- SQL Server 재해 복구 사용을 사용 하도록 설정 하려면 sql **server 저장소 백업에서 재해 복구를** 사용 하도록 설정 확인란을 선택 합니다.
    
    재해 복구를 사용하도록 설정한 경우 **백업 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 백업 SQL Server 미러링 저장소에 미러링을 사용 하도록 설정 하려면 **Sql server 스토어 미러링 사용** 확인란을 선택 합니다.
    
    백업 SQL Server 스토어 미러링을 사용 하도록 선택한 경우 목록 **백업 Sql server 저장소 미러에서**저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 백업 SQL Server 저장소의 자동 장애 조치를 사용 하려면 **Sql server 미러링 미러링 모니터를 사용 하 여 자동 장애 조치 설정 확인란을** 선택 합니다.
    
    SQL Server store 미러링 감시가 자동 장애 조치 (failover)를 사용 하도록 선택한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 미러링 모니터 서버 저장소에 대해 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 준수 데이터베이스를 사용하도록 설정하려면 **준수 사용** 확인란을 선택합니다.
    
    준수를 사용하도록 설정한 경우 **준수 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 준수 SQL Server 저장소에 미러링을 사용 하도록 설정 하려면 **Sql server 스토어 미러링 사용** 확인란을 선택 합니다.
    
    준수 SQL Server 스토어 미러링을 사용 하도록 선택한 경우 목록 **준수 Sql server 저장소 미러에서**저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- Sql server **미러링 미러링 모니터를 사용 하 여 자동 장애 조치 사용 확인란을** 선택 하 여 규정 준수 SQL server store의 자동 장애 조치를 사용할 수 있습니다.
    
    SQL Server store 미러링 감시가 자동 장애 조치 (failover)를 사용 하도록 선택한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 미러링 모니터 서버 저장소에 대해 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 준수를 사용하도록 설정한 경우 **백업 준수 SQL Server 저장소** 목록에서 저장소와 인스턴스를 선택합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 준수 SQL Server 저장소에 미러링을 사용 하도록 설정 하려면 **Sql server 스토어 미러링 사용** 확인란을 선택 합니다.
    
    준수 SQL Server 스토어 미러링을 사용 하도록 선택한 경우 목록 **백업 준수 SQL server 저장소 미러에서**저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- 백업 준수 SQL Server 저장소의 자동 장애 조치가 필요한 경우 **Sql server 미러링 미러링 모니터를 사용 하 여 자동 장애 조치 사용 확인란을** 선택 합니다.
    
    SQL Server store 미러링 감시가 자동 장애 조치 (failover)를 사용 하도록 선택한 경우 목록에서 저장소와 인스턴스를 선택 합니다.
    
    **새로 만들기**를 클릭하여 미러링 모니터 서버 저장소에 대해 새 SQL Server 저장소 및 선택적 인스턴스를 정의합니다.
    
- **파일 저장소** 목록에서 파일 저장소 위치를 선택 하거나 **새로** 만들기를 클릭 하 여 새 파일 저장소를 만듭니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[비즈니스용 Skype Server 2015 토폴로지에 영구 채팅 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[영구 채팅 서버를 위한 고가용성 및 재해 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
