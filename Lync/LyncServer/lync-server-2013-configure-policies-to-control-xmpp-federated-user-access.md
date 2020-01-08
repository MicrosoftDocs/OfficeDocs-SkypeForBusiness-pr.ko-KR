---
title: 'Lync Server 2013: XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 문서는 예비 문서로, 변경 될 수 있습니다. 빈 항목은 개체 틀로 포함 됩니다.

XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션 파트너 지원에 대 한 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (세션 초기화 프로토콜) 서비스 공급자의 사용자에 게는 적용 되지 않습니다. (예: Windows Live) 또는 SIP 페더레이션 도메인 사용자가 연락처를 추가 하 고 통신 하는 데 사용할 각 XMPP 페더레이션 도메인에 대해 **Xmpp 페더레이션 파트너** 를 구성 합니다. XMPP 페더레이션 파트너 정책은 글로벌 정책으로 정의 되지 않고 글로벌 정책 역할을 하는 단일 범위 에서만 사용할 수 있습니다. XMPP 페더레이션 파트너에 대해 전역, 사이트 또는 사용자 정책을 정의 하려면 먼저 필요한 범위에 대해 외부 액세스 정책을 만들고 구성 하 여 정책 범위를 구성 합니다. 외부 액세스 및 페더레이션에 대해 구성할 수 있는 정책의 유형에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) 를 참조 하세요.

<div>


> [!NOTE]  
> 모든 <STRONG>페더레이션 및 외부 액세스</STRONG> 정책은 대역내 프로비저닝을 통해 적용 됩니다. 사용자에 게 적용 되거나 사이트에 속해 있거나 범위에 전역 인 정책이 로그인 중에 클라이언트에 게 전달 됩니다. 조직에 XMPP 페더레이션을 설정 하지 않은 경우에도 XMPP 페더레이션 파트너 액세스를 제어 하도록 정책을 구성할 수 있습니다. 그러나 구성 하는 정책은 조직에 대해 XMPP 파트너 페더레이션을 배포 하 고 사용 하도록 설정한 경우에만 적용 됩니다. XMPP 파트너 페더레이션 배포 및 구성에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시지 구성을</A> 참조 하세요. 또한 XMPP 페더레이션 파트너를 제어 하기 위해 외부 액세스 정책에서 사용자 정책을 지정 하는 경우 Lync Server 2013에서 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대 한 전역 정책을 편집 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 페이지에서 글로벌 정책에 대해 다음을 수행 합니다.

5.  전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 세부 정보 표시를 클릭 합니다.

6.  전역 정책에 대 한 설명을 입력 합니다 (선택 사항).

7.  **페더레이션 사용자와의 통신 사용**을 선택 합니다.

8.  **XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.

9.  **커밋을** 클릭 하 여 전역 정책에 대 한 변경 내용을 저장 합니다.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대 한 사이트 또는 사용자 정책을 만들려면

1.  **새로 만들기**를 클릭 한 다음 **사이트 정책** 또는 **사용자 정책을**클릭 합니다. **사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.

2.  사이트 정책에 대 한 설명을 입력 합니다 (선택 사항).

3.  사이트 또는 사용자 정책에서 **페더레이션된 사용자와의 통신 사용**을 선택 합니다.

4.  **XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.

5.  **커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>XMPP 페더레이션 파트너에 대 한 기존 정책 편집

1.  기존 정책을 변경 하려면 목록에서 해당 정책을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

2.  정책에 대 한 설명을 변경 하거나 업데이트 합니다 (선택 사항).

3.  **페더레이션 사용자와의 통신 사용**을 선택 하거나 선택을 취소 합니다.

4.  **XMPP 페더레이션 사용자와의 통신 사용을**선택 하거나 선택을 취소 합니다.

5.  **커밋을** 클릭 하 여 정책에 대 한 변경 내용을 저장 합니다.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책 편집

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    페더레이션 사용자 액세스에 대 한 글로벌 정책을 True (enabled) 및 XMPP 도메인 액세스 (사용)로 설정 하는 예제 명령:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 사이트 또는 사용자 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    페더레이션 사용자 액세스를 위해 Redmond 사이트에 대 한 사이트 정책을 사용할 수 있도록 설정 하 고 XMPP 도메인 액세스를 사용 하는 경우의 예제 명령:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책 삭제

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    사용자 정책을 삭제 하는 명령 예:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  전역 정책을 기본값으로 다시 설정 하는 예제 명령:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Lync 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[부여-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

