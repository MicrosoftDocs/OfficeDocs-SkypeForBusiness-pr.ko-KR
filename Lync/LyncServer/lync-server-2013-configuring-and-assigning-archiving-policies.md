---
title: 'Lync Server 2013: 보관 정책 구성 및 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Lync Server 2013에서 보관 정책 구성 및 할당

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

Lync Server 2013에서는 정책을 사용 하 여 Lync Server 2013에 있는 사용자에 대 한 내부 통신 및 외부 통신을 사용 하도록 설정 하 고 보관 하지 않도록 합니다. 여기에는 다음과 같은 보관 정책이 포함 됩니다.

  - Lync Server 2013을 배포할 때 기본적으로 생성 되는 전역 정책입니다.

  - 특정 사이트 또는 사용자에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 사용자 수준 정책입니다.

보관 정책을 처음에 설정 했지만 배포 후에 정책을 변경, 추가, 삭제할 수 있습니다. Lync Server 2013 제어판에서 **보관 및 모니터링** 그룹의 **보관 정책** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 사용자 수준에서 정책을 관리할 수 있습니다.

<div>


> [!NOTE]  
> 보관 구현을 제어 하려면 IM 또는 회의 보관 여부, 중요 한 모드 사용, 제거 옵션 등의 보관 구성에 대 한 옵션을 지정 해야 합니다. 기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서는 옵션을 사용할 수 없습니다. 보관 정책에서 내부 또는 외부 통신에 대 한 보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다. 자세한 내용은 운영 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하세요.<BR>Lync Server 저장소를 Exchange 2013 저장소와 통합 하는 경우 Exchange 사용자 정책은 해당 사서함이 원본 위치 유지에 배치 되어 있는 Exchange 2013에 속한 사용자 에게만 2013 적용 됩니다.



</div>

정책 계층 구조를 포함 하 여 정책이 구현 되는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요. 배포 후 정책을 관리 하는 방법에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 보관할 글로벌 정책 구성](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Lync Server 2013에서 보관할 사이트 정책 설정](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Lync Server 2013에서 사용자에 대 한 보관 정책 설정](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

