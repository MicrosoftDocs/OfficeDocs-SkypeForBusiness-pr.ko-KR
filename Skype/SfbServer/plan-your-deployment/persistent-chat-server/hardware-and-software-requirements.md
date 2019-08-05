---
title: 영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197934"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항
 
**요약:** 이 항목에서는 비즈니스용 Skype Server 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대해 자세히 알아보세요.
  
영구 채팅 서버는 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 함께 설치할 수 있습니다. 요구 사항은 설치 된 비즈니스용 Skype 서버 2015의 버전과 비즈니스의 성능 요구 사항에 따라 달라 집니다. Enterprise Edition은 최대 8만 동시 사용자를 지원할 수 있습니다. 스탠더드 버전은 최대 2만 동시 사용자를 지원할 수 있습니다. 영구 채팅은 프런트 엔드 구성 요소 및 백 엔드 SQL 데이터베이스 구성 요소로 구성 됩니다.
  
영구 채팅 서버를 배포 하기 전에 다음 하드웨어 및 소프트웨어 요구 사항이 충족 되는지 확인 해야 합니다.
  
- 비즈니스용 Skype 서버 2015, 영구 채팅 서버, 데이터베이스 서버, 파일 서버를 지원 하기 위한 최소 요구 사항을 충족 하는 하드웨어입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
    
- 지원 되는 운영 체제 및 데이터베이스 소프트웨어
    
    지원 되는 운영 체제 및 데이터베이스 소프트웨어 및 Windows 업데이트 요구 사항에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
    
- 비즈니스용 Skype 서버 2015 프런트 엔드 서버. 프런트 엔드 서버는 SIP (세션 초기화 프로토콜) 라우팅의 기반 이므로 영구 채팅 서버를 실행 하는 컴퓨터와 영구 채팅 기능을 통해 통신 합니다. 
    
- 메시지 대기열 소프트웨어. 영구 채팅 서버와 영구 채팅 준수 서비스 (배포 된 경우)에서 사용 합니다.
    
다음 섹션에서는 영구 채팅 서버와 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.

> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 
  
## <a name="front-end-server-requirements"></a>프런트 엔드 서버 요구 사항

프런트 엔드 서버 요구 사항은 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 영구 채팅 서버를 배포 하 고 있는지 여부에 따라 달라 집니다.
  
- 비즈니스용 Skype Server 2015 Enterprise Edition을 사용 하 여 영구 채팅 서버를 배포 하는 경우 엔터프라이즈 버전 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 영구 채팅 서버 프런트 엔드 서버를 배포할 수 있습니다. 비즈니스용 Skype 서버 2015 프런트 엔드 서버에서 영구 채팅 프런트 엔드 서버를 collocate 수 없습니다. 
    
    단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다. 최대 4 개의 활성 프론트 엔드와 영구 채팅 서버 풀을 사용 하 여 총 8만 동시 사용자를 지원할 수 있습니다. 
    
- 비즈니스용 Skype Server 2015 Standard Edition과 영구 채팅 서버를 배포 하는 경우 프런트 엔드 서버와 영구 채팅을 collocate 수 있습니다. 이 단일 서버 배포는 최대 2만 사용자를 지원할 수 있습니다. 
    
## <a name="persistent-chat-server-database-requirements"></a>영구 채팅 서버 데이터베이스 요구 사항

영구 채팅 서버에는 채팅방 기록과 콘텐츠, 구성 데이터, 사용자 프로 비전 데이터 및 기타 관련 메타 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다. 필요에 따라 지속적인 채팅 준수 데이터베이스를 사용 하 여 규정 준수 데이터를 저장 합니다. 영구 채팅 데이터베이스는 동일한 SQL Server 또는 백 엔드 데이터베이스와 동일한 SQL 인스턴스에서 collocated 수 있습니다. 
  
- 비즈니스용 Skype Server 2015 Enterprise Edition과 영구 채팅 서버를 설치 하는 경우 최적의 성능을 유지 하려면 영구 채팅 파일 저장소를 설치 하는 것이 좋습니다.
    
- 비즈니스용 Skype Server 2015 Standard edition과 영구 채팅 서버를 설치 하는 경우 로컬 SQL Server Express 인스턴스에서 영구 채팅 저장소 백 엔드 서버를 배포할 수 있습니다.
    
- Mgc (지속적인 채팅 데이터베이스) 및 mgccomp (준수 데이터베이스)는 SQL Server의 동일한 인스턴스나 다른 SQL 서버에 있을 수 있습니다.
    
데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 합니다. 영구 채팅 데이터베이스 서버의 서버 플랫폼에는 비즈니스용 Skype 서버 2015 백 엔드 데이터베이스 서버와 동일한 하드웨어가 필요 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.
  
데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인 합니다.

- 최신 서비스 팩을 사용 하는 Microsoft SQL Server 2017.

- Microsoft SQL Server 2016 (서비스 팩 1)에서는 비즈니스용 Skype Server 누적 업데이트 7 이상 버전으로 실행 해야 합니다. 최신 서비스 팩을 사용 하 여 SQL Server 2016을 실행 하는 것이 좋습니다. Microsoft SQL Server 2016을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2016 설치](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)를 참조 하세요.

- Microsoft SQL Server 2014를 사용 하 고 있으며 비즈니스용 Skype Server 누적 업데이트 6 이상 릴리스에서 실행 해야 합니다. 최신 서비스 팩을 사용 하 여 SQL Server 2014을 실행 하는 것이 좋습니다. Microsoft SQL Server 2014을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2014 설치](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)를 참조 하세요.

- Microsoft SQL Server 2012 (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다. Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2012 설치](https://go.microsoft.com/fwlink/p/?LinkID=248559)를 참조 하세요.

## <a name="persistent-chat-server-certificate-requirements"></a>영구 채팅 서버 인증서 요구 사항

인증서를 획득 하 고 SQL Server 데이터베이스를 만들고 파일 저장소를 만드는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015](../../deploy/deploy.md)을 참조 하세요. 
  
## <a name="for-more-information"></a>자세한 내용은

하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 다음 항목을 참조 하세요.
  
- [비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [비즈니스용 Skype 서버 2015에 대한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

