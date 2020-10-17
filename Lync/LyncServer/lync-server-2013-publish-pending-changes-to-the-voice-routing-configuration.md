---
title: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용 게시'
description: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용을 게시 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565454"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-07_

**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후 다음 절차를 수행하여 대기 중인 변경 내용을 검토, 게시 또는 취소할 수 있습니다.

<div>


> [!IMPORTANT]  
> 한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정하도록 해야 합니다.<BR>대기 중인 모든 변경 내용은 <STRONG>모두 커밋</STRONG> 명령을 실행하여 동시에 게시되어야 합니다. 대기 중인 변경 내용을 선택해서 게시할 수 없습니다. 대기 중인 변경 내용을 게시하기 전에 <STRONG>커밋되지 않은 변경 내용 검토</STRONG> 명령을 실행하고 게시하지 않을 구성 변경 내용을 모두 취소합니다.<BR>대기 중인 변경 내용을 커밋하기 전에 <STRONG>음성 라우팅</STRONG> 그룹의 페이지에서 이동할 경우 대기 중인 모든 변경 내용이 손실됩니다. 단, 대기 중인 모든 변경 사항을 비롯한 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트된 구성을 가져오고 게시할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013에서 음성 경로 구성 파일 내보내기를</A>참조 하십시오.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.

4.  **음성 라우팅** 그룹의 각 페이지에서 구성 설정을 원하는 대로 변경합니다.

5.  대기 중인 변경 내용을 게시하지 않고 검토하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토**를 선택합니다.

6.  대기 중인 변경 내용을 취소하려면 다음 중 하나를 수행합니다.
    
      - **커밋** 메뉴에서 **커밋되지 않은 모든 변경 내용 취소**를 선택합니다.
    
      - 취소할 대기 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동하고 대기 중인 변경 내용이 포함된 항목을 선택한 후 **커밋**, **선택한 변경 내용 취소**를 차례로 클릭합니다.

7.  대기 중인 변경 내용을 모두 검토하고 게시하지 않을 변경 내용을 취소했으면 **커밋**, **모두 커밋**을 차례로 클릭합니다.

8.  대기 중인 모든 변경 내용에 대한 목록이 표시되는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭합니다.
    
    Lync Server 제어판이 변경 내용을 커밋한 경우 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 표시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

