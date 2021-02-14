---
title: 모니터링 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 모니터링 서버를 제거한 후 서버 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753330"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>모니터링 서버용 SQL Server 데이터베이스 제거

모니터링 서버를 제거한 후 서버 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 SQL Server 데이터베이스를 제거하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 여는 경우
    
2. 토폴로지 작성기에서  공유 구성 요소로 이동한 다음 저장소를 SQL Server **제거되거나** 다시 구성한 모니터링 서버와 연결된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭한 다음 **삭제를** 클릭합니다.
    
3. 토폴로지를 게시한 후 복제 상태를 확인합니다.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server에서 데이터베이스 파일을 제거하려면

1. SQL Server 기반 서버에서 데이터베이스를 제거하려면 데이터베이스 파일을 제거할 SQL Server 서버의 SQL Server sysadmins 그룹의 구성원이 되어야 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.
    
3. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서  _\<FQDN\>_ 데이터베이스 서버의 FQDN(FQDN) 및 선택적 명명된 데이터베이스  _\<instance\>_ 인스턴스입니다. 
    
4. **Uninstall-CsDataBase** cmdlet에 작업을 확인하라는 메시지가 표시되면 정보를 읽은 다음 Y(또는 Enter)를 눌러 계속하거나 N을 누를 경우 cmdlet을 중지하려는 경우 Enter를 누를 수 있습니다(오류가 있는 경우). 
    

