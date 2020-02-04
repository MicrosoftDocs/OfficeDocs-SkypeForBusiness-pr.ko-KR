---
title: 모든 Exchange UM 연락처 개체가 레거시 풀에서 제거 되었는지 확인
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
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>모든 Exchange UM 연락처 개체가 레거시 풀에서 제거 되었는지 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-26_

**Ocsumutil** 도구나 **Get-csexumcontact** cmdlet 중 하나를 사용 하 여 Exchange UM Contact 개체가 레거시 Office Communications Server 2007 R2 풀에서 제거 되었는지 확인 합니다. **Ocsumutil** 은 다음 폴더에 있습니다.

% Program Files%\\Common Files\\Lync Server 2013\\에서\\ocsumutil을 지원 합니다.

**Ocsumutil** 은 다음과 같은 사용자 계정에서 실행 해야 합니다.

  - RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹의 구성원 (Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)

  - 지정 된 OU (조직 구성 단위) 컨테이너에서 연락처 개체를 만들 수 있는 도메인 권한

**Get-CsExumContact** cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [get-help (Get-csexumcontact)](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

