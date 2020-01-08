---
title: 'Lync Server 2013: 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-06-24_

페더레이션에 대 한 지원은 파트너 도메인 및 사용자가 지 원하는 공개 인스턴트 메시징 (IM) 제공자 사용자를 포함 하 여 계정이 있는 사용자가 사용자와 공동 작업할 수 있도록 하기 위해 필요 합니다. 구성은. 페더레이션은 또한 호스팅된 Exchange 서비스 공급자를 사용 하 여 사서함이 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스에 있는 Enterprise Voice 사용자에 게 음성 메일을 제공 해야 합니다. 이러한 외부 도메인과의 신뢰 관계를 설정한 경우 해당 도메인의 사용자에 게 배포에 액세스 하 여 Lync Server 통신에 참여 하도록 허가할 수 있습니다. 이 신뢰 관계는 페더레이션 이라고 하며 Active Directory 신뢰 관계와 관련이 없거나 종속 되어 있지 않습니다.

페더레이션 도메인 사용자가 액세스를 지원 하려면 페더레이션을 사용 하도록 설정 해야 합니다. 조직을 위해 페더레이션을 사용 하는 경우 다음 옵션을 구현할지 여부도 지정 해야 합니다.

  - **파트너 도메인 검색**   사용이 옵션을 사용 하도록 설정 하면 Lync Server에서 DNS (domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 없는 도메인을 검색 하 고 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하며 신뢰 수준, 트래픽 양, 관리자 설정에 따라 해당 트래픽을 제한 하거나 차단 합니다. 이 옵션을 선택 하지 않으면 허용 된 도메인 목록에 포함 된 도메인의 사용자만 페더레이션 사용자 액세스를 사용할 수 있습니다. 이 옵션을 선택 하는지 여부에 관계 없이 페더레이션 도메인에서 액세스 경계 서비스를 실행 하는 특정 서버에 대 한 액세스 제한을 포함 하 여 개별 도메인을 차단 또는 허용 하도록 지정할 수 있습니다. 페더레이션 도메인의 액세스를 제어 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하세요.

  - **페더레이션 파트너**     의 법적 고 지 사항 보내기 배포의 보관이 현재 위치에 있는 페더레이션 파트너로 전송 됩니다. 페더레이션 파트너 도메인과의 외부 통신 보관을 지 원하는 경우 보관 고 지 사항 알림을 사용 하 여 해당 메시지가 보관 되 고 있음을 파트너에 게 경고 해야 합니다.

나중에 페더레이션 도메인 사용자의 액세스를 일시적으로 또는 영구적으로 방지 하려면 조직에 페더레이션 기능을 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대해 지원 되는 적절 한 페더레이션 옵션 지정을 비롯 하 여 조직에 대 한 페더레이션 사용자 액세스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

<div>


> [!NOTE]  
> 조직에 페더레이션을 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버가 페더레이션 도메인에 대 한 라우팅을 지원 하도록 지정 됩니다. 페더레이션 도메인의 사용자는 페더레이션 사용자 액세스를 지원 하기 위해 하나 이상의 정책을 구성할 때까지 조직의 IM 또는 회의에 참가할 수 없습니다. 공용 im 서비스 공급자의 사용자는 공용 IM 연결을 지원 하기 위해 하나 이상의 정책을 구성할 때까지 조직의 IM 또는 회의에 참가할 수 없습니다. Lync Server는 호스팅된 음성 메일 정책을 구성할 때까지 호스트 된 Exchange 서비스에 사서함이 있는 사용자를 위한 자동 전화 교환 서비스, 전화 응답, Outlook Voice Access (음성 메일 포함)를 제공할 수 없습니다. 라우팅 정보를 제공 합니다. 다른 조직의 페더레이션 도메인 사용자와 통신 하는 데 필요한 정책을 구성 하는 방법에 대 한 자세한 내용은 운영 설명서의 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션 도메인 관리</A> 를 참조 하세요. 또한 IM 서비스 공급자의 사용자와의 통신을 지원 하려면 정책을 구성 하 고 지원 하려는 개별 서비스 공급자에 대 한 지원도 구성 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션된 공급자 관리</A> 를 참조 하세요. 호스팅된 음성 메일 정책 만들기에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</A> 를 참조 하세요.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>조직에 대 한 페더레이션 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.

4.  **액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.
    
      - 조직에 대해 페더레이션 사용자 액세스를 사용 하도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 조직의 페더레이션 사용자 액세스를 사용 하지 않도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

6.  **페더레이션 사용자와 통신 사용** 확인란을 선택한 경우 다음을 수행 합니다.
    
    1.  파트너 도메인의 자동 검색을 지원 하려면 **파트너 도메인 검색 사용** 확인란을 선택 합니다.
    
    2.  조직에서 외부 통신 보관을 지 원하는 경우 **페더레이션 파트너에 게 보관 고 지 사항 보내기** 확인란을 선택 합니다.

7.  **커밋**을 클릭합니다.

페더레이션 사용자가 Lync Server 2013 배포에서 사용자와 공동 작업할 수 있도록 하려면 하나 이상의 외부 액세스 정책을 구성 하 여 페더레이션 사용자 액세스를 지원 해야 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md) 참조 하세요. 특정 페더레이션 도메인에 대 한 액세스를 제어 하려면 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 허용 된 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md) 참조 하세요.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함

페더레이션 및 공용 IM 연결도 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>페더레이션 및 공용 IM 연결을 사용 하도록 설정 하려면

  - 페더레이션 및 공용 IM 연결을 사용 하도록 설정 하려면 **AllowFederatedUsers** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>페더레이션 및 공용 IM 연결을 사용 하지 않도록 설정 하려면

  - 페더레이션 및 공용 IM 연결을 사용 하지 않으려면 **AllowFederatedUsers** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

