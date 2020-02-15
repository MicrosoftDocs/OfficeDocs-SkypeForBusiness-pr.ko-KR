---
title: 'Lync Server 2013: 조직에 대 한 외부 액세스 정책 관리'
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
ms.openlocfilehash: 3a7a3d612de9cf530e512031b7009a83ad9c391c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Lync Server 2013에서 외부 액세스 정책 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

하나 이상의에 지 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.

조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 글로벌 정책이 만들어지지만 삭제할 수는 없습니다.

  - **글로벌 정책**   에 지 서버를 배포할 때 전역 정책이 만들어집니다. 기본적으로 글로벌 정책에서는 외부 사용자 액세스 옵션이 사용 되지 않습니다. 전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 글로벌 정책을 구성 합니다. 전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다. 전역 정책을 삭제 하는 경우에는 제거 하지 않습니다. 대신 기본 설정으로 다시 설정 합니다.

  - **사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스에 대 한 지원을 제한 하도록 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다. 예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.

  - **사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스에 대 한 지원을 제한 하기 위해 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다. 예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.

<div>


> [!IMPORTANT]  
> 한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 대해 자세히 설정 된다는 것을 의미 하며 개체에 대 한 영향을 더 줍니다.



</div>

이러한 옵션에는 다음과 같은 유형의 외부 액세스가 포함됩니다.

  - **페더레이션 사용자**   와의 통신 사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다. 이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 통신할 수 있으며 Microsoft Office 365 같은 호스트 된 공급자도 구성 됩니다. 이 설정을 선택 하면 XMPP 페더레이션 도메인과의 통신을 허용 하는 옵션을 선택할 수 있습니다.
    
    **페더레이션 사용자와의 통신 사용**을 처음 선택할 경우에는 옵션으로 **XMPP 페더레이션 파트너와의 통신 사용**을 선택할 수 있습니다. XMPP 페더레이션은 XMPP(Extensible Messaging and Presence Protocol)를 사용하는 조직과의 페더레이션입니다.
    
    <div>
    

    > [!NOTE]  
    > XMPP 페더레이션을 사용 하도록 설정 하는 경우에는 토폴로지 작성기의에 지 풀 구성 섹션에서 <STRONG>Xmpp 페더레이션</STRONG> 도 배포 하도록 선택 해야 합니다. XMPP 페더레이션을 구성 하는 경우에는에 지 서버 및 프런트 엔드 서버의 XMPP 게이트웨이에서 XMPP 프록시를 배포 합니다.

    
    </div>

  - **원격 사용자**   와의 통신 사용 사용자가 방화벽 외부에 있는 조직 (예: 재택 근무자 및 사용자가 인터넷을 통해 Lync Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정)을 선택 합니다.

  - **공용 사용자**   와의 통신 사용 내부 사용자가 공용 IM 공급자 연락처 (예: Windows Live, Yahoo\!및 북미 온라인)에서 제공 하는 대화 상대와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
    > <LI>
    > <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
    > <LI>
    > <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 조직에서 외부 사용자 액세스 사용을 제어하는 정책을 구성해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다. 외부 사용자 액세스에 대 한 정책을 만들고 구성 하 고 적용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요.



</div>

**Windows PowerShell cmdlet을 사용 하 여 외부 액세스 정책을 보려면**

  - Lync Server 관리 셸 및 **get-csexternalaccesspolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.
    
    모든 외부 액세스 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsExternalAccessPolicy
    
    이 명령은 다음과 비슷한 정보를 반환합니다.
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Lync Server 2013에서 외부 사용자 액세스 정책 다시 설정 또는 삭제](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

