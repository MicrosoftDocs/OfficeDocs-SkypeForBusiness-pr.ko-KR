---
title: 'Lync Server 2013: 부록 B: SBA(Survivable Branch Appliance) 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>부록 B: Lync Server 2013에서 SBA(Survivable Branch Appliance) 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

이 항목에서는 Survivable Branch 기기를 관리 하는 절차에 대해 설명 합니다. 특히 Survivable Branch 기기를 바꾸거나 이름을 바꾸는 방법 및 Survivable 분기 기기가 연결 된 Lync Server 2013 프런트 엔드 풀을 변경 하는 방법을 설명 합니다.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Survivable Branch 기기를 바꾸려면

1.  Survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다. (Survivable Branch 기기 공급 업체 문서를 참조 하세요.)

2.  권장 도메인에서 Survivable Branch 기기를 제거 합니다.

3.  Active Directory 도메인 서비스에서 Survivable Branch 기기 컴퓨터 개체를 삭제 하려면 다음 단계를 따르세요.
    
      - 엔터프라이즈 관리자 그룹의 구성원으로 구성원 서버에 로그온 합니다.
    
      - **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.
    
      - Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.

4.  Survivable Branch 기기 컴퓨터 개체를 다시 추가 합니다. ( [Lync Server 2013에서 Active Directory에 Survivable Branch 기기 추가를](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)참조 하세요.)

5.  Active Directory 복제가 수행 될 때까지 기다립니다.

6.  Lync Server Management Shell을 열고 **Enable-CSTopology**를 입력 합니다.

7.  새 Survivable Branch 기기를 네트워크에 연결 하 고 [Lync server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 의 단계를 따르고, [lync server 2013-지사 사이트 작업으로 Survivable Branch 기기 또는 서버를 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)합니다.

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Survivable Branch 기기 이름 바꾸기

1.  사용자를 중앙 사이트로 이동 합니다. 자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.

2.  Survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다. (Survivable Branch 기기 공급 업체 문서를 참조 하세요.)

3.  다음 단계에 따라 토폴로지에서 Survivable Branch 기기를 제거 합니다.
    
      - **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - 콘솔 트리에서 **지점 사이트**를 확장 하 고 Survivable Branch 기기를 클릭 한 다음 작업 창에서 **삭제** 를 클릭 합니다.

4.  도메인에서 Survivable Branch 기기를 제거 합니다.

5.  Active Directory에서 Survivable Branch 기기 컴퓨터 개체를 삭제 하려면 다음 단계를 따르세요.
    
      - 엔터프라이즈 관리자 그룹의 구성원으로 도메인 컨트롤러에 로그온 합니다.
    
      - **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.
    
      - Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.

6.  Survivable Branch 기기를 출하시 기본값으로 복원 합니다. (Survivable Branch 기기 공급 업체 문서를 참조 하세요.)

7.  [Lync server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 의 단계를 따르고 [lync server 2013-지사 사이트 작업을 사용 하 여 Survivable Branch 기기 또는 서버를 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)합니다.

8.  이름을 바꾼 Survivable Branch 기기로 사용자를 이동 합니다. 자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 변경 하려면

1.  Survivable Branch 기기에서 중앙 사이트의 Lync Server 프런트 엔드 풀로 사용자를 이동 합니다. 자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.

2.  Survivable Branch 기기에서 모든 Lync Server 서비스를 중지 합니다. (Survivable Branch 기기 공급 업체 문서를 참조 하세요.)

3.  다음 단계에 따라 Survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 업데이트 합니다.
    
      - **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - **지점 사이트**를 확장 합니다.
    
      - 수정할 Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집** 을 클릭 합니다.
    
      - 회복성에서 Survivable Branch 기기를 연결할 새 프런트 엔드 풀을 선택 하 고 **다음**을 클릭 합니다.
    
      - 콘솔 트리에서 새 Survivable Branch 기기를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.

4.  Survivable Branch 기기에서 모든 Lync Server 서비스를 다시 시작 합니다.

5.  Survivable Branch 기기를 테스트 합니다. 자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버의 가정용 사용자](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)를 참조 하세요.

6.  중앙 사이트의 Lync Server 프런트 엔드 풀에서 Survivable Branch 기기로 사용자를 이동 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

