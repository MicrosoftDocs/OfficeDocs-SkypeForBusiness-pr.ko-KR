---
title: 등록자 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 탄성은 등록자 풀에 대해 고가용성 및 재해 복구를 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 실패한 시스템에 따라 잠재적으로 사용할 수 있는 기능이 축소될 수 있습니다.
ms.openlocfilehash: 599923fc8b85e57387ff2742a933c60a928a2dde
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837710"
---
# <a name="registrar-settings-expander"></a>등록자 설정 확장기
 
탄성은 등록자 풀에 대해 고가용성 및 재해 복구를 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 실패한 시스템에 따라 잠재적으로 사용할 수 있는 기능이 축소될 수 있습니다.
  
SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 **속성 편집** 대화 상자에 있는 **복구** 섹션에서 다음 설정을 변경할 수 있습니다.
  
- **연결된 사용자 서비스 및 백업 등록자 풀** 드롭다운 목록에서 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 분기 서버의 백업 등록자 역할을 할 프런트 엔드 서버를 선택합니다.
    
- **장애 조치(failover) 및 장애 조치(failback) 사용** 실패한 등록자가 자동으로 검색될 수 있도록 허용하려면 이 설정을 선택하고 기본 등록자가 백업되어 등록자 프로세스를 다시 시작할 준비가 되어 있는 자동 확인을 선택합니다.
    
- **오류 검색 간격(초)** 기본 등록자가 실패한 것으로 판단되기 전에 경과해야 하는 시간(초)을 입력합니다. 기본값은 120초입니다. 장애 조치(Failover) 및 장애 조치(Failback) 를 선택하는 경우 이 **필드가 필요합니다.**
    
- **Fallback detection interval (sec)** 기본 등록자가 백업된 것으로 결정되기 전에 경과해야 하는 시간(초)을 입력합니다. 기본값은 240초입니다. 장애 조치(Failover) 및 Fallback 사용 을 선택하는 경우 이 **필드가 필요합니다.**
    
> [!IMPORTANT]
> 실패 검색 및 대체 검색 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 발생하지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다. 
  

