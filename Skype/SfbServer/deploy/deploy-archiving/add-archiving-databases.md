---
title: 비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '요약: 이 항목을 읽고 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가하는 방법을 설명합니다.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820678"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가
 
**요약:** 이 항목을 읽고 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가하는 방법을 설명합니다.
  
보관을 지원하도록 배포를 구성하려면 먼저 토폴로지에 보관을 통합해야 합니다. 이 항목의 정보는 토폴로지 작성기에서 다음을 하는 방법을 설명합니다.
  
- 토폴로지에 보관 데이터베이스를 추가합니다.
    
- 업데이트된 토폴로지 게시를 통해 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가합니다.
    
> [!NOTE]
> Microsoft Exchange 통합을 사용하여 배포의 모든 사용자에 대해 Exchange 서버에 보관 데이터 및 파일을  저장하려면 보관 저장소 또는 SQL Server 저장소 미러링 SQL Server 지정하지 **않습니다.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>토폴로지에 보관 데이터베이스 추가

1. 비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.
    
2. 토폴로지 작성기를 시작합니다.
    
3. 콘솔 트리에서 보관을 배포할 프런트 엔드 풀로 이동한 다음 보관을 배포할 프런트 엔드 풀의 이름을 클릭합니다.
    
4. **동작** 메뉴에서 **속성 편집** 을 클릭합니다. 
    
5. **속성 편집** 대화 상자에서 **일반** 을 클릭합니다.
    
6. 아래쪽의 **보관** 으로 스크롤합니다.
    
7. **보관** 확인란을 선택합니다.
    
8. 보관 **SQL Server 저장소에서 다음** 중 하나를 합니다.
    
   - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다. 모든 사용자가 Microsoft Exchange Server 2013 이상에 있는 경우 Exchange의 모든 사용자에 대한 비즈니스용 Skype 통신을 보관할 수 있습니다. 이 경우 보관 저장소를 구성할 SQL Server 없습니다.
    
   - 새 SQL Server 저장소를 지정하려면 새로하기를 클릭한 다음 새 SQL Server **저장소** 정의 대화 상자에서 다음을 선택합니다. 
    
   - FQDN의 SQL Server 저장소를 만들 서버의 **FQDN을** SQL Server 지정합니다.
    
   - **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
   - 지정된 SQL Server 인스턴스가 미러링 관계에 있는 경우  이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.
    
9. 저장소 미러링을 SQL Server 사용하려면 SQL Server 저장소 미러링 **사용을** 선택하고 다음을 합니다.
    
   - 기존 SQL Server 저장소를 미러링에 사용하려면  보관 SQL Server 저장소 미러 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭합니다.
    
   - 미러링에 사용할 새 SQL Server 저장소를 지정하려면 새로 고침을 클릭한 다음 새 SQL Server 저장소 정의 **대화** 상자에서 다음 중 하나를 선택합니다.
    
     a. FQDN의 SQL Server 저장소를 만들 SQL Server **FQDN을** SQL Server 지정합니다.
    
     b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
     c. 지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.
    
   - SQL Server 미러링을 사용하도록 설정하고 SQL Server 미러링 서버(기본 SQL Server 및 미러 인스턴스의 상태 검색이 가능하도록 별도의 세 번째 SQL Server 인스턴스)를 포함하려면 SQL Server 미러링크 사용 확인란을 선택하고 다음 중 하나를 수행하십시오. 
    
     a. FQDN을 SQL Server 새 미러링 SQL Server 만들 서버의 **FQDN을** 지정합니다.
    
     b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.
    
     c. 지정된 SQL Server 인스턴스가 미러링 관계에 있는 경우  이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.
    
10. 구성을 저장하려면 **확인** 을 클릭합니다.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>업데이트된 토폴로지 게시를 통해 배포에 보관 데이터베이스 추가

1. 비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.
    
    > [!NOTE]
    > 로컬 Users 그룹의 구성원이지만 토폴로지 게시를 위해 계정을 사용하여 토폴로지 정의할 수 있습니다. 토폴로지 작성기에서 필요한 경우 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 비즈니스용 Skype 서버 파일 저장소에 사용중인 파일 공유에 대한 모든 권한(읽기, 쓰기 및 수정)을 가진 계정을 사용(토폴로지 작성기에서 필요한 DACL(사용자 지정 액세스 제어 목록)을 구성할 수 있도록 해야 합니다.
  
2. 토폴로지 작성기에서 이전 섹션에서 만든 토폴로지 열기
    
3. 콘솔 트리에서 비즈니스용 **Skype** 서버를 마우스 오른쪽 단추로 클릭한 다음 토폴로지 **게시를 클릭합니다.**
    
4. **토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.
    
5. **데이터베이스 만들기** 페이지에서 데이터베이스가 선택되었는지 확인하고 **다음** 을 클릭합니다. 
    
    > [!NOTE]
    > 데이터베이스를 만드는 데 적합한 권한이 없으면 데이터베이스 선택을 취소하고 적합한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다. > 토폴로지 작성기에서 전용 SQL 서버의 데이터베이스만 설치할 수 있습니다. 다른 서버 구성 요소와 함께 배치된 SQL Server의 데이터베이스는 해당 컴퓨터의 로컬 설정을 실행하여 설치해야 합니다. 
  
6. **게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침** 을 클릭합니다.
    
    > [!IMPORTANT]
    > 토폴로지를 게시한 후 콘텐츠를 보관할 수 있으려면 먼저 보관에 대한 옵션 및 정책을 구성해야 합니다. 자세한 내용은 비즈니스용 Skype 서버에 대한 보관 옵션 구성 및 비즈니스용 [Skype](configure-archiving-options.md) 서버에 대한 보관 정책 [구성을 참조하세요.](configure-archiving-policies.md) 
  

