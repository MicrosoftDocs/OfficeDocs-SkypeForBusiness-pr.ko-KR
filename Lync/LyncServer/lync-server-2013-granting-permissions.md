---
title: 'Lync Server 2013: 사용 권한 부여'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Lync Server 2013에서 사용 권한 부여

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

설치의 경우 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU의 RTCUniversalServerAdmins 그룹 구성원이 지정 된 도메인에 Lync Server 2013을 설치할 수 있습니다. OU에 대 한 사용 권한을 부여 하면 다음 사용 권한이 부여 됩니다.

  - 자세한

  - 작성

  - ReadSPN

  - WriteSPN

관리의 경우 포리스트 준비를 통해 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원 일 필요 없이 Ou에 액세스할 수 있도록 지정 된 Ou에 대 한 사용 권한을 추가할 수 있습니다. 지정 된 OU에 추가 되는 권한은 **CsAdDomain** cmdlet이 컴퓨터 및 사용자 OU 컨테이너에 추가 하는 권한과 동일 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 설치 권한 부여](lync-server-2013-granting-setup-permissions.md)

  - [Lync Server 2013에서 조직 구성 단위 권한 부여](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

