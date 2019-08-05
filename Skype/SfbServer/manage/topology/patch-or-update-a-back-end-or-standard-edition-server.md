---
title: 비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '요약: 비즈니스용 Skype 서버의 백 엔드 서버에 업데이트나 패치를 설치 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187089"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
 
**요약:** 비즈니스용 Skype 서버의 백 엔드 서버에 업데이트나 패치를 설치 하는 방법에 대해 알아봅니다.
  
이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.
  
업그레이드 하는 동안 백 엔드 서버가 최소 30 분 동안 중단 되 면 사용자가 복원 모드로 전환할 수 있습니다. 업그레이드가 완료 되 고 백 엔드 서버가 풀의 프런트 엔드 서버와 다시 연결 되 면 사용자가 전체 기능으로 반환 됩니다. 업그레이드 시간이 30 분 미만이 되 면 사용자에 게 영향을 주지 않습니다.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>백 엔드 서버 또는 Standard Edition 서버를 업데이트 하려면

1. CsAdministrator 역할의 구성원으로 업그레이드 하는 서버에 로그온 합니다.
    
2. 업데이트를 다운로드 하 고 로컬 하드 디스크에 압축을 풉니다.
    
3. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management Shell**을 클릭 합니다.
    
4. 비즈니스용 Skype 서버 서비스를 중지 합니다. 명령줄에 다음을 입력 합니다.
    
    ```
    Stop-CsWindowsService
    ```

5. World Wide Web 서비스를 중지 합니다. 명령줄에 다음을 입력 합니다.
    
    ```
    net stop w3svc
   ```

6. 모든 비즈니스용 Skype 서버 관리 셸 창을 닫습니다.
    
7. 업데이트를 설치 합니다.
    
8. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
9. 비즈니스용 Skype Server 서비스를 중지 하 고 GAC (전역 어셈블리 캐시)-d 어셈블리를 catch 합니다. 명령줄에 다음을 입력 합니다.
    
    ```
    Stop-CsWindowsService
    ```

10. World Wide Web 서비스를 다시 시작 합니다. 명령줄에 다음을 입력 합니다.
    
    ```
    net start w3svc
    ```

11. 다음 중 하나를 수행 하 여 SQL Server 데이터베이스에 대 한 변경 내용을 적용 합니다.
    
    - Enterprise Edition 백 엔드 서버이 고 데이터베이스 보관 또는 모니터링 등의 collocated 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Enterprise Edition 백 엔드 서버이 고이 서버에 collocated 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 스탠더드 버전 서버인 경우 명령줄에 다음을 입력 합니다.
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
