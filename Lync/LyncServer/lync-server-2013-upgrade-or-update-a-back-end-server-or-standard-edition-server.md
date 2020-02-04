---
title: 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트
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
ms.openlocfilehash: 0526cc7ba6a6abefd066bf07d845ffed3a4107ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.

업그레이드 하는 동안 백 엔드 서버가 최소 30 분 동안 중단 되 면 사용자가 복원 모드로 전환할 수 있습니다. 업그레이드가 완료 되 고 백 엔드 서버가 풀의 프런트 엔드 서버와 다시 연결 되 면 사용자가 전체 기능으로 반환 됩니다. 업그레이드 시간이 30 분 미만이 되 면 사용자에 게 영향을 주지 않습니다.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>백 엔드 서버 또는 Standard Edition 서버를 업데이트 하려면

1.  CsAdministrator 역할의 구성원으로 업그레이드 하는 서버에 로그온 합니다.

2.  업데이트를 다운로드 하 고 로컬 하드 디스크에 압축을 풉니다.

3.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

4.  Lync Server 서비스를 중지 합니다. 명령줄에 다음을 입력 합니다.
    
        Stop-CsWindowsService

5.  World Wide Web 서비스를 중지 합니다. 명령줄에 다음을 입력 합니다.
    
        net stop w3svc

6.  모든 Lync Server Management 셸 창을 닫습니다.

7.  업데이트를 설치합니다.

8.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

9.  Lync Server 서비스를 다시 중지 하 여 GAC (전역 어셈블리 캐시) – d 어셈블리를 catch 합니다. 명령줄에 다음을 입력 합니다.
    
        Stop-CsWindowsService

10. World Wide Web 서비스를 다시 시작 합니다. 명령줄에 다음을 입력 합니다.
    
        net start w3svc

11. 다음 중 하나를 수행 하 여 LyncServerUpdateInstaller에의 한 변경 내용을 SQL Server 데이터베이스에 적용 합니다.
    
      - Enterprise Edition 백 엔드 서버이 고 데이터베이스 보관 또는 모니터링 등의 collocated 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Enterprise Edition 백 엔드 서버이 고이 서버에 collocated 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 스탠더드 버전 서버인 경우 명령줄에 다음을 입력 합니다.
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

