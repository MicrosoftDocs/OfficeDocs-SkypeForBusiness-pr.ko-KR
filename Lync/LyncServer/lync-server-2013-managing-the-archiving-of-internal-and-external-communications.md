---
title: 내부 및 외부 통신의 보관 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525035"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Lync Server 2013에서 내부 및 외부 통신의 보관 관리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Lync Server 2013에서는 보관 정책을 사용 하 여 Microsoft Exchange 통합을 사용 하지 않는 경우 또는 내부 통신 및 외부 통신에 대해 보관을 사용 하거나 사용 하지 않도록 설정 하 고, Exchange 2013에 있지 않은 사용자가 사서함을 In-Place 보류 상태로 전환 되도록 해야 합니다. 여기에는 다음과 같은 보관 정책이 포함됩니다.

  - Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 정책입니다.

  - 특정 사이트 또는 사용자에 대해 보관이 구현되는 방식을 지정하도록 만들어서 사용하는 선택적인 사이트 수준 및 사용자 수준 정책

보관을 배포할 때 처음으로 보관 정책을 설정하게 되며, 배포 후에 정책을 변경, 추가 및 삭제할 수 있습니다. Lync Server 2013 제어판에서는 **보관 및 모니터링** 그룹의 **보관 정책** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 사용자 수준에서 정책을 관리할 수 있습니다. Lync Server 저장소와 Exchange 2013 저장소를 통합 하는 경우 Exchange 사용자 정책이 Lync Server 2013 보관 정책 보다 우선적으로 적용 됩니다.

정책 계층 구조를 포함 하 여 정책이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]
> 보관의 구현을 제어하려면 IM 또는 회의 보관 여부, 중요 모드 및 제거 옵션 사용 등의 옵션을 보관 구성에서 지정해야 합니다. 기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서 모든 옵션이 사용하도록 설정되어 있지 않습니다. 보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 작업 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하십시오.<BR>배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하 고 사서함을 In-Place 보존 상태로 설정 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 보관 정책을 만들어 특정 사이트 또는 사용자에 대 한 내부 또는 외부 통신의 보관을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Lync Server 2013의 보관 정책을 변경 하 여 조직, 사이트 또는 사용자에 대 한 내부 또는 외부 통신의 보관을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Lync Server 2013의 사용자에 게 보관 정책 적용](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Exchange Server 통합을 사용 하는 경우 Lync Server 2013에서 보관용 정책 설정](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Lync Server 2013에서 보관 정책 삭제](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

