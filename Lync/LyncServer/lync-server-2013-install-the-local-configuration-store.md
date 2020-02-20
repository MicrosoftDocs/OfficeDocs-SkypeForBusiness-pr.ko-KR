---
title: 'Lync Server 2013: 로컬 구성 저장소 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 478f45ff682b399f911b41d11a16c802181d14ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Lync Server 2013에서 로컬 구성 저장소 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-27_

이 단계를 수행 하기 전에 로컬 관리자와 RTCUniversalReadOnlyAdmin 그룹의 구성원 모두에 해당 하는 도메인 사용자 계정을 사용 하 여 서버에 로그온 했는지 확인 합니다.

Lync Server 배포 마법사를 사용 하 여 모든 작업을 수행 하려면 서버에 로컬 구성 저장소가 있어야 합니다. 로컬 구성 저장소는 SQL Server Express 로컬 설치 후 만들어지는 중앙 관리 저장소의 읽기 전용 복사본입니다. 중앙 관리 저장소 자체도 Standard Edition server 또는 SQL Server Express 기반 데이터베이스에 설치 된 기존 SQL Server 데이터베이스에 추가 됩니다.

<div>


> [!IMPORTANT]  
> 이전에이 서버에서 Lync Server 2013 설치 프로그램을 실행 하지 않은 경우에는 Lync Server 2013를 설치할 드라이브와 경로를 입력 하 라는 메시지가 표시 됩니다. 이렇게 하면 조직에서 필요로 하는 경우 또는 공간에 문제가 있는 경우 시스템 드라이브 이외의 드라이브에 설치할 수 있습니다. 설치 대화 상자에서 Lync Server 파일의 설치 위치 경로를 사용 가능한 새 드라이브로 변경 하면 됩니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 나머지 Lync Server 2013 파일에도 배포 됩니다.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>로컬 구성 저장소를 설치하려면

1.  설치 \\미디어에서 설치\\프로그램 amd64\\setup.exe를 찾은 다음 **확인**을 클릭 합니다.

2.  Microsoft Visual c # 2012 재배포 가능 패키지를 설치할지 묻는 메시지가 표시 되 면 **예**를 클릭 합니다.

3.  **Lync Server 2013 설치 위치** 페이지에서 **확인**을 클릭 합니다.

4.  **최종 사용자 사용권 계약** 페이지에서 사용 조건을 검토 하 **고 동의 함을 선택한 다음** **확인** 을 클릭 하 여 계속 진행 합니다.

5.  배포 마법사 페이지에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.

6.  **Lync Server 2013** 페이지에서 **1 단계 옆: 로컬 구성 저장소 설치**옆에 있는 **실행**을 클릭 합니다.

7.  **로컬 구성 저장소 설치** 페이지에서 **중앙 관리 저장소에서 직접 검색** 옵션이 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.

8.  로컬 서버 구성 설치가 완료 되 면 **마침을**클릭 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

