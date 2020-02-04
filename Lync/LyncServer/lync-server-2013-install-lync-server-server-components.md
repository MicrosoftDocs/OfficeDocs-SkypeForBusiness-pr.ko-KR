---
title: 'Lync Server 2013: Lync Server 서버 구성 요소 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Lync Server 2013의 서버 구성 요소 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-05_

이 단계를 수행 하기 전에 로컬 관리자이 고 Active Directory에서 RTCUniversalReadOnlyAdmins 그룹의 구성원 인 도메인 사용자 계정으로 서버에 로그온 했는지 확인 하세요.

Lync Server 배포 마법사는 각 Lync 서버 역할에 필요한 구성 요소를 설치 하 고 서버를 활성화 하는 데 사용 됩니다. 이 문서에서는 Lync 인프라에서 Standard Edition server 또는 프런트 엔드 서버를 배포 하는 단계를 안내 합니다.

<div>

## <a name="to-install-lync-server-components"></a>Lync Server 구성 요소를 설치 하려면

1.  Lync Server 배포 마법사가 실행 되 고 있지 않으면 Lync를 설치 하려는 서버에서 시작 합니다.

2.  **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.

3.  배포 마법사에서 **1 단계: 로컬 구성 저장소 설치** 에 녹색 확인 표시가 있는지 확인 합니다 .이는이 서버에 스토어의 로컬 복사본이 성공적으로 설치 되어 있음을 의미 합니다. 선택 되지 않은 경우 서버에 로컬 구성 저장소를 설치 해야 합니다. [Lync Server 2013에서 로컬 구성 저장소를 설치](lync-server-2013-install-the-local-configuration-store.md) 하는 단계를 수행한 다음 다시 방문 하세요.

4.  서버에 Lync Server 2013 구성 요소를 설치할 준비가 되 면 **2 단계: Lync Server 구성 요소 설정 또는 제거**옆에 있는 **실행** 을 클릭 합니다.

5.  **Lync Server 구성 요소 설정** 페이지에서 **다음** 을 클릭 하 여 게시 된 토폴로지에 정의 되어 있는 구성 요소를 설정 합니다.

6.  명령 **실행** 페이지에는 설정 된 대로 명령 및 설치 정보에 대 한 요약이 표시 됩니다. 완료 되 면 목록을 사용 하 여 보려는 로그를 선택한 다음 **로그 보기**를 클릭 하면 됩니다.

7.  Lync Server 2013 구성 요소 설치가 완료 되 고 필요한 경우 로그를 검토 한 경우 **마침을** 클릭 하 여 설치에서이 단계를 완료 합니다.
    
    <div>
    

    > [!NOTE]  
    > 서버를 다시 시작 하 라는 메시지가 표시 되는 경우 (이 경우에는 Windows 데스크톱 환경을 설치 해야 할 수 있음)이 작업을 명확 하 게 합니다. 컴퓨터를 백업 하 고 실행 하는 경우 위에 나열 된 3 단계부터 (기본적으로 배포 마법사에서 2 단계를 한 번 더 실행) 이러한 단계를 다시 수행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

