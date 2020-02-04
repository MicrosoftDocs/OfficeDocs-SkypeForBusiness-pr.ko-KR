---
title: 'Lync Server 2013: 보관 데이터베이스를 추가 하기 위해 업데이트 된 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0d12b1b4195e57fc289d11eb54f24903d05ea26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>업데이트 된 토폴로지를 게시 하 여 Lync Server 2013에서 보관 데이터베이스 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 보관을 구성 하 고 사용할 수 있도록 먼저 토폴로지를 중앙 관리 저장소에 게시 해야 합니다. 모든 서버가 토폴로지와 다른 구성 변경 사항과 동기화 되도록 유지 하기 위해 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제 됩니다.

<div>

## <a name="to-publish-your-updated-topology"></a>업데이트 된 토폴로지를 게시 하려면

1.  Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 서버를 추가 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며, Lync server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있는 경우 (즉, 토폴로지 작성기가 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 합니다. 또는 해당 권한이 있는 계정

    
    </div>

2.  토폴로지 작성기를 사용 하 여 이전 섹션에서 만든 토폴로지를 엽니다.

3.  콘솔 트리에서 **Lync Server 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

4.  **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.

5.  **데이터베이스 만들기** 페이지에서 데이터베이스가 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 데이터베이스를 만들 수 있는 적절 한 권한이 없는 경우 데이터베이스 선택을 취소 하 고 적절 한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다. 필요한 관리자 권한 및 사용 권한에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013에서 SQL Server에 대 한 배포 권한을</A> 참조 하세요.<BR>토폴로지 작성기를 사용 하 여 전용 SQL Server 서버의 데이터베이스만 설치할 수 있습니다. 다른 서버 구성 요소와 collocated는 SQL Server 서버의 데이터베이스는 해당 컴퓨터에서 로컬 설정을 실행 하 여 설치 해야 합니다.

    
    </div>

6.  **게시 마법사 완료** 페이지에서 토폴로지가 성공적으로 게시 되었는지 확인 한 다음 **마침을**클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 토폴로지를 게시 한 후에는 콘텐츠를 보관 하기 전에 보관을 위한 옵션과 정책을 구성 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원 구성을</A> 참조 하세요.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

