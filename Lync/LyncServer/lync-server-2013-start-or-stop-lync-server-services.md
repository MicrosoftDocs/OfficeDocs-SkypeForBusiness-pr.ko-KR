---
title: 'Lync Server 2013: Lync Server 서비스 시작 또는 중지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Lync Server 2013 서비스 시작 또는 중지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

Lync Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 Lync Server 2013 서비스를 시작 하거나 중지 하거나 특정 서비스를 시작 하거나 중지할 수 있습니다.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>컴퓨터에서 모든 Lync Server 서비스를 시작 하거나 중지 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다. 다음과 같은 명령을 실행 하 여 CsServerAdministrator 또는 CsAdministrator RBAC 역할을 할당 했는지 여부를 확인할 수 있습니다.
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.

4.  **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.

5.  **동작**을 클릭 합니다.

6.  **모든 서비스 시작** 또는 **모든 서비스 중지**를 클릭 합니다.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>특정 서비스를 시작 하거나 중지 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.

4.  **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.

5.  **속성**을 클릭 합니다.

6.  필요한 경우 서비스 목록을 정렬 하 고 시작 하거나 중지 하려는 서비스를 클릭 합니다.

7.  **동작**을 클릭 합니다.

8.  **서비스 시작** 또는 **서비스 중지**를 클릭 합니다.

9.  **닫기를**클릭 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 서비스에 대 한 세션 방지](lync-server-2013-prevent-sessions-for-services.md)  


[Lync Server 2013 토폴로지 관리](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

