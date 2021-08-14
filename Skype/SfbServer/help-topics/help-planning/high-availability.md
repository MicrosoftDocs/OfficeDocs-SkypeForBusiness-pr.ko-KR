---
title: 비즈니스용 Skype 서버 고가용성 계획 도구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: 비즈니스용 Skype 서버 2015의 대부분의 서버 역할에 대한 주요 고가용성 스키마는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.
ms.openlocfilehash: d8c6a16ba29d5725a148810c71a17325bdbab763
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234703"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>비즈니스용 Skype 서버 고가용성 계획 도구
 
비즈니스용 Skype 서버 2015의 대부분의 서버 역할에 대한 주요 고가용성 스키마는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.
  
비즈니스용 Skype 서버 2015에서는 고가용성을 사용하려면 프런트 엔드 서버가 두 개 이상 필요합니다. 계획 도구는 다음 조건을 사용하여 고가용성을 지원하기 위해 추가 서버를 추가할지 여부를 결정할 수 있습니다.
  
- 배포에 둘 이상의 프런트 엔드 서버가 포함된 경우 계획 도구에서 추가 서버를 추가하지 않습니다.
    
- 배포에 에지 서버가 포함되어 있는 경우 다른 서버가 추가됩니다. 
    
- 배포에 영구 채팅이 포함된 경우 계획 도구에서 추가 서버를 추가하지만 풀 번호는 늘리지 않습니다. 예를 들어 배포에 이미 4개의 서버가 포함되어 있는 경우 계획 도구에서 다른 서버(총 5대의 서버)를 추가하는 것이 권장되지만 단일 풀은 유지 관리합니다. 
    
또한 계획 도구는 모든 데이터베이스에 SQL 데이터베이스를 추가합니다. 예를 들어 프런트 엔드 SQL Server 데이터베이스가 있는 경우 계획 도구는 이 데이터베이스의 미러 데이터베이스로 다른 데이터베이스를 추가하고 이름을 "프런트 엔드 미러 SQL 데이터베이스입니다.
  
고가용성을 위해 환경을 준비하는 데 대한 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버 2015을 참조합니다.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  

