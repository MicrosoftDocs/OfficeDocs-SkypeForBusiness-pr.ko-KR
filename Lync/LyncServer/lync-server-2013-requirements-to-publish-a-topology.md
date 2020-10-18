---
title: 'Lync Server 2013: 토폴로지를 게시 하기 위한 요구 사항'
description: 'Lync Server 2013: 토폴로지를 게시 하기 위한 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577864"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 게시 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

이 항목에서는 토폴로지 작성기 또는 Lync Server 2013 관리 셸 명령줄 인터페이스를 사용 하 여 토폴로지를 게시 하는 것과 관련 된 인프라 및 소프트웨어 요구 사항에 대해 설명 합니다. 이러한 요구 사항은 모든 Lync Server 2013 관리 도구에 적용 되는 일반적인 운영 체제, 소프트웨어 및 사용 권한 요구 사항 외에도 해당 됩니다. 토폴로지를 게시 하기 전에 모든 관리 도구 요구 사항을 충족 하는지 확인 합니다.

  - Active Directory 도메인 서비스 준비 단계가 이미 완료 되도록 만들려는 Lync Server 2013 배포의 동일한 도메인 또는 포리스트에 가입 된 컴퓨터에서 토폴로지 작성기를 실행 해야 하며, 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 성공적으로 게시할 수 있습니다.

  - 토폴로지에 정의된 컴퓨터는 에지 서버를 제외하고 도메인 및 AD DS에 참여해야 합니다. 하지만 토폴로지를 게시할 때 컴퓨터가 온라인 상태일 필요는 없습니다.

  - 풀에 대한 파일 공유를 만들고 원격 사용자에게 제공해야 합니다.

  - Enterprise Edition 프런트 엔드 풀을 게시 하려면 SQL Server 기반 백 엔드 서버가 서버를 배포할 도메인에 가입 하 고, 온라인 상태 이며, 원격 사용자가 사용할 수 있도록 적절 한 방화벽 규칙을 사용 하 여 구성 해야 합니다. 방화벽 예외 지정에 대 한 자세한 내용은 [Lync server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)를 참조 하십시오. SQL Server 구성에 대 한 자세한 내용은 [CONFIGURE Sql Server For Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)을 참조 하십시오.
    
    <div>
    

    > [!NOTE]  
    > Standard Edition 서버에는 게시 된 구성을 허용 하는 배치 된 데이터베이스가 있습니다. 먼저 Lync Server 배포 마법사에서 <STRONG>최초 Standard Edition server 설치 준비</STRONG> 작업을 실행 해야 합니다.

    
    </div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013에서 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013의 관리 도구 소프트웨어 요구 사항](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

