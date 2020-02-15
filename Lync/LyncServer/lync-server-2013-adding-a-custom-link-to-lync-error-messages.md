---
title: 'Lync Server 2013: Lync 오류 메시지에 사용자 지정 링크 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c9f15b72f105edf291007569999c549b8b2c841
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Lync Server 2013의 Lync 오류 메시지에 사용자 지정 링크 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

자체 문제 해결 또는 지원 센터 정보에 대 한 링크를 추가 하 여 Lync 2013 오류 메시지를 사용자 지정 합니다. 이 작업을 수행 하려면 CustomLinkInErrorMessages 매개 변수를 사용 하 여 **신규 csclientpolicy** 또는 **Set-csclientpolicy** Lync Server Management Shell cmdlet을 사용 합니다. 사용자 지정 링크의 텍스트는 "관리자의 지원 항목은 여기를 클릭 하세요." 이며 사용자 지정할 수 없습니다.

예를 들어 다음 명령은 모든 Lync 2013 오류 메시지의 각주 영역에 사용자 지정 링크가 표시 되도록 하 고 링크 대상을 다음으로 설정 합니다.http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

**Grant-CSClientPolicy**를 사용하여 새로운 이 정책을 사용자에게 지정합니다. 자세한 내용은 Lync Server 관리 셸 설명서에서 **New-csclientpolicy** 및 **Grant-csclientpolicy** 를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

