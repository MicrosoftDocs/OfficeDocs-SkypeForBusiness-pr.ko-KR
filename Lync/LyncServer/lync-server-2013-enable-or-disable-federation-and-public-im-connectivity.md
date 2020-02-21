---
title: 'Lync Server 2013: 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad7e1ecce7c292b4022f15075635a5473417db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-06-24_

지원하는 공용 IM(인스턴트 메시징) 공급자의 사용자 및 파트너 도메인을 포함하여 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자가 조직 내 사용자와 공동 작업할 수 있도록 하려면 페더레이션 지원이 필요합니다. 또한 호스팅되는 Exchange 서비스 공급자를 사용하여 Microsoft Exchange Online 등의 호스팅되는 Exchange 서비스에 사서함이 있는 Enterprise Voice 사용자에게 음성 메일을 제공하려는 경우에도 페더레이션이 필요합니다. 이러한 외부 도메인과의 트러스트 관계를 설정 하면 해당 도메인의 사용자에 게 배포에 액세스 하 여 Lync Server 통신에 참여 하도록 허가할 수 있습니다. 이러한 신뢰 관계는 페더레이션이라고 하며, Active Directory 신뢰 관계와는 관련이 없고 해당 관계에 종속되지도 않습니다.

페더레이션 도메인 사용자의 액세스를 지원하려면 페더레이션을 사용하도록 설정해야 합니다. 조직의 페더레이션을 사용하도록 설정하는 경우 다음 옵션을 구현할지 여부도 지정해야 합니다.

  - **파트너 도메인 검색**   사용이 옵션을 사용 하도록 설정 하면 Lync Server는 DNS (domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 없는 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하며, 보안 수준, 트래픽 양 및 관리자 설정에 따라 트래픽을 제한 하거나 차단 합니다. 이 옵션을 선택 하지 않으면 허용 도메인 목록에 포함 된 도메인의 사용자에 대해서만 페더레이션 사용자 액세스를 사용할 수 있습니다. 이 옵션을 선택 하지 않으면 페더레이션 도메인에서 액세스에 지 서비스를 실행 하는 특정 서버에 대 한 액세스 제한 등 개별 도메인을 차단 하거나 허용 하도록 지정할 수 있습니다. 페더레이션 도메인의 액세스를 제어 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하세요.

  - **페더레이션 파트너**     에 게 보관 고 지 사항 보내기 현재 위치에 보관 되 고 있는 페더레이션 파트너로 메시지가 전송 됩니다. 페더레이션 파트너 도메인과의 외부 통신 보관을 지 원하는 경우 보관 고 지 사항 알림을 사용 하 여 메시지가 보관 되 고 있음을 해당 파트너에 게 경고 해야 합니다.

나중에 페더레이션 도메인 사용자의 액세스를 일시적으로 또는 영구적으로 차단하려면 조직의 페더레이션을 사용하지 않도록 설정하면 됩니다. 이 섹션의 절차를 사용하여 조직에 지원할 적절한 페더레이션 옵션 지정을 비롯하여 조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하십시오.

<div>


> [!NOTE]  
> 조직에 대해 페더레이션을 사용하도록 설정하면 액세스 에지 서비스를 실행하는 서버가 페더레이션 도메인으로 라우팅하는 작업만 지원하도록 지정됩니다. 페더레이션 사용자 액세스를 지원하는 정책도 하나 이상 구성해야 페더레이션 도메인의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다. 또한 공용 IM 연결을 지원하는 정책도 하나 이상 구성해야 공용 IM 서비스 공급자의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다. 라우팅 정보를 제공하는 호스팅된 음성 메일 정책을 구성해야 사서함이 호스팅되는 Exchange 서비스에 있는 사용자에 대해 Lync Server가 호스팅되는 Exchange 서비스를 사용하여 전화 응답, Outlook Voice Access(음성 메일 포함) 또는 자동 전화 교환 서비스를 제공할 수 있습니다. 다른 조직에 있는 페더레이션 도메인의 사용자와 통신 하기 위한 정책을 구성 하는 방법에 대 한 자세한 내용은 작업 설명서의 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션 도메인 관리</A> 를 참조 하십시오. 또한 IM 서비스 공급자 사용자와의 통신을 지원하려는 경우 이를 지원하는 정책을 구성하고 지원할 개별 서비스 공급자에 대한 지원도 구성해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리</A> 를 참조 하십시오. 호스팅된 음성 메일 정책을 만드는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅 음성 메일 정책 관리</A> 를 참조 하십시오.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **액세스 에지 구성**을 클릭합니다.

4.  **액세스 에지 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **액세스 에지 구성 편집**에서 다음 중 하나를 수행합니다.
    
      - 조직의 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 조직의 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란의 선택을 취소합니다.

6.  **페더레이션 사용자와의 통신 사용** 확인란을 선택한 경우 다음을 수행하십시오.
    
    1.  파트너 도메인 자동 검색을 지원하려면 **파트너 도메인 검색 사용** 확인란을 선택합니다.
    
    2.  조직에서 외부 통신 보관을 지원하는 경우 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택합니다.

7.  **커밋**을 클릭합니다.

페더레이션 사용자가 Lync Server 2013 배포에서 사용자와 공동 작업을 할 수 있도록 하려면 페더레이션 사용자 액세스를 지원 하도록 하나 이상의 외부 액세스 정책을 구성 해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 페더레이션 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md) 참조 하십시오. 특정 페더레이션 도메인에 대 한 액세스를 제어 하려면 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md) 참조 하십시오.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함

페더레이션 및 공용 IM 연결도 Windows PowerShell 및 Set-csaccessedgeconfiguration cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>페더레이션 및 공용 IM 연결을 사용 하도록 설정 하려면

  - 페더레이션 및 공용 IM 연결을 사용하도록 설정하려면 **AllowFederatedUsers** 속성 값을 True($True)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>페더레이션 및 공용 IM 연결을 사용 하지 않도록 설정 하려면

  - 페더레이션 및 공용 IM 연결을 사용하지 않도록 설정하려면 **AllowFederatedUsers** 속성 값을 False($False)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

