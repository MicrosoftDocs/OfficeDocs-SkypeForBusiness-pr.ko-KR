---
title: 'Lync Server 2013: Standard Edition 서버 데이터베이스 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Lync Server 2013에 대한 Standard Edition 서버 데이터베이스 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

표준 버전 서버를 인프라의 유일한 서버로 설정 하는 것은 **배포 마법사** 에서 초기 서버 설정에 대 한 선택이 있기 때문에 사용자가 다른 서버 설치와 다릅니다.

<div>

## <a name="to-install-a-standard-edition-server"></a>스탠더드 버전 서버를 설치 하려면

1.  Standard Edition server를 로컬 관리자 또는 동등한 도메인으로 설치할 서버에 로그온 합니다.

2.  Active Directory 도메인 서비스를 준비 하지 않은 경우 먼저 해당 절차를 수행 합니다. 자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하세요.

3.  Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.

4.  **단일 Standard Edition Server 준비** 페이지에서 **다음**을 클릭 합니다.

5.  **명령 실행** 페이지에서 SQL Server 2012 Express가 중앙 관리 저장소로 설치 됩니다. 필요한 방화벽 규칙이 생성 됩니다. 데이터베이스 설치 및 필수 소프트웨어 소프트웨어가 완료 되 면 **마침을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 초기 설치에는 명령 출력 요약 화면에 표시 되는 업데이트 없이 시간이 걸릴 수 있습니다. 이는 SQL Server Express의 설치 때문입니다. 데이터베이스 설치를 모니터링 해야 하는 경우 작업 관리자를 사용 하 여 설정을 모니터링 합니다.

    
    </div>

6.  Lync Server 배포 마법사 페이지에서 이전에 관리 도구를 설치 하지 않은 경우 **토폴로지 작성기 설치** 를 클릭 합니다. 자세한 내용은 [Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하세요.

7.  "Active Directory 준비", "첫 번째 Standard Edition server 준비" 및 "토폴로지 작성기 설치" 옆에 녹색 확인 표시가 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

