---
title: 'Lync Server 2013: Lync Server에서 보관용 사용자 정책 설정'
description: 'Lync Server 2013: Lync Server에서 보관에 대 한 사용자 정책을 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e33abf6cf16c9c1367162aa8beee91874f4c725
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554084"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 보관용 사용자 정책 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-10_

Lync Server 2013에 있는 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정 하려면 하나 이상의 사용자 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 적절 한 정책을 적용 해야 합니다. 사용자 정책은 사이트 및 전역 정책에 우선 하지만 Lync Server 2013에 있는 사용자 에게만 적용 됩니다.

사용자가 항상 Lync Server에 속해 있습니다. Microsoft Exchange 통합이 사용 하도록 설정 된 경우 사서함이 Microsoft Exchange Server 2013 인 사용자는 Lync Server의 보관 정책을 관리할 필요가 없습니다. 보관을 사용 하는 이러한 사용자는 Exchange In-Place 보류에서 관리 됩니다.

전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 exchange 2013에 있는 사용자에 대해 보관이 사용 하도록 설정 되어 있는지 여부를 제어 In-Place 유지 정책에 따라 제어할 수 있습니다. 이러한 사용자에 대 한 보관을 사용 하려면 사서함이 보류 In-Place에 있어야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.<BR>보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 보관에 대 한 사용자 정책 만들기 및 구성](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Lync Server 2013의 사용자에 게 Lync Server 보관 정책 적용](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

