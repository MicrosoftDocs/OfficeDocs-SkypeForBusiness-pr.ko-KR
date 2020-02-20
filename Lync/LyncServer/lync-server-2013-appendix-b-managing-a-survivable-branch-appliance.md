---
title: 'Lync Server 2013: 부록 B: Sba (survivable Branch 어플라이언스 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>부록 B: Lync Server 2013에서 Sba (survivable 분기 기기 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

이 항목에서는 Sba (survivable 분기 어플라이언스를 관리 하는 절차에 대해 설명 합니다. 특히 Sba (survivable 분기 어플라이언스를 교체 하 고 이름을 바꾸는 방법 및 Sba (survivable 분기 기기가 연결 된 Lync Server 2013 프런트 엔드 풀을 변경 하는 방법을 설명 합니다.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>SBA(Survivable Branch Appliance)를 대체하려면

1.  Sba (survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다. 자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.

2.  는 도메인에서 Sba (survivable Branch 기기를 제거 합니다.

3.  다음 단계를 수행 하 여 Active Directory 도메인 서비스에서 Sba (survivable Branch 기기 computer 개체를 삭제 합니다.
    
      - Enterprise Admins 그룹의 구성원으로 구성원 서버에 로그온합니다.
    
      - **시작**, **관리 도구**를 차례로 클릭한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭합니다.
    
      - Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.

4.  Sba (survivable Branch 기기 컴퓨터 개체를 다시 추가 합니다. ( [Lync Server 2013에서 Active Directory에 Sba (survivable 분기 어플라이언스 추가](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)를 참조 하세요.)

5.  Active Directory 복제가 수행 될 때까지 기다립니다.

6.  Lync Server 관리 셸을 열고 **Enable-enable-cstopology**을 입력 합니다.

7.  새 Sba (survivable 분기 기기를 네트워크에 연결 하 고, [Sba (survivable Branch 기기 또는 server For Lync server 2013-중앙 사이트 작업](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 을 배포 하 고 [, sba (survivable Branch 기기 또는 서버를 lync server 2013-Branch site task를 사용 하 여 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)의 단계를 수행 합니다.

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>SBA(Survivable Branch Appliance)의 이름을 바꾸려면

1.  사용자를 중앙 사이트로 이동합니다. 자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.

2.  Sba (survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다. 자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.

3.  다음 단계를 수행 하 여 토폴로지에서 Sba (survivable Branch 기기를 제거 합니다.
    
      - **시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.
    
      - 콘솔 트리에서 **분기 사이트**를 확장 하 고 Sba (survivable Branch 기기를 클릭 한 다음 작업 창에서 **삭제** 를 클릭 합니다.

4.  도메인에서 Sba (survivable Branch 기기를 제거 합니다.

5.  다음 단계를 수행 하 여 Active Directory에서 Sba (survivable Branch 기기 computer 개체를 삭제 합니다.
    
      - Enterprise Admins 그룹의 구성원으로 도메인 컨트롤러에 로그온합니다.
    
      - **시작**, **관리 도구**, **Active Directory 사용자 및 컴퓨터**를 차례로 클릭합니다.
    
      - Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.

6.  Sba (survivable 분기 어플라이언스를 출고시 기본값으로 복원 합니다. 자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.

7.  [Sba (survivable Branch 기기 또는 Lync server 2013을 사용](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 하는 서버를 배포 하는 단계와 중앙 사이트 작업을 배포 하 고 [sba (survivable Branch 기기 또는 서버를 lync server 2013-Branch site task를 사용](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)하 여 배치 합니다.

8.  이름이 바뀐 Sba (survivable Branch 기기로 사용자를 이동 합니다. 자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>SBA(Survivable Branch Appliance)가 연결된 Lync Server 프런트 엔드 풀을 변경하려면

1.  Sba (survivable 분기 기기의 사용자를 중앙 사이트의 Lync Server 프런트 엔드 풀로 이동 합니다. 자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.

2.  Sba (survivable Branch 기기에서 모든 Lync Server 서비스를 중지 합니다. (Sba (survivable Branch 어플라이언스 공급 업체 설명서 참조).

3.  다음 단계를 수행 하 여 Sba (survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 업데이트 합니다.
    
      - **시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.
    
      - **분기 사이트**를 확장합니다.
    
      - 수정할 Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집** 을 클릭 합니다.
    
      - 복구에서 Sba (survivable 분기 기기가 연결 될 새 프런트 엔드 풀을 선택 하 고 **다음**을 클릭 합니다.
    
      - 콘솔 트리에서 새 Sba (survivable 분기 기기를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.

4.  Sba (survivable Branch 기기에서 모든 Lync Server 서비스를 다시 시작 합니다.

5.  Sba (survivable Branch 기기를 테스트 합니다. 자세한 내용은 [Home users in a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.

6.  중앙 사이트의 Lync Server 프런트 엔드 풀에서 Sba (survivable Branch 기기로 사용자를 이동 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

