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
ms.openlocfilehash: eaad239f320f498378498f9b3e373592d487c0c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 미디어 바이패스 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-15_

미디어 바이패스 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다. 미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다. 미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션에서 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하십시오. Lync Server 제어판에서 미디어 바이패스를 사용 하지 않도록 설정할 수 있습니다. Medial bypass 사용 및 구성에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 미디어 바이패스 사용](lync-server-2013-enabling-network-media-bypass.md) 을 참조 하십시오.

<div>

## <a name="to-disable-media-bypass"></a>미디어 바이패스를 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **전역**을 클릭합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.

5.  **편집** 메뉴에서 **자세히 보기**를 클릭합니다.

6.  **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란의 선택을 취소합니다.

7.  **커밋**을 클릭하여 변경 내용을 저장합니다.

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

