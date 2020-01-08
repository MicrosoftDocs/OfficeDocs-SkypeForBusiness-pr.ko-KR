---
title: 'Lync Server 2013: 메신저 대화에 사용자 지정 텍스트 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Lync Server 2013에서 메신저 대화에 사용자 지정 텍스트 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

IMWarning 매개 변수를 사용 하는 **새 csclientpolicy** 또는 **Set csclientpolicy** Lync Server Management Shell cmdlet을 사용 하 여 모든 Lync 2013 인스턴트 메시징 대화의 시작 부분에 부인 또는 경고를 추가 합니다.

다음 예제의 명령은 새 메신저 대화가 시작 될 때마다 대화 창 맨 위에 보안 알림을 추가 합니다.

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

**허용-CSClientPolicy** 를 사용 하 여이 새 정책을 사용자에 게 할당 합니다. 자세한 내용은 Lync Server 관리 셸 설명서에서 **새 csclientpolicy** 및 **부여-csclientpolicy** 를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

