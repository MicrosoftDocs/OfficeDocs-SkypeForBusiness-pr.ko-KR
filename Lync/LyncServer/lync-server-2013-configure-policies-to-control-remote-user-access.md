---
title: 'Lync Server 2013: 원격 사용자 액세스를 제어하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

원격 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 원격 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 사이트 정책은 글로벌 정책 보다 우선 하며 사용자 정책은 사이트 및 전역 정책 보다 우선 합니다. 구성할 수 있는 정책의 유형에 대 한 자세한 내용은 [Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)를 참조 하세요. 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.

<div>


> [!NOTE]  
> 조직의 원격 사용자 액세스를 사용 하도록 설정 하지 않은 경우에도 원격 사용자 액세스를 제어 하도록 정책을 구성할 수 있습니다. 그러나 사용자가 구성한 정책은 조직에 대해 원격 사용자 액세스를 사용할 수 있는 경우에만 적용 됩니다. 원격 사용자 액세스를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을</A>참조 하세요. 또한 원격 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우에는 Lync Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다. 원격 위치에서 Lync Server에 로그인 할 수 있는 사용자를 지정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013에서 lync를 사용 하는 사용자에 게 외부 사용자 액세스 정책 할당</A>을 참조 하세요.



</div>

다음 절차를 사용 하 여 원격 사용자 액세스를 제어 하는 데 사용할 각 외부 액세스 정책을 구성 합니다.

<div>


> [!NOTE]  
> 이 절차에서는 원격 사용자와의 통신을 사용 하도록 정책을 구성 하는 방법에 대해 설명 하지만 원격 사용자 액세스를 지원 하도록 구성 하는 각 정책은 페더레이션된 사용자 액세스 및 공용 사용자 액세스를 구성할 수도 있습니다. 페더레이션 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하세요. 공용 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</A>을 참조 하세요.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>원격 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 원격 사용자 액세스를 지원 하도록 전역 정책을 구성 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다. **사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. **새 외부 액세스 정책**에서 사용자 정책이 적용 되는 항목을 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: remote users에 대 한 통신을 사용 하도록 설정 하는 사용자 정책에 대 한 **enableremoteusers** ).
    
      - 기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  ) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.

6.  다음 중 하나를 수행 합니다.
    
      - 정책에 대 한 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 정책에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

원격 사용자 액세스를 사용 하도록 설정 하려면 조직에서 원격 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 참조 하세요.

사용자 정책 인 경우 원격으로 연결할 수 있도록 하는 사용자에 게도 정책을 적용 해야 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

