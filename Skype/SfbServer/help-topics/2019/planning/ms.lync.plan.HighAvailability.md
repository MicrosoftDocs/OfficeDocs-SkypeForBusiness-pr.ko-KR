---
title: 고가용성 (계획 도구)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버에서 대부분의 서버 역할에 대 한 주요 고가용성 체계는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.
ms.openlocfilehash: 36869cedb2443d13774e8646b72a51a039683f16
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197947"
---
# <a name="high-availability-planning-tool"></a>고가용성 (계획 도구)
 
비즈니스용 Skype 서버에서 대부분의 서버 역할에 대 한 주요 고가용성 체계는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.
  
고가용성을 위해 비즈니스용 Skype 서버에는 두 대 이상의 프런트 엔드 서버가 필요 합니다. 계획 도구는 다음 조건을 사용 하 여 고가용성을 지원 하기 위해 추가 서버를 추가할 것인지 여부를 결정 합니다.
  
- 배포에 두 개 이상의 프런트 엔드 서버가 포함 된 경우 계획 도구에서 서버를 더 추가 하지 않습니다.
    
- 배포에 Edge Server가 포함 되어 있으면 추가 서버가 추가 됩니다. 
    
- 배포에 영구 채팅이 포함 되어 있는 경우 계획 도구는 추가 서버를 추가 하지만 풀 번호는 증가 하지 않습니다. 예를 들어 배포에 이미 4 개의 서버가 있는 경우 계획 도구는 추가 서버 (총 5 개 서버)를 추가 하는 것을 제안 하지만 단일 풀을 유지 합니다. 

    > [!NOTE] 
    > 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 비즈니스용 [Skype For Microsoft 팀 업그레이드](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)를 참조 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

    
또한 계획 도구는 모든 데이터베이스에 대 한 미러 SQL 데이터베이스를 추가 합니다. 예를 들어 프런트 엔드 SQL Server 데이터베이스가 있는 경우 계획 도구는이 데이터베이스에 대 한 미러 데이터베이스를 추가 하 고 "프런트 엔드 미러 SQL 데이터베이스"로 이름을 만듭니다.
  
고가용성을 위해 환경을 준비 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.
  

