---
title: Lync Server에서 보관에 대 한 사용자 정책 만들기 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8c3c83f06f7bc01d81acc18cb0c9cedb4b0ef7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 보관에 대 한 사용자 정책 만들기 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Lync Server에 있는 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정 하려면 먼저 사용자 정책을 만든 다음 하나 이상의 사용자 또는 사용자 그룹에 정책을 적용 해야 합니다. 특정 사용자 및 사용자 그룹에 사용자 정책을 적용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 사용자에 게 Lync Server 보관 정책 적용](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 을 참조 하십시오.

전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>


> [!NOTE]
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 해당 사서함을 원본 위치 유지 상태로 전환 하는지 여부를 제어 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.<BR>보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Lync Server에 있는 사용자에 대 한 보관 정책을 구성 하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다. Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.

4.  **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.

5.  **새 보관 정책**에서 다음을 수행합니다.
    
      - **이름**에 사용자 정책의 이름을 지정합니다.
    
      - **설명**에서 사용자 정책에 대한 정보를 입력합니다(예: 법률 부서용 사용자 정책).
    
      - 사용자 정책에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
      - 사용자 정책에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.

6.  **커밋**을 클릭합니다.

사용자 정책은 해당 정책을 지정한 사용자에게만 적용됩니다. 특정 사용자에 게 사용자 정책을 적용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 사용자에 게 Lync Server 보관 정책 적용](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

