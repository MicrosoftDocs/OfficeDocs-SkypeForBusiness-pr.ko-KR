---
title: 미러된 Enterprise Edition 백 엔드 서버-미러 복원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511585"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-19_

미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 미러만 실패 하는 경우에는이 섹션의 절차를 따르세요. 주 데이터베이스와 미러 서버에 모두 오류가 발생 하면 [Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요. 기본에만 오류가 발생 하는 경우 [Lync server 2013-primary에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)참조 하세요. 중앙 관리 저장소를 호스트 하는 데이터베이스가 실패 하면 [Lync server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요. 백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하면 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.

복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Enterprise Edition 백 엔드 서버 미러 데이터베이스를 복원 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  미러링을 제거 합니다. 먼저 다음 cmdlet을 입력 합니다.
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    예제:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.

4.  오류가 발생 한 컴퓨터와 동일한 FQDN (정규화 된 도메인 이름)을 가진 깨끗 한 서버나 새 서버를 만들고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll DB1.contoso.com 합니다. 이 서버는 새 미러에서 작동 합니다.

5.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.

6.  SQL Server 2012 또는 SQL Server 2008 r 2를 설치 하 고 인스턴스 이름을 오류 이전과 동일 하 게 유지 합니다.

7.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

8.  토폴로지 작성기를 사용 하 여 미러 데이터베이스를 설치 합니다. 다음 작업을 수행하십시오.
    
      - 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.
    
      - **데이터베이스 설치** 마법사를 따릅니다. **데이터베이스 만들기** 페이지에서 다시 만들 데이터베이스를 선택 합니다.
    
      - 마법사의 지시에 따라 **미러 데이터베이스 만들기** 메시지가 표시 될 때까지 합니다. 설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.
        
        <div>
        

        > [!TIP]
        > 토폴로지 작성기를 실행 하는 대신 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용 하 여 미러링을 구성할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

