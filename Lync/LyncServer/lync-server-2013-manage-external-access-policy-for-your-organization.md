---
title: 'Lync Server 2013: 조직에 대한 외부 액세스 정책 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Lync Server 2013에서 외부 액세스 정책 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.

기본적으로 조직에 대해 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 외부 사용자 액세스를 지원 하도록 구성 된 정책은 없습니다. 외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 전역 정책은 만들어지지만 삭제할 수는 없습니다.

  - **전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다. 기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다. 전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다. 전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다. 전역 정책을 삭제 해도 제거 되지 않습니다. 대신 기본 설정으로 다시 설정 합니다.

  - **사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다. 예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.

  - **사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다. 예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.

<div>


> [!IMPORTANT]  
> 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.



</div>

이러한 옵션에는 다음과 같은 외부 액세스 유형이 포함 됩니다.

  - **페더레이션 사용자**   와의 통신 사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다. 이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 통신 하는 기능 뿐만 아니라 Microsoft Office 365와 같은 호스트 공급자도 연결할 수 있습니다. 이 설정을 선택 하면 XMPP 페더레이션 도메인과의 통신을 허용 하는 옵션을 선택할 수 있습니다.
    
    옵션으로, 먼저 **페더레이션 사용자와 통신 사용**을 선택 하면 **xmpp 페더레이션 파트너와 통신 사용** 을 선택할 수 있습니다. XMPP federation는 확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP)을 사용 하는 조직이 있는 페더레이션입니다.
    
    <div>
    

    > [!NOTE]  
    > XMPP 페더레이션을 사용 하는 경우에는 토폴로지 작성기의 Edge 풀 구성 섹션에서 <STRONG>Xmpp 페더레이션</STRONG> 만 배포 하도록 선택 해야 합니다. XMPP 페더레이션의 구성은 Edge 서버 및 프런트 엔드 서버의 XMPP 게이트웨이에서 XMPP 프록시를 배포 합니다.

    
    </div>

  - **원격 사용자**   와 통신 설정 방화벽 외부에 있는 사용자 (예: 출장 중인 재택 근무 사용자)가 인터넷을 통해 Lync Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.

  - **공용 사용자**   와 통신 사용 내부 사용자가 Windows Live, Yahoo\!, 북미에서 제공 하는 것과 같은 공용 IM 공급자 대화 상대와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
    > <LI>
    > <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
    > <LI>
    > <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 먼저 조직의 외부 사용자 액세스 사용을 제어 하는 정책을 구성 해야 합니다. 외부 사용자 액세스에 대 한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요.



</div>

**Windows PowerShell cmdlet을 사용 하 여 외부 액세스 정책을 보려면**

  - Lync Server Management Shell 및 **CsExternalAccessPolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.
    
    모든 외부 액세스 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsExternalAccessPolicy
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Lync Server 2013에서 Lync 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Lync Server 2013에서 외부 사용자 액세스 정책 다시 설정 또는 삭제](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

