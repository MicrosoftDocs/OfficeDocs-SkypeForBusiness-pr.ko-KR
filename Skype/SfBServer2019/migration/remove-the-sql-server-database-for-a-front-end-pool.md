---
title: 프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거
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
description: 프런트 엔드 풀을 제거하거나 다른 데이터베이스를 사용하기 위해 풀을 다시 구성한 후 풀 데이터를 호스팅하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
ms.openlocfilehash: 01a28beabb85aa7cda25043680537f519872d58654dee5418f03ae9f5f702a19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340324"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거

프런트 엔드 풀을 제거하거나 다른 데이터베이스를 사용하기 위해 풀을 다시 구성한 후 풀 데이터를 호스팅하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 SQL Server 데이터베이스를 제거하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 열고 기존 토폴로지 다운로드를 합니다. 
    
2. 토폴로지 작성기에서  공유 구성 요소로 이동한 다음 **저장소를 SQL Server** 제거되거나 다시 구성된 프런트 엔드 풀과 연결된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**
    
3. 토폴로지 게시 후 복제 상태를 검사합니다. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>서버의 사용자 및 응용 프로그램 데이터베이스를 SQL

1. SQL 서버에서 데이터베이스를 제거하려면 데이터베이스 파일을 제거할 SQL Server 서버에 대한 SQL sysadmins 그룹의 구성원이 되어야 합니다. 
    
2. 관리 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
3. 풀 사용자 저장소의 데이터베이스를 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 는 데이터베이스 _\<FQDN\>_ 서버의 FQDN(FQDN)으로, 명명된 데이터베이스 인스턴스(즉, 정의된 경우)입니다. _\<instance\>_ 
    
4. 풀 응용 프로그램 저장소의 데이터베이스를 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 는 데이터베이스  _\<FQDN\>_ 서버의 FQDN으로, 명명된 데이터베이스 인스턴스(즉, 정의된  _\<instance\>_ 경우)입니다. 
    
5. **Uninstall-CsDataBase** cmdlet에 작업을 확인하라는 메시지가 표시되면 정보를 읽은 다음 Y(또는 Enter)를 눌러 계속 진행하거나, N을 누운 다음 cmdlet을 중지하려는 경우 Enter를 누르고(오류가 있는 경우) 
    

