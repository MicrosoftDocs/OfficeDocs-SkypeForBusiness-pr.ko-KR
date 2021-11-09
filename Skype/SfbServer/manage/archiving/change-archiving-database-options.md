---
title: 2013에서 보관 데이터베이스 옵션 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '요약: 사용자에 대한 보관 데이터베이스 옵션을 변경하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: e07c94530d71c9d31ef9f11eaef6332dbfa32d0e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847461"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>2013에서 보관 데이터베이스 옵션 비즈니스용 Skype 서버

**요약:** 사용자에 대한 보관 데이터베이스 옵션을 변경하는 비즈니스용 Skype 서버.
  
사용자에 대해 보관 저장소에 SQL Server 저장소를 사용하여 보관을 배포하는 경우 다음과 같은 데이터베이스 저장소를 변경할 수 있습니다.
  
- 보관 저장소에 SQL Server 데이터베이스를 사용합니다. 여기에는 기본 보관 데이터베이스와 기본 미러링에 사용하는 SQL Server 포함됩니다.
    
- Microsoft Exchange 통합으로 전환하여 보관 데이터 및 파일을 Exchange 서버에 저장합니다. 모든 사용자가 Exchange 서버에 있으며 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용하려는 경우 토폴로지에서 SQL Server 저장소 데이터베이스를 제거해야 합니다. 
    
이러한 변경 내용을 적용하려면 토폴로지 작성기에서 변경한 다음 토폴로지 다시 게시해야 합니다. SQL Server 서버에  SQL Server 사용자가 없는 경우를  비즈니스용 Skype 경우를 한 저장소에 보관 저장소를 지정하거나 SQL Server 미러링 사용 설정을 지정하지 Exchange 않습니다.
  
## <a name="change-archiving-database-options"></a>보관 데이터베이스 옵션 변경

1. 비즈니스용 Skype 서버 실행 중인 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 사용하는 계정)을 사용하여 로그온합니다.
    
    > [!NOTE]
    > 로컬 Users 그룹의 구성원인 계정을 사용하여 토폴로지 정의할 수 있지만 토폴로지(토폴로지에 구성 요소를 추가하는 데 필요)를 게시하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 모든 권한을 가진 계정(즉,  비즈니스용 Skype 서버 파일 저장소에 사용하는 파일 공유(즉, 토폴로지 작성기에서 필요한 DACL(사용자 재량 액세스 제어 목록) 또는 동등한 권한이 있는 계정을 구성할 수 있도록 하는 파일 공유에 대한 읽기, 쓰기 및 수정
  
2. 토폴로지 작성기를 시작합니다.
    
3. 콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경할 프런트 엔드 풀의 이름을 클릭합니다.
    
4. **동작** 메뉴에서 **속성 편집** 을 클릭합니다. 
    
5. **속성 편집** 대화 상자에서 **일반** 을 클릭합니다.
    
6. 아래쪽의 **보관** 으로 스크롤합니다.
    
7. **보관** 에서 다음을 수행합니다.
    
   - 다른 기존 SQL Server 저장소로 변경하려면 **보관 SQL Server 저장소** 아래 드롭다운 목록 상자에서 다음을 수행합니다.
    
   - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.
    
   - 새 SQL Server 저장소를 지정하려면 **새로 만들기** 를 클릭하고 **새 SQL Server 저장소 정의** 대화 상자에서 다음을 수행합니다.
    
     - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.
    
     - 새 SQL Server 저장소를 지정하려면 새로 추가를 클릭한 다음 새 SQL Server **저장소** 정의 대화 상자에서 다음을 클릭합니다.
    
       - **FQDN SQL Server** 에서 새 서버 저장소를 만들 서버의 FQDN을 SQL Server 지정합니다.
    
       - **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
       - 지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
   - 미러링용으로 SQL Server 저장소를 추가하거나 SQL Server 저장소 미러링을 위해 다른 기존 SQL Server 저장소로 변경하려면 **SQL Server 저장소 미러링 사용** 을 선택하고 다음을 수행합니다.
    
     - 기존 SQL Server 저장소를 미러링에 사용하려면  보관 저장소 SQL Server 저장소 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭합니다.
    
     - 미러링용 새 SQL Server 저장소를 지정하려면 새로 고침을 클릭한 다음 새 SQL Server **저장소** 정의 대화 상자에서 다음 중 하나를 선택합니다.
    
       a. **FQDN** SQL Server 에서 새 SQL Server 저장소를 만들 SQL Server 지정합니다.
    
       b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.
    
       c. 지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
   - SQL Server 미러링을 사용하도록 설정하고 SQL Server 미러링을 추가하거나 변경하려면(주 SQL Server 서버 및 미러 인스턴스의 상태 감지를 할 수 있는 별도의 세 번째 SQL Server 인스턴스) 자동 장애 **조치(failover)를** 사용하도록 설정하려면 SQL Server 미러링링크 사용 확인란을 선택한 다음  다음 중 하나를 합니다.
    
      a. FQDN SQL Server 에서 새 미러링 SQL Server 만들 서버의 **FQDN을** 지정합니다.
    
      b. **기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.
    
      c. 지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계에 있습니다. 확인란을 선택한 다음 미러 포트 번호에서 포트 번호를 지정합니다.
    
   - Microsoft Exchange 통합으로 전환하여 보관 데이터 및 파일을 Exchange 서버에 저장하려면(배포의 모든 사용자가 Exchange 서버에 있는 경우) 보관 데이터베이스에 대한 모든 정보를 삭제합니다.
    
     > [!IMPORTANT]
     > 비즈니스용 Skype 서버에 비즈니스용 Skype 사용자가 있는 경우 Exchange 저장소 정보를 삭제하지 SQL Server 않습니다. 
  
8. 구성을 저장하려면 **확인** 을 클릭합니다.
    
    > [!IMPORTANT]
    > 토폴로지 작성기에서 변경한 내용은 새 토폴로지 게시 전까지는 적용되지 않습니다. 자세한 내용은 [Add archiving databases to an existing deployment in 비즈니스용 Skype 서버.](../../deploy/deploy-archiving/add-archiving-databases.md) 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>보관 데이터베이스의 위치를 변경하려면 다음을 Windows PowerShell

대부분의 경우 보관 서버를 설치할 때 지정된 보관 데이터베이스의 위치를 변경할 필요가 없습니다. 그러나 하드웨어 오류 또는 기타 문제가 발생할 경우 **Set-CsArchivingServer** cmdlet을 사용하여 보관 서버를 새 데이터베이스로 설정할 수 있습니다.
  
다음 예제에서는 ArchivingServer:atl-cs-001.contoso.com 보관 서버의 위치를 변경합니다. 이 예제에서 새 데이터베이스는 ArchivingDatabase:atl-sql-001.contoso.com.
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


