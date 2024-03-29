---
title: 영구 채팅 일반 설정 확장기
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 다음 속성을 구성하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 일반 설정을 편집합니다.
ms.openlocfilehash: e93af8c8924117159434691b550f2ed9fcbb6e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417691"
---
# <a name="persistent-chat-general-settings-expander"></a>영구 채팅 일반 설정 확장기
 
다음 속성을 구성  하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 일반 설정을 편집합니다.
  
 **일반**
  
- **FQDN**: 이 설정을 편집하여 영구 채팅 서버 또는 영구 채팅 서버 풀의 정식 도메인 이름을 정의합니다.
    
- **영구 채팅** 풀의 표시 이름: 서버 또는 풀에 대해 사용자에게 친숙하고 사용자가 읽을 수 있는 설정을 제공하도록 이 설정을 정의합니다. 이 설정을 사용하면 사용자가 완전히 정식 도메인 이름을 이해하는 대신 표시 이름을 기반으로 특정 영구 채팅 서버 또는 영구 채팅 서버 풀을 보다 쉽게 연결합니다.
    
- **영구 채팅 포트**: 영구 채팅에 사용할 포트를 지정합니다.
    
다음 속성을 구성  하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 연결 설정을 편집합니다.
  
 **연결**
  
- **SQL Server 저장소**: 목록에서 SQL Server 저장소 및 선택적 명명된 인스턴스를 선택합니다.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 기본 SQL Server **저장소** 에 대해 미러링을 사용하도록 설정하려면 SQL Server 확인란을 선택합니다.
    
    저장소 미러링을 사용하도록 SQL Server 경우 미러링 저장소 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 기본 SQL Server 저장소의 자동 장애 조치(**failover)** 를 사용하려면 자동 장애 조치(failover)를 사용하려면 미러링 SQL Server 선택합니다.
    
    자동 장애 조치(failover)를 사용하도록 SQL Server 저장소 미러링크를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.
    
    새로 **추가를** 클릭하여 새 SQL Server 저장소 및 미러링크 저장소의 선택적 인스턴스를 정의합니다.
    
- 재해 복구 **를 사용하도록 설정** 하려면 SQL Server 저장소를 사용하여 재해 복구 사용 확인란을 SQL Server 선택합니다.
    
    재해 복구를 사용하도록 선택한 경우 백업 저장소 저장소 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 백업 서버 **SQL Server** 저장소에 대해 미러링을 사용하도록 설정하려면 SQL Server 확인란을 선택합니다.
    
    백업 저장소 미러링을 사용하도록 SQL Server 경우 백업 저장소 미러 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 백업 서버 SQL Server 저장소의 자동 장애 조치(failover)를 수행하려면 자동 장애 조치(**failover**)를 사용하려면 미러링 SQL Server 선택합니다.
    
    자동 장애 조치(failover)를 사용하도록 SQL Server 저장소 미러링크를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.
    
    새로 **추가를** 클릭하여 새 SQL Server 저장소 및 미러링크 저장소의 선택적 인스턴스를 정의합니다.
    
- 준수 데이터베이스 **를** 사용하도록 설정하려면 준수 사용 확인란을 선택합니다.
    
    규정 준수를 사용하도록 선택한 경우 준수 저장소 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 준수 저장소 **에 SQL Server** 미러링을 사용하도록 설정하려면 SQL Server 확인란을 선택합니다.
    
    준수 저장소 미러링을 사용하도록 SQL Server 경우 준수 저장소 미러 목록에서 저장소 **SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 준수 서버 SQL Server 저장소의 자동 장애 조치(failover)를 수행하려면 자동 장애 조치(**failover**)를 사용하려면 미러링 SQL Server 선택합니다.
    
    자동 장애 조치(failover)를 사용하도록 SQL Server 저장소 미러링크를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.
    
    새로 **추가를** 클릭하여 새 SQL Server 저장소 및 미러링크 저장소의 선택적 인스턴스를 정의합니다.
    
- 준수를 사용하도록 선택한 경우 백업 준수 및 저장소 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 준수 저장소 **에 SQL Server** 미러링을 사용하도록 설정하려면 SQL Server 확인란을 선택합니다.
    
    저장소 미러링을 SQL Server 사용하도록 설정한 경우 저장소 미러링 백업 준수 목록에서 저장소 **및 SQL Server 선택합니다**.
    
    새로 **추가를** 클릭하여 저장소 및 SQL Server 인스턴스를 정의합니다.
    
- 백업 준수 SQL Server 저장소의 자동 장애 조치(failover)를 수행하려면 자동 장애 조치(**failover**)를 사용하려면 미러링 SQL Server 선택합니다.
    
    자동 장애 조치(failover)를 사용하도록 SQL Server 저장소 미러링크를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.
    
    새로 **추가를** 클릭하여 새 SQL Server 저장소 및 미러링크 저장소의 선택적 인스턴스를 정의합니다.
    
- **파일 저장소** 목록에서 파일 저장소 위치를 선택하거나 새로 만들기를 클릭하여  새 파일 저장소를 만들 수 있습니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  
## <a name="see-also"></a>참고 항목

[2015년 비즈니스용 Skype 서버 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 토폴로지에서 영구 채팅 비즈니스용 Skype 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[2015년 8월 영구 채팅 서버에 대한 고가용성 비즈니스용 Skype 서버 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
