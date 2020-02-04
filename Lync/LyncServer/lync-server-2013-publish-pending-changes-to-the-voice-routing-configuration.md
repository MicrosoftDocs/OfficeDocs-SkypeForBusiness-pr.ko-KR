---
title: 'Lync Server 2013: 음성 라우팅 구성에 보류 중인 변경 내용 게시'
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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-07_

**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후에는이 절차를 수행 하 여 보류 중인 변경 내용을 검토 하거나 게시 하거나 취소 합니다.

<div>


> [!IMPORTANT]  
> 한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정 하도록 합니다.<BR>보류 중인 모든 변경 내용은 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 동시에 게시 해야 합니다. 보류 중인 변경 내용을 선택적으로 게시할 수 없습니다. 보류 중인 변경 내용을 게시 하기 전에 <STRONG>커밋되지 않은 변경 내용 검토</STRONG> 명령을 실행 하 고 게시 하지 않으려는 구성 변경 내용을 취소 합니다.<BR>보류 중인 변경 내용을 커밋하기 전에 <STRONG>음성 라우팅</STRONG> 그룹의 페이지에서 다른 위치로 이동 하면 보류 중인 변경 내용이 모두 손실 됩니다. 그러나 보류 중인 변경 내용을 포함 하 여 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트 된 구성을 가져오고 게시할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013에서 음성 경로 구성 파일 내보내기를</A>참조 하세요.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.

4.  **음성 라우팅** 그룹의 각 페이지에 대 한 설정을 원하는 대로 변경 합니다.

5.  보류 중인 변경 내용을 게시 하지 않고 검토 하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토** 를 선택 합니다.

6.  보류 중인 변경 내용을 취소 하려면 다음 중 하나를 수행 합니다.
    
      - **커밋** 메뉴에서 **커밋되지 않은 변경 내용 모두 취소** 를 선택 합니다.
    
      - 취소 하려는 보류 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동 하 고 보류 중인 변경 내용이 있는 항목을 선택한 다음 **커밋을**클릭 하 고 **선택한 변경 내용 취소**를 클릭 합니다.

7.  보류 중인 변경 내용을 모두 검토 하 고 게시 하지 않으려는 작업을 취소 한 후에는 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.

8.  모든 보류 중인 변경 내용 목록을 표시 하는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.
    
    Lync Server 제어판이 변경 내용을 커밋한 경우 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 표시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

