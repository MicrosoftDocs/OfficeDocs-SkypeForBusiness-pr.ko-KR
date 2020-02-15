---
title: 'Lync Server 2013: 업데이트 된 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Lync Server 2013에서 업데이트 된 토폴로지 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 영구 채팅 서버를 구성 하 고 사용 하기 전에 토폴로지를 중앙 관리 저장소에 게시 해야 합니다. 모든 서버가 토폴로지 및 기타 구성 변경 내용과 동기화되도록 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제됩니다.

<div>

## <a name="to-publish-an-updated-topology"></a>업데이트된 토폴로지를 게시하려면

토폴로지를 게시 하기 전에 영구 채팅 서버용 데이터베이스를 설치 합니다. **작업** 및 **데이터베이스 설치**를 선택 하 여 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 합니다.

1.  Lync Server 2013을 실행 하거나 Lync Server 관리 도구를 설치 하는 컴퓨터에서 다음을 수행 합니다. **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원 인 계정을 사용 하 여 로그온 하 고, 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (읽기, 쓰기 및 수정)을 포함 하는 (토폴로지 작성기가 필요한 임의 액세스 제어 목록 (dacl)를 구성할 수 있도록 함) 또는 이와 동등한 사용자 권한을 가진 계정으로 설정 합니다.

2.  토폴로지 작성기를 시작합니다. **기존 배포에서 토폴로지 다운로드** 또는 **로컬 파일에서 토폴로지 열기**(로컬로 저장한 경우)를 선택합니다.

3.  콘솔 트리에서 **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

4.  **토폴로지 게시** 페이지에서 **다음**을 클릭합니다.

5.  **게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 토폴로지를 게시 한 후에는 콘텐츠를 보관 하기 전에 영구 채팅 서버에 대 한 지원을 구성 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

