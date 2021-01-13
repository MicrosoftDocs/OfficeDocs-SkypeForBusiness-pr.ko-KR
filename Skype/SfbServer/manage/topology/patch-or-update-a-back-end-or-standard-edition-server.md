---
title: 비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '요약: 비즈니스용 Skype 서버에서 백 엔드 서버에 업데이트 또는 패치를 설치하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826308"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
 
**요약:** 비즈니스용 Skype 서버에서 백 엔드 서버에 업데이트 또는 패치를 설치하는 방법을 자세히 알아보습니다.
  
이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치하는 방법을 설명합니다.
  
업그레이드하는 동안 백 엔드 서버가 30분 이상 중단되는 경우에는 사용자가 복구 모드로 전환될 수 있습니다. 업그레이드가 완료되고 백 엔드 서버가 다시 풀의 프런트 엔드 서버에 연결되면 사용자가 전체 기능 모드로 복구됩니다. 업그레이드에 30분 미만이 걸리는 경우에는 사용자에게 영향이 없습니다.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>백 엔드 서버 또는 Standard Edition 서버를 업데이트하는 경우

1. CsAdministrator 역할의 구성원으로 업그레이드할 서버에 로그온합니다.
    
2. 업데이트를 다운로드한 후 로컬 하드 디스크로 압축을 풉니다.
    
3. 비즈니스용 Skype 서버 관리 셸을 시작합니다. **시작,** **모든** 프로그램, 비즈니스용 **Skype,** 비즈니스용 **Skype** 서버 관리 셸을 클릭합니다.
    
4. 비즈니스용 Skype 서버 서비스를 중지합니다. 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. World Wide Web 서비스를 중지합니다. 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    net stop w3svc
   ```

6. 비즈니스용 Skype 서버 관리 셸 창을 모두 닫습니다.
    
7. 업데이트를 설치합니다.
    
8. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
9. 비즈니스용 Skype 서버 서비스를 다시 중지하여 GAC(전역 어셈블리 캐시) -d 어셈블리를 catch합니다. 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. World Wide Web 서비스를 다시 시작합니다. 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    net start w3svc
    ```

11. 다음 중 하나를 수행하여 SQL Server 변경 내용을 적용합니다.
    
    - 이 서버가 Enterprise Edition 백 엔드 서버인 경우 보관 또는 모니터링 데이터베이스와 같이 이 서버에 함께 있는 데이터베이스가 없는 경우 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Enterprise Edition 백 엔드 서버가고 이 서버에 함께 있는 데이터베이스가 있는 경우 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Standard Edition 서버인 경우 명령줄에 다음을 입력합니다.
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
