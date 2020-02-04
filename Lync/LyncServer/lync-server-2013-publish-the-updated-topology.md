---
title: 'Lync Server 2013: 업데이트된 토폴로지 게시'
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
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Lync Server 2013에서 업데이트된 토폴로지 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 영구 채팅 서버를 구성 하 고 사용할 수 있도록 먼저 토폴로지를 중앙 관리 저장소에 게시 해야 합니다. 모든 서버가 토폴로지와 다른 구성 변경 사항과 동기화 되도록 유지 하기 위해 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제 됩니다.

<div>

## <a name="to-publish-an-updated-topology"></a>업데이트 된 토폴로지를 게시 하려면

토폴로지를 게시 하기 전에 영구 채팅 서버용 데이터베이스를 설치 합니다. **작업** 및 **데이터베이스 설치**를 선택 하 여 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 합니다.

1.  Lync Server 2013을 실행 하거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 **도메인 관리자** 그룹과 **RTCUniversalServerAdmins** 그룹 모두의 구성원 인 계정을 사용 하 여 로그온 하 고, 영구적 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있으며,이는 토폴로지 작성기가 필수 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 하는 계정 이거나 해당 사용자 권한이 있는 계정을 사용 하는 것입니다.

2.  토폴로지 작성기를 시작 합니다. **기존 배포에서 토폴로지 다운로드**를 선택 하거나 **로컬 파일을 로컬로 저장 한 경우에는 토폴로지를 엽니다** .

3.  콘솔 트리에서 **Lync Server 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

4.  **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.

5.  **게시 마법사 완료** 페이지에서 토폴로지가 성공적으로 게시 되었는지 확인 한 다음 **마침을**클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 토폴로지를 게시 한 후에는 영구 채팅 서버에 대 한 지원을 구성 해야 콘텐츠를 보관할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

