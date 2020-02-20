---
title: 'Lync Server 2013: 원격 사용자 액세스를 제어 하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429d1751f9b9628df98c05112838715de2b249d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

원격 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 사이트 정책은 글로벌 정책보다 우선 적용되며 사용자 정책은 사이트 정책 및 글로벌 정책보다 우선 적용됩니다. 구성할 수 있는 정책 유형에 대 한 자세한 내용은 [Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)를 참조 하세요. 한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 대해 자세히 설정 된다는 것을 의미 하며 개체에 대 한 영향을 더 줍니다.

<div>


> [!NOTE]  
> 조직에 대해 원격 사용자 액세스를 사용하도록 설정하지 않았더라도 원격 사용자 액세스를 제어하는 정책을 구성할 수 있습니다. 그러나 구성하는 정책은 조직에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우에만 적용됩니다. 원격 사용자 액세스를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을</A>참조 하세요. 또한 원격 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우이 정책은 Lync Server에 대해 사용 하도록 설정 되 고 정책을 사용 하도록 구성 된 사용자 에게만 적용 됩니다. 원격 위치에서 Lync Server에 로그인 할 수 있는 사용자를 지정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</A>을 참조 하십시오.



</div>

원격 사용자 액세스를 제어하는 데 사용할 각 외부 액세스 정책을 구성하려면 다음 절차를 사용합니다.

<div>


> [!NOTE]  
> 이 절차에서는 원격 사용자와의 통신을 가능하게 하는 정책을 구성하는 방법에 대해서만 설명하지만, 원격 사용자 액세스를 지원하기 위해 구성하는 각 정책은 페더레이션 사용자 액세스 및 공용 사용자 액세스도 구성할 수 있습니다. 페더레이션 사용자를 지원 하기 위한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오. 공용 사용자를 지원 하기 위한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</A>을 참조 하십시오.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>원격 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **외부 액세스 정책**을 클릭합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.
    
      - 원격 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책, **편집**을 차례로 클릭한 다음 **세부 정보 표시**를 클릭합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다. **사이트 선택**의 목록에서 적절한 사이트를 클릭하고 **확인**을 클릭합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다. **새 외부 액세스 정책**에서 사용자 정책에서 다루는 내용을 나타내는 고유 이름을 **이름** 필드에 만듭니다(예: 원격 사용자에 대한 통신을 가능하게 하는 사용자 정책의 경우 **EnableRemoteUsers**).
    
      - 기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시**를 차례로 클릭합니다.

5.  (선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명**에 지정합니다.

6.  다음 중 하나를 수행합니다.
    
      - 정책에 대해 원격 사용자 액세스를 사용하도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 정책에 대해 원격 사용자 액세스를 사용하지 않도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택 취소합니다.

7.  **커밋**을 클릭합니다.

원격 사용자 액세스를 사용하도록 설정하려면 조직에서 원격 사용자 액세스에 대한 지원을 사용하도록 설정해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 참조 하세요.

사용자 정책의 경우에는 원격으로 연결할 수 있도록 하려는 사용자에게도 정책을 적용해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

