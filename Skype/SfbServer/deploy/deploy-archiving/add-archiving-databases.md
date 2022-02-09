---
title: 보관 데이터베이스를 기존 배포에 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '요약: 이 항목을 통해 보관 데이터베이스를 배포에 추가하는 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 3bc4e14998e45803518436bb180906e9c79e14f4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401582"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>보관 데이터베이스를 기존 배포에 비즈니스용 Skype 서버
 
**요약:** 이 항목을 통해 보관 데이터베이스를 배포에 추가하는 방법을 비즈니스용 Skype 서버 있습니다.
  
보관을 지원하도록 배포를 구성하려면 먼저 토폴로지에 보관을 통합해야 합니다. 이 항목의 정보는 토폴로지 작성기에서 다음을 하는 방법에 대해 설명하고 있습니다.
  
- 토폴로지에 보관 데이터베이스를 추가합니다.
    
- 업데이트된 토폴로지 게시를 통해 보관 데이터베이스를 비즈니스용 Skype 서버 배포합니다.
    
> [!NOTE]
> Microsoft Exchange 통합을 사용하여 배포의 모든 사용자에 대해 Exchange 서버에 보관 데이터 및 파일을 저장하려면 보관 저장소 또는 SQL Server **Store** 미러링 정보 SQL Server 지정하지 않습니다.
  
### <a name="add-an-archiving-database-to-your-topology"></a>토폴로지에 보관 데이터베이스 추가

1. 비즈니스용 Skype 서버 실행 중인 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 사용하는 계정)을 사용하여 로그온합니다.
    
2. 토폴로지 작성기를 시작합니다.
    
3. 콘솔 트리에서 보관을 배포할 프런트 엔드 풀로 이동한 다음 보관을 배포할 프런트 엔드 풀의 이름을 클릭합니다.
    
4. **동작** 메뉴에서 **속성 편집** 을 클릭합니다. 
    
5. **속성 편집** 대화 상자에서 **일반** 을 클릭합니다.
    
6. 아래쪽의 **보관** 으로 스크롤합니다.
    
7. **보관** 확인란을 선택합니다.
    
8. 보관 **SQL Server 저장소에서 다음** 중 하나를 진행합니다.
    
   - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다. 모든 사용자가 Microsoft Exchange Server 2013 이상에 있는 경우 모든 사용자의 비즈니스용 Skype 통신을 보관할 Exchange. 이 경우 보관 저장소를 구성할 SQL Server 없습니다.
    
   - 새 SQL Server 저장소를 지정하려면 새로 고안을 클릭한 다음 새 SQL Server 저장소 정의 대화 **상자** 에서 다음을 클릭합니다.
    
   - FQDN에 SQL Server 저장소를 만들 서버의 **FQDN** 을 SQL Server 지정합니다.
    
   - **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
   - 지정한 SQL Server 인스턴스가 미러링 관계에 있는 경우 이 SQL 인스턴스가 미  러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
9. 저장소 미러링을 SQL Server 사용하려면 SQL Server 저장소 미러링 **사용을** 선택한 후 다음을 합니다.
    
   - 기존 SQL Server 저장소를 미러링에 사용하려면 보관 SQL Server 저장소 미러  드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭합니다.
    
   - 미러링용 새 SQL Server 저장소를 지정하려면 새로 고침을 클릭한 다음 새 SQL Server **저장소 정의 대화 상자** 에서 다음 중 하나를 선택합니다.
    
     a. FQDN에 SQL Server 저장소를 만들 SQL Server **FQDN** 을 SQL Server 지정합니다.
    
     b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
     c. 지정한 SQL Server 인스턴스가 미러링 관계에 있는 경우 이 SQL 인스턴스가 미  러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
   - SQL Server 미러링을 사용하도록 설정하고 SQL Server 미러링을 포함하려는 경우(기본 SQL Server 및 미러 인스턴스의 상태 감지를 할 수 있는 별도의 세 번째 SQL Server 인스턴스)를 포함하려면 자동 장애 조치(**failover)** 를 사용하려면 SQL Server 미러링링크 사용 미러링크를 선택합니다.  확인란을 확인한 다음 다음 중 하나를 선택합니다.
    
     a. FQDN SQL Server 새 미러링 SQL Server 만들 서버의 **FQDN** 을 지정합니다.
    
     b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.
    
     c. 지정한 SQL Server 인스턴스가 미러링 관계에 있는 경우 이 SQL 인스턴스가 미  러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
10. 구성을 저장하려면 **확인** 을 클릭합니다.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>업데이트된 토폴로지 게시를 통해 배포에 보관 데이터베이스 추가

1. 비즈니스용 Skype 서버 실행 중인 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 사용하는 계정)을 사용하여 로그온합니다.
    
    > [!NOTE]
    > 로컬 Users 그룹의 구성원인 계정을 사용하여 토폴로지 정의할 수 있지만 토폴로지(토폴로지에 서버를 추가하는 데 필요한 토폴로지)를 게시하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 모든 권한(읽기,  토폴로지 작성기에서 필요한 DACL(사용자용 액세스 제어 목록) 또는 동등한 권한이 있는 계정을 구성할 수 있도록 비즈니스용 Skype 서버 파일 저장소에 대해 사용하는 파일 공유에 대한 쓰기 및 수정)
  
2. 토폴로지 작성기에서 이전 섹션에서 만든 토폴로지 열기
    
3. 콘솔 트리에서 마우스 오른쪽 단추로 비즈니스용 Skype 서버 토폴로지 **게시를 클릭합니다**.
    
4. **토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.
    
5. **데이터베이스 만들기** 페이지에서 데이터베이스가 선택되었는지 확인하고 **다음** 을 클릭합니다. 
    
    > [!NOTE]
    > 데이터베이스를 만드는 데 적합한 권한이 없으면 데이터베이스 선택을 취소하고 적합한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다. > 전용 서버의 SQL 토폴로지 작성기에서만 설치할 수 있습니다. 다른 서버 구성 요소와 함께 배치된 SQL Server의 데이터베이스는 해당 컴퓨터의 로컬 설정을 실행하여 설치해야 합니다. 
  
6. **게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침** 을 클릭합니다.
    
    > [!IMPORTANT]
    > 토폴로지를 게시한 후 콘텐츠를 보관할 수 있으려면 먼저 보관에 대한 옵션 및 정책을 구성해야 합니다. 자세한 내용은 [Configure archiving options for 비즈니스용 Skype 서버](configure-archiving-options.md) [및 Configure archiving policies for 비즈니스용 Skype 서버](configure-archiving-policies.md). 
  

