---
title: 'Lync Server 2013: Lync 오류 메시지에 사용자 지정 링크 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Lync Server 2013에서 Lync 오류 메시지에 사용자 지정 링크 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

고유한 문제 해결 또는 지원 센터 정보에 대 한 링크를 추가 하 여 Lync 2013 오류 메시지를 사용자 지정 합니다. 이렇게 하려면 CustomLinkInErrorMessages 매개 변수를 사용 하 여 **새 csclientpolicy** 또는 **Set csclientpolicy** Lync 서버 관리 셸 cmdlet을 사용 합니다. 사용자 지정 링크의 텍스트는 "관리자의 지원 항목에 대해서는 여기를 클릭 하세요" 라는 의미 이며, 사용자 지정할 수 없습니다.

예를 들어 다음 명령을 실행 하면 모든 Lync 2013 오류 메시지의 각주 영역에 사용자 지정 링크가 나타나고 링크 대상을 다음으로 설정 합니다.http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

**허용-CSClientPolicy** 를 사용 하 여이 새 정책을 사용자에 게 할당 합니다. 자세한 내용은 Lync Server 관리 셸 설명서에서 **새 csclientpolicy** 및 **부여-csclientpolicy** 를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

