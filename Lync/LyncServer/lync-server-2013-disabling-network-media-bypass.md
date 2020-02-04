---
title: 'Lync Server 2013: 네트워크 미디어 바이패스 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0457281a743d317e17a5fd0728e1a747b4d88271
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 미디어 바이패스를 사용 하지 않도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

미디어 무시 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다. 미디어 바이패스는 호출을 사용 하 여 중재 서버를 무시할 수 있습니다. 미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션의 [Lync Server 2013에서 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하세요. Lync Server 제어판에서 미디어 바이패스를 사용 하지 않도록 설정할 수 있습니다. Medial bypass 사용 및 구성에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 미디어 바이패스 사용](lync-server-2013-enabling-network-media-bypass.md) 을 참조 하세요.

<div>

## <a name="to-disable-media-bypass"></a>미디어 바이패스를 해제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **전역**을 클릭 합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭 합니다. 항상 하나의 구성만 있으며 항상 전역 이라는 이름으로 지정 됩니다.

5.  **편집** 메뉴에서 **세부 정보 보기**를 클릭 합니다.

6.  **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란의 선택을 취소 합니다.

7.  **커밋을** 클릭 하 여 변경 내용을 저장 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 미디어 바이패스 사용](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

