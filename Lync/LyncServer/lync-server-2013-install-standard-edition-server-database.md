---
title: 'Lync Server 2013: Standard Edition Server 데이터베이스 설치'
description: 'Lync Server 2013: Standard Edition Server 데이터베이스를 설치 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574084"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Lync Server 2013에 대 한 Standard Edition server 데이터베이스 설치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Standard Edition 서버를 인프라의 유일한 서버로 설정 하는 것은 **배포 마법사** 에서 초기 서버를 설정 하는 것이 기본적으로 선택 되어 있으므로 사용자를 가정 하는 다른 서버 설치와는 다릅니다.

<div>

## <a name="to-install-a-standard-edition-server"></a>Standard Edition 서버를 설치하려면

1.  Standard Edition server를 설치할 서버에 로컬 관리자 또는 동등한 도메인으로 로그온 합니다.

2.  Active Directory 도메인 서비스를 준비 하지 않은 경우 먼저 해당 절차를 수행 합니다. 자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하십시오.

3.  Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.

4.  **단일 Standard Edition Server 준비** 페이지에서 **다음**을 클릭합니다.

5.  **명령 실행** 페이지에서 SQL Server 2012 Express는 중앙 관리 저장소로 설치 됩니다. 또한 필요한 방화벽 규칙이 만들어집니다. 데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다. SQL Server Express가 설치 되었기 때문입니다. 데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.

    
    </div>

6.  Lync Server 배포 마법사 페이지에서 이전에 관리 도구를 설치 하지 않은 경우 **토폴로지 작성기 설치** 를 클릭 합니다. 자세한 내용은 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.

7.  "Active Directory 준비", "첫 번째 Standard Edition 서버 준비" 및 "토폴로지 작성기 설치" 옆에 녹색 확인 표시가 있는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

