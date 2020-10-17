---
title: 백 엔드 서버 또는 Standard Edition Server 업그레이드 또는 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3afeee91457b2d10f506be81a146643a4598c9f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506645"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.

업그레이드하는 동안 백 엔드 서버가 30분 이상 중단되는 경우에는 사용자가 복구 모드로 전환될 수 있습니다. 업그레이드가 완료되고 백 엔드 서버가 다시 풀의 프런트 엔드 서버에 연결되면 사용자가 전체 기능 모드로 복구됩니다. 업그레이드에 30분 미만이 걸리는 경우에는 사용자에게 영향이 없습니다.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>백 엔드 서버 또는 Standard Edition server를 업데이트 하려면

1.  CsAdministrator 역할의 구성원으로 업그레이드할 서버에 로그온합니다.

2.  업데이트를 다운로드한 후 로컬 하드 디스크로 압축을 풉니다.

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  명령줄에 다음을 입력하여 Lync Server 서비스를 중지합니다.
    
        Stop-CsWindowsService

5.  명령줄에 다음을 입력하여 World Wide Web 서비스를 중지합니다.
    
        net stop w3svc

6.  모든 Communications Server 관리 셸 창을 닫습니다.

7.  업데이트를 설치합니다.

8.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

9.  Lync Server 서비스를 다시 중지하여 GAC(전역 어셈블리 캐시) -d 어셈블리를 catch합니다. 명령줄에 다음을 입력합니다.
    
        Stop-CsWindowsService

10. 명령줄에 다음을 입력하여 World Wide Web 서비스를 다시 시작합니다.
    
        net start w3svc

11. 다음 중 하나를 수행하여 LyncServerUpdateInstaller.exe에서 SQL Server 데이터베이스에 대해 수행한 변경 내용을 적용합니다.
    
      - Enterprise Edition 백 엔드 서버인 경우 보관 또는 모니터링 데이터베이스와 같이이 서버에 배치 된 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Enterprise Edition 백 엔드 서버이 고이 서버에 배치 된 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Standard Edition server 인 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

