---
title: 영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항 비즈니스용 Skype 서버 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '요약: 이 항목을 통해 2015년 8월 영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: f0abc9bde21a4bd5b8e198edad76ff420ce8074e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765176"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항 비즈니스용 Skype 서버 2015
 
**요약:** 이 항목을 통해 2015년 8월 영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 비즈니스용 Skype 서버 있습니다.
  
영구 채팅 서버는 2015 또는 2015 비즈니스용 Skype 서버 함께 설치할 Enterprise Edition Standard Edition. 요구 사항은 설치한 비즈니스용 Skype 서버 2015 버전과 비즈니스의 성능 요구 사항에 따라 다릅니다. Enterprise Edition 최대 80,000명까지 동시 사용자를 지원할 수 있습니다. Standard Edition 동시 사용자를 20,000명까지 지원할 수 있습니다. 영구 채팅은 프런트 엔드 구성 요소와 백 엔드 데이터베이스 구성 요소로 SQL 구성됩니다.
  
영구 채팅 서버를 배포하기 전에 다음 하드웨어 및 소프트웨어 요구 사항이 충족되어야 합니다.
  
- 비즈니스용 Skype 서버, 영구 채팅 서버, 데이터베이스 서버 및 파일 서버를 지원하기 위한 최소 요구 사항을 충족하는 하드웨어입니다. 자세한 내용은 server [requirements for 비즈니스용 Skype 서버 2015을 참조하십시오.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- 지원되는 운영 체제 및 데이터베이스 소프트웨어.
    
    지원되는 운영 체제 및 데이터베이스 소프트웨어 및 Windows 대한 자세한 내용은 [server requirements for 비즈니스용 Skype 서버 2015을 참조하세요.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- 비즈니스용 Skype 서버 2015 프런트 엔드 서버. 프런트 엔드 서버는 영구 채팅 서버를 실행하는 컴퓨터와 영구 채팅 기능을 사용할 수 있는 SIP(Session Initiation Protocol) 라우팅의 기반이 됩니다. 
    
- 메시지 큐 소프트웨어. 배포된 경우 영구 채팅 서버 및 영구 채팅 준수 서비스에서 사용됩니다.
    
다음 섹션에서는 영구 채팅 데이터를 저장하는 영구 채팅 서버 및 데이터베이스에 대한 특정 요구 사항에 대해 설명합니다.

> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
  
## <a name="front-end-server-requirements"></a>프런트 엔드 서버 요구 사항

프런트 엔드 서버 요구 사항은 비즈니스용 Skype 서버 2015 또는 2015와 함께 영구 채팅 서버를 Enterprise Edition Standard Edition.
  
- 비즈니스용 Skype 서버 2015 Enterprise Edition 영구 채팅 서버를 배포하는 경우 Enterprise Edition 풀의 하나 이상의 독립 실행형 컴퓨터에 영구 채팅 서버 프런트 엔드 서버를 배포할 수 있습니다. 영구 채팅 프런트 엔드 서버를 2015 프런트 엔드 서버에 비즈니스용 Skype 서버 수 없습니다. 
    
    단일 영구 채팅 서버 프런트 엔드 서버는 활성 사용자 20,000명을 지원할 수 있습니다. 최대 4개 활성 프런트 엔드가 있는 영구 채팅 서버 풀을 유지하여 총 80,000명의 동시 사용자를 지원할 수 있습니다. 
    
- 비즈니스용 Skype 서버 2015 Standard Edition 영구 채팅 서버를 배포하는 경우 영구 채팅을 프런트 엔드 서버와 함께 배치할 수 있습니다. 이 단일 서버 배포는 최대 20,000명까지 지원할 수 있습니다. 
    
## <a name="persistent-chat-server-database-requirements"></a>영구 채팅 서버 데이터베이스 요구 사항

영구 채팅 서버에는 SQL Server 콘텐츠, 구성 데이터, 사용자 프로비전 데이터 및 기타 관련 메타데이터를 저장하기 위해 데이터베이스 소프트웨어가 필요합니다. 선택적으로 영구 채팅 준수 데이터베이스를 사용하여 준수 데이터를 저장합니다. 영구 채팅 데이터베이스는 백 엔드 데이터베이스와 동일한 SQL Server 또는 동일한 SQL 인스턴스에 함께 함께 사용할 수 있습니다. 
  
- 최적의 성능을 보장하기 위해 비즈니스용 Skype 서버 2015 Enterprise Edition 영구 채팅 서버를 설치하는 경우 영구 채팅 파일 저장소를 설치하는 것이 좋습니다.
    
- 비즈니스용 Skype 서버 2015 Standard 버전과 함께 영구 채팅 서버를 설치하는 경우 로컬 SQL Server Express 인스턴스에 영구 채팅 저장소 백 엔드 서버를 배포할 수 있습니다.
    
- 영구 채팅 데이터베이스(mgc) 및 준수 데이터베이스(mgccomp)는 동일한 데이터베이스 인스턴스 또는 다른 SQL Server 서버에 위치할 SQL 있습니다.
    
데이터베이스 서버 플랫폼을 준비하려면 각 컴퓨터가 하드웨어 요구 사항을 충족하는지 확인한 다음 필요한 소프트웨어를 설치합니다. 영구 채팅 데이터베이스 서버용 서버 플랫폼에는 2015년 백 엔드 데이터베이스 서버와 비즈니스용 Skype 서버 하드웨어가 필요합니다. 자세한 내용은 [server requirements for 비즈니스용 Skype 서버 2015을 참조하세요.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나를 설치해야 합니다.

- Microsoft SQL Server 2017의 최신 서비스 팩을 제공합니다.

- Microsoft SQL Server 2016 서비스 팩 1을 설치하고, 비즈니스용 Skype 서버 누적 업데이트 7 이상 릴리스에서 실행해야 합니다. 최신 서비스 팩을 SQL Server 2016을 실행하는 것이 좋습니다. 2016을 설치하는 방법에 대한 자세한 Microsoft SQL Server 설치 SQL Server [2016를 참조합니다.](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)

- Microsoft SQL Server 2014 및 2014년 비즈니스용 Skype 서버 누적 업데이트 6 이상 릴리스에서 실행해야 합니다. 최신 서비스 팩을 SQL Server 2014를 실행하는 것이 좋습니다. 2014를 설치하는 방법에 대한 자세한 Microsoft SQL Server Install [SQL Server 2014를 참조합니다.](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)

- Microsoft SQL Server 2012(64비트 버전) 최신 서비스 팩을 실행하는 것이 좋습니다. 2012를 설치하는 방법에 Microsoft SQL Server 자세한 내용은 [Install SQL Server 2012를 참조합니다.](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))

## <a name="persistent-chat-server-certificate-requirements"></a>영구 채팅 서버 인증서 요구 사항

인증서를 구하고, SQL Server 데이터베이스를 만들고, 파일 저장소를 만드는 데 대한 자세한 내용은 [Deploy 비즈니스용 Skype 서버 2015를 참조합니다.](../../deploy/deploy.md) 
  
## <a name="for-more-information"></a>자세한 내용

하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 다음 항목을 참조하십시오.
  
- [비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [2015년 비즈니스용 Skype 서버 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
