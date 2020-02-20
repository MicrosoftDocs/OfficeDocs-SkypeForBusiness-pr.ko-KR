---
title: 'Lync Server 2013: XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c1cce84068681640d0b19ad0f604e9a0e518c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 내용은 예비 설명서 이며 변경 될 수 있습니다. 빈 항목은 자리 표시자로 포함되어 있습니다.

XMPP(Extensible Messaging and Presence Protocol) 페더레이션 파트너 지원을 위한 정책을 구성하면 해당 정책은 XMPP 페더레이션 도메인 사용자에게는 적용되지만 SIP(Session Initiation Protocol) IM(인스턴트 메시징) 서비스 공급자(예: Windows Live) 또는 SIP 페더레이션 도메인 사용자에게는 적용되지 않습니다. 사용자가 대화 상대를 추가하고 통신하도록 허용할 각 XMPP 페더레이션 도메인에 대해 **XMPP 페더레이션 파트너**를 구성합니다. XMPP 페더레이션 파트너 정책은 단일 범위에서만 사용 가능하며, 글로벌 정책으로 정의되지는 않지만 글로벌 정책으로 작동합니다. XMPP 페더레이션 파트너에 대해 글로벌, 사이트 또는 사용자 정책을 정의하려면 먼저 필요한 범위에 대해 외부 액세스 정책을 만들고 구성하여 정책 범위를 구성합니다. 외부 액세스 및 페더레이션을 위해 구성할 수 있는 정책 유형에 대 한 자세한 내용은 작업 설명서에서 [페더레이션 및 외부 액세스에 대 한 Lync Server 2013를](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) 참조 하십시오.

<div>


> [!NOTE]  
> 모든 <STRONG>페더레이션 및 외부 액세스</STRONG> 정책은 인밴드 프로비전을 통해 적용됩니다. 사용자에게 적용되거나, 사이트에 속하거나, 범위가 글로벌인 정책은 로그인 중에 클라이언트에게 전달됩니다. 조직에 대해 XMPP 페더레이션을 사용하도록 설정하지 않았더라도 XMPP 페더레이션 파트너 액세스를 제어하는 정책을 구성할 수 있습니다. 그러나 구성하는 정책은 조직에 대해 XMPP 파트너 페더레이션을 배포하고 사용하도록 설정하고 구성하는 경우에만 적용됩니다. XMPP 파트너 페더레이션 배포 및 구성에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성을</A> 참조 하십시오. 또한 XMPP 페더레이션 파트너를 제어 하기 위해 외부 액세스 정책에서 사용자 정책을 지정 하는 경우에는 Lync Server 2013을 사용 하도록 설정 되 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대한 글로벌 정책을 편집하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **외부 액세스 정책**을 클릭합니다.

4.  **외부 액세스 정책** 페이지에서 글로벌 정책에 대해 다음을 수행합니다.

5.  글로벌 정책을 클릭하고 **편집**을 클릭한 다음 자세한 정보 표시를 클릭합니다.

6.  원하는 경우 글로벌 정책의 설명을 입력합니다.

7.  **페더레이션 사용자와의 통신 사용**을 선택합니다.

8.  Select **Enable communications with XMPP federated users(XMPP 페더레이션 사용자와의 통신 사용)** 을 선택합니다.

9.  글로벌 정책에 대한 변경 내용을 저장하려면 **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대한 사이트 또는 사용자 정책을 만들려면

1.  **새로 만들기**를 클릭하고 **사이트 정책** 또는 **사용자 정책**을 클릭합니다. **사이트 선택**의 목록에서 적절한 사이트를 클릭하고 **확인**을 클릭합니다.

2.  원하는 경우 사이트 정책의 설명을 입력합니다.

3.  사이트 또는 사용자 정책에서 **페더레이션 사용자와의 통신 사용**을 선택합니다.

4.  **XMPP 페더레이션 사용자와의 통신 사용**을 선택합니다.

5.  사이트 또는 사용자 정책에 대한 변경 내용을 저장하려면 **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대한 기존 정책을 편집하려면

1.  기존 정책을 변경하려면 목록에서 적절한 정책을 선택하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

2.  원하는 경우 정책의 설명을 변경하거나 업데이트합니다.

3.  **페더레이션 사용자와의 통신 사용**을 선택하거나 선택을 취소합니다.

4.  **XMPP 페더레이션 사용자와의 통신 사용**을 선택하거나 선택을 취소합니다.

5.  정책에 대한 변경 내용을 저장하려면 **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책을 편집 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    페더레이션 사용자 액세스에 대 한 글로벌 정책을 True (enabled) 및 XMPP 도메인 액세스를 True (enabled)로 설정 하는 예 명령입니다.
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 사이트 또는 사용자 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    아래에는 페더레이션 사용자 액세스를 위한 Redmond 사이트용 사이트 정책을 사용하도록 설정하고 XMPP 도메인 액세스를 사용하도록 설정하는 명령의 예가 나와 있습니다.
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    아래에는 사용자 정책을 삭제하는 명령의 예가 나와 있습니다.
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  아래에는 글로벌 정책을 기본값으로 다시 설정하는 명령의 예가 나와 있습니다.
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

