---
title: 'Lync Server 2013: 음성 경로 구성 파일 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1549cabf8163275c202075dcfc7ef081b38d20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로 구성 파일 내보내기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

음성 라우팅 구성을 게시 하지 않고 저장 하려면 다음 단계를 수행 하 여 Lync Server 제어판 구성 내보내기 및 가져오기 명령을 사용 하 여 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다. 음성 라우팅 구성 파일 (vcfg)을 가져올 때 서버에서 음성 라우팅 구성이 변경 되 면 Lync Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에는 음성 라우팅의 커밋되지 않은 변경 내용이 있음을 나타내는 메시지가 표시 됩니다. 커밋되지 않은 이러한 변경 내용으로 인해 두 구성 간 차이가 발생하며, 이러한 차이를 조정해야 합니다.

그룹 내의 모든 페이지에 대 한 설정을 커밋되지 않은 방식으로 변경 하면 해당 변경 내용이 내보낸 음성 구성 파일 (vcfg)에 저장 됩니다. 이를 통해 변경 내용을 게시 하기 전에 여러 세션 중에 음성 라우팅 구성을 변경할 수 있습니다.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>음성 라우팅 구성을 내보내려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.

4.  **동작** 메뉴에서 **구성 내보내기**를 클릭합니다.

5.  위치 및 파일 이름을 지정하고 **저장**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 경로 구성 파일 가져오기](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

