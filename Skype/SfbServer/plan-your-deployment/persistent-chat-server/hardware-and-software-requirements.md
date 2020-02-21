---
title: 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 요약:이 항목을 읽으면 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213234"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항
 
**요약:** 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.
  
영구 채팅 서버는 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 함께 설치할 수 있습니다. 요구 사항은 설치한 비즈니스용 Skype 서버 2015 및 비즈니스의 성능 요구 사항에 따라 달라 집니다. Enterprise Edition은 최대 8만 명의 동시 사용자를 지원할 수 있습니다. Standard Edition은 최대 2만 명의 동시 사용자를 지원할 수 있습니다. 영구 채팅은 프런트 엔드 구성 요소와 백 엔드 SQL 데이터베이스 구성 요소로 구성 됩니다.
  
영구 채팅 서버를 배포 하기 전에 다음 하드웨어 및 소프트웨어 요구 사항이 충족 되는지 확인 해야 합니다.
  
- 비즈니스용 Skype 서버 2015, 영구 채팅 서버, 데이터베이스 서버 및 파일 서버를 지원 하기 위한 최소 요구 사항을 충족 하는 하드웨어입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
    
- 지원 되는 운영 체제 및 데이터베이스 소프트웨어
    
    지원 되는 운영 체제 및 데이터베이스 소프트웨어 및 Windows 업데이트 요구 사항에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
    
- 비즈니스용 Skype 서버 2015 프런트 엔드 서버 프런트 엔드 서버는 SIP (Session 착수 프로토콜) 라우팅의 기반 이며 영구 채팅 서버를 실행 하는 컴퓨터와 가능한 영구 채팅 기능을 사용 하 여 통신을 수행 합니다. 
    
- 메시지 큐 소프트웨어 영구 채팅 서버 및 영구 채팅 준수 서비스 (배포 된 경우)에 사용 됩니다.
    
다음 섹션에서는 영구 채팅 서버 및 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.

> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참조 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능을 필요로 하는 사용자를 팀으로 마이그레이션하거나 비즈니스용 Skype 서버 2015을 계속 사용 하는 것이 좋습니다. 
  
## <a name="front-end-server-requirements"></a>프런트 엔드 서버 요구 사항

프런트 엔드 서버 요구 사항은 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition에 영구 채팅 서버를 배포 하는 지에 따라 달라 집니다.
  
- 비즈니스용 Skype 서버 2015 Enterprise Edition과 영구 채팅 서버를 배포 하는 경우 Enterprise Edition 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 영구 채팅 서버 프런트 엔드 서버를 배포할 수 있습니다. 비즈니스용 Skype 서버 2015 프런트 엔드 서버에서는 영구 채팅 프런트 엔드 서버를 함께 배치할 수 없습니다. 
    
    단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다. 최대 4 개의 활성 프런트 엔드와 함께 영구 채팅 서버 풀을 사용 하 여 총 8만 동시 사용자를 지원할 수 있습니다. 
    
- 비즈니스용 Skype 서버 2015 Standard Edition과 함께 영구 채팅 서버를 배포 하는 경우에는 프런트 엔드 서버와 영구 채팅을 함께 배치할 수 있습니다. 이 단일 서버 배포에서는 최대 2만 명의 사용자를 지원할 수 있습니다. 
    
## <a name="persistent-chat-server-database-requirements"></a>영구 채팅 서버 데이터베이스 요구 사항

영구 채팅 서버를 사용 하려면 대화방 기록과 콘텐츠, 구성 데이터, 사용자 프로 비전 데이터 및 기타 관련 메타 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다. 필요한 경우 영구 채팅 준수 데이터베이스를 사용 하 여 준수 데이터를 저장 합니다. 영구 채팅 데이터베이스는 동일한 SQL Server 또는 백 엔드 데이터베이스와 동일한 SQL 인스턴스에 배치 된 수 있습니다. 
  
- 최적의 성능을 보장 하기 위해 비즈니스용 Skype 서버 2015 Enterprise Edition과 함께 영구 채팅 서버를 설치 하는 경우에는 영구 채팅 파일 저장소를 설치 하는 것이 좋습니다.
    
- 비즈니스용 Skype 서버 2015 Standard edition과 함께 영구 채팅 서버를 설치 하는 경우 로컬 SQL Server Express 인스턴스에 영구 채팅 저장소 백 엔드 서버를 배포할 수 있습니다.
    
- 영구 채팅 데이터베이스 (mgc) 및 준수 데이터베이스 (mgccomp)는 동일한 SQL Server 인스턴스나 다른 SQL 서버에 있을 수 있습니다.
    
데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 해야 합니다. 영구 채팅 데이터베이스 서버에 대 한 서버 플랫폼은 비즈니스용 Skype 서버 2015 백 엔드 데이터베이스 서버와 동일한 하드웨어를 사용 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
  
데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인해 보십시오.

- 최신 서비스 팩을 포함 하는 Microsoft SQL Server 2017

- Microsoft SQL Server 2016 서비스 팩 1을 사용 하며, 비즈니스용 Skype 서버 누적 업데이트 7 이상 버전을 실행 해야 합니다. 최신 서비스 팩이 적용 된 SQL Server 2016를 실행 하는 것이 권장 됩니다. Microsoft SQL Server 2016을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)를 참조 하십시오.

- Microsoft SQL Server 2014 및 비즈니스용 Skype 서버 누적 업데이트 6 이상 버전에서 실행 해야 합니다. 최신 서비스 팩이 적용 된 SQL Server 2014를 실행 하는 것이 권장 됩니다. Microsoft SQL Server 2014을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)를 참조 하십시오.

- Microsoft SQL Server 2012 (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다. Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)를 참조 하십시오.

## <a name="persistent-chat-server-certificate-requirements"></a>영구 채팅 서버 인증서 요구 사항

인증서 획득, SQL Server 데이터베이스 만들기 및 파일 저장소 만들기에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015](../../deploy/deploy.md)를 참조 하세요. 
  
## <a name="for-more-information"></a>자세한 내용

하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
  
- [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

