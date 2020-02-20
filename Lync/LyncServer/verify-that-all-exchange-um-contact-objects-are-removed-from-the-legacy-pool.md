---
title: 레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e18e63dbbc5b64ca61baf9c5635717fc7f3fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-26_

**Ocsumutil** 도구 또는 **get-help** cmdlet을 사용 하 여 Exchange UM 대화 상대 개체가 레거시 Office Communications Server 2007 R2 풀에서 제거 되었는지 확인 합니다. **OCSUmUtil**은 다음 폴더에 있습니다.

% Program Files%\\Common Files\\Lync Server 2013\\지원\\ocsumutil

**OCSUmUtil**은 다음을 포함하는 사용자 계정으로부터 실행해야 합니다.

  - RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹의 구성원(Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)

  - 지정된 OU(조직 구성 단위) 컨테이너에 대화 상대 개체를 만드는 도메인 권한

**Get-help** cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [get-help-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

