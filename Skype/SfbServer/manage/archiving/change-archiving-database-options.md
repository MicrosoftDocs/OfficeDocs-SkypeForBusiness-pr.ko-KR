---
title: 비즈니스용 Skype 서버의 보관 데이터베이스 옵션 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 데이터베이스 옵션을 변경 하는 방법을 알아보세요.'
ms.openlocfilehash: c489117894eca69141ac07860c45aa07eb5916ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818980"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 보관 데이터베이스 옵션 변경

**요약:** 비즈니스용 Skype 서버에 대 한 보관 데이터베이스 옵션을 변경 하는 방법에 대해 알아봅니다.
  
사용자의 저장소 보관을 위해 SQL Server 저장소를 사용 하 여 보관을 배포 하는 경우 다음과 같은 데이터베이스 저장소 변경 내용을 적용할 수 있습니다.
  
- 보관 저장소에 다른 SQL Server 데이터베이스를 사용 합니다. 여기에는 기본 보관 데이터베이스와 SQL Server 미러링에 사용 하는 데이터베이스가 포함 됩니다.
    
- Exchange 서버에 보관 데이터 및 파일을 저장 하려면 Microsoft Exchange 통합으로 전환 합니다. 모든 사용자가 Exchange 서버에 있고 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용 하려는 경우에는 토폴로지에서 SQL Server 스토어 데이터베이스를 제거 해야 합니다. 
    
이러한 변경 작업을 수행 하려면 토폴로지 작성기를 실행 하 고 변경한 다음 토폴로지를 다시 게시 해야 합니다. Exchange 서버에 있지 않은 비즈니스용 Skype 사용자가 없는 경우 **Sql server 저장소 보관** 을 지정 하거나 **sql server 저장소 미러링 정보를 사용 하도록 설정** 하지 마세요.
  
## <a name="change-archiving-database-options"></a>보관 데이터베이스 옵션 변경

1. 비즈니스용 Skype 서버를 실행 중이거나 비즈니스용 Skype 서버 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.
    
    > [!NOTE]
    > 로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 구성 요소를 추가 하는 데 필요한 토폴로지를 게시 하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원 인 계정을 사용 해야 하며, 비즈니스용 Skype Server 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있는 경우 (즉, 토폴로지 작성기가 필요한 임의 액세스 제어를 구성할 수 있도록 합니다. 목록 (Dacl) 또는 해당 권한이 있는 계정
  
2. 토폴로지 작성기를 시작 합니다.
    
3. 콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경 하려는 프런트 엔드 풀의 이름을 클릭 합니다.
    
4. **작업** 메뉴에서 **속성 편집**을 클릭 합니다. 
    
5. **속성 편집** 대화 상자에서 **일반**을 클릭 합니다.
    
6. 아래로 스크롤하여 **보관**합니다.
    
7. **보관**에서 다음을 수행 합니다.
    
   - 다른 기존 SQL Server 저장소로 변경 하려면 **Sql server Store 보관**아래에 있는 드롭다운 목록 상자에서 다음을 수행 합니다.
    
   - 기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.
    
   - 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.
    
     - 기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.
    
     - 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.
    
       - **Sql SERVER fqdn**에서 새 SQL server 저장소를 만들 서버의 FQDN을 지정 합니다.
    
       - 기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.
    
       - 지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.
    
   - 미러링 용 SQL Server 저장소를 추가 하거나 SQL server 스토어 미러링을 위해 다른 기존 SQL Server 저장소에 변경 하려면 **Sql server 스토어 미러링을 사용 하도록**선택 하 고 다음을 수행 합니다.
    
     - 미러링에 대 한 기존 SQL Server 저장소를 사용 하려면 **Sql server 저장소 미러 서버 보관** 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭 합니다.
    
     - 미러링할 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
       에서. **Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 fqdn을 지정 합니다.
    
       b. 기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.
    
       c. 지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.
    
   - SQL Server 미러링 기능을 사용 하도록 설정 하 고 SQL Server 미러링 모니터를 추가 하거나 변경 하려면 (기본 SQL Server server 서버와 미러 인스턴스의 상태를 검색할 수 있는 별도의 SQL Server 인스턴스), **Sql server 미러링 미러링 모니터를 사용 하 여 자동 장애 조치 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
    
      에서. **Sql SERVER fqdn**에서 새 SQL server 미러링 감시를 만들 서버의 FQDN을 지정 합니다.
    
      b. 기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 미러링 모니터에 사용할 인스턴스를 지정 합니다.
    
      c. 지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.
    
   - Exchange 서버에 보관 데이터 및 파일을 저장 하는 Microsoft Exchange 통합으로 전환 하려면 (배포의 모든 사용자가 Exchange 서버에 있는 경우) 데이터베이스 보관에 대 한 모든 정보를 삭제 합니다.
    
     > [!IMPORTANT]
     > Exchange 서버에 있지 않은 비즈니스용 Skype 사용자가 있는 경우 SQL Server 스토어 정보를 삭제 하지 마세요. 
  
8. 구성을 저장 하려면 **확인**을 클릭 합니다.
    
    > [!IMPORTANT]
    > 토폴로지 작성기에서 변경한 내용은 새 토폴로지를 게시할 때까지 적용 되지 않습니다. 자세한 내용은 [비즈니스용 Skype 서버의 기존 배포에 보관 데이터베이스 추가](../../deploy/deploy-archiving/add-archiving-databases.md)를 참조 하세요. 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 데이터베이스의 위치 변경

대부분의 경우 보관 서버를 설치할 때 지정 되는 보관 데이터베이스의 위치를 변경할 필요는 없습니다. 그러나 하드웨어 오류 또는 기타 문제가 발생 하는 경우 **Set-CsArchivingServer** cmdlet을 사용 하 여 새 데이터베이스에 서버 보관을 가리킬 수 있습니다.
  
다음 예에서는 ArchivingServer: atl-cs-001.contoso.com 보관 서버에 대 한 보관 데이터베이스의 위치를 변경 합니다. 이 예제에서는 새 데이터베이스가 ArchivingDatabase: atl-sql-001.contoso.com:에 있습니다.
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


