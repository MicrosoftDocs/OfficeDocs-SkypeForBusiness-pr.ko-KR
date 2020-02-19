---
title: 'Lync Server 2013: Lync 사용자가 원격 통화 제어를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e165efe4e9b679c5464a35aac1c4130840b801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013에서 Lync 사용자가 원격 통화 제어를 사용 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

서버 기반의 대역내 프로 비전 정책을 사용 하 여 원격 통화 제어에 대 한 Lync 사용자를 구성할 수 있습니다. Lync Server 제어판 또는 Lync Server 관리 셸 명령줄 인터페이스를 사용 하 여 대역내 프로 비전 설정을 관리할 수 있습니다. 이러한 도구는 이전 버전에서 그룹 정책 설정을 관리 하는 데 사용 된 WMI (Windows Management Instrumentation) 스냅인을 대체 합니다.

사용자가 Lync에서 자체 원격 통화 제어 설정을 구성 하도록 하려면 **줄 서버 URI** 및 **줄 URI** 값을 지정 하지 않고 서버에서 사용자에 대 한 원격 통화 제어 설정을 구성 하면 됩니다. 적절 한 **회선 서버 URI** 및 **줄 uri** 값을 사용자에 게 전달 하 고 사용자에 게 이러한 설정을 구성 하기 위한 지침을 제공 해야 합니다. Lync Server에서 원격 통화 제어를 수동으로 구성 하는 절차는 Microsoft Office 웹 사이트의 Lync 클라이언트 설명서 <https://go.microsoft.com/fwlink/p/?linkid=210132> 에서 "전화 옵션 및 번호 설정"을 참조 하십시오.

기존 Communications Server 2007 R2 또는 Communications Server 2007 배포가 있는 경우 Communicator 2007 R2 및 Communicator 2007 클라이언트는 병행 마이그레이션 중에 그룹 정책을 계속 사용 합니다. 그러나 정책 설정을 Lync 클라이언트에 전달 하려면 해당 Lync Server 대역내 프로 비전 설정을 구성 해야 합니다.

<div>


> [!NOTE]  
> 사용자가 원격 통화 제어를 사용 하도록 설정 하려면 줄 URI와 줄 서버 URI를 모두 사용자에 게 제공 해야 합니다. <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013의 원격 통화 제어에 대 한 배포 작업</A>에 설명 된 대로이 설정에 대해 게이트웨이에 필요한 구문을 사용 해야 합니다.<BR>회선 서버 URI의 도메인이 게이트웨이에 대 한 고정 경로를 구성할 때 MatchUri 매개 변수에 지정한 대상 도메인과 같은지 여부를 지정 합니다.<BR>줄 URI는 전자 프로그램에서 사용자에 게 할당 되는 전화 번호를 "TEL:" 접두사를 사용 하 여 지정 합니다 (예: tel-+ 14255550150). 내선 번호를 구성 하려면 다음을 수행 합니다. + 14255550150; ext = 111. 이전에 사용자의 줄 URI를 구성 했지만 값이 변경 되지 않은 경우 원격 통화 제어에 대해 사용자를 사용 하도록 설정 하면 줄 URI를 지정할 필요가 없습니다.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>관리 셸을 사용하여 Lync 사용자가 원격 통화 제어를 사용하도록 설정하려면

1.  Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터나 **CsUser** cmdlet이 할당 된 역할 기반 액세스 제어 역할로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  **Set-CsUser** cmdlet를 사용하여 기존 Lync 사용자에 대한 원격 통화 제어를 구성하려면 다음을 수행합니다.
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    예:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용하여 원격 통화 제어에 대해 사용자를 구성하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 Uri (Uniform resource Identifier)를 모두 (또는 첫 부분)를 입력 하 고 **찾기를**클릭 합니다.

5.  표에서 수정할 사용자 계정을 클릭합니다.

6.  **편집** 메뉴에서 **수정**을 클릭합니다.

7.  **전화 통신**에서 다음 중 하나를 수행합니다.
    
      - 사용자가 Lync 2013에서 PBX (private branch exchange) 전화를 제어 하 여 pc 간 음성 통화 및 PC 간 통화를 제어할 수 있도록 하는 원격 통화 제어를 사용 하도록 설정 하려면 **원격 통화 제어**를 클릭 합니다. **줄 URI**에 사용자의 전화 번호를 지정합니다. **회선 서버 URI**에 SIP/CSTA 게이트웨이의 SIP URI를 지정합니다.
    
      - 원격 통화 제어를 사용 하도록 설정 하 되 PC 간 음성 통화를 사용 하지 않도록 설정 하 고 사용자만 Lync 2013에서 전화를 제어할 수 있도록 하 여 PC 간 통화를 설정 하려면 **원격 통화 제어만**을 클릭 합니다. **줄 URI**에 사용자의 전화 번호를 지정합니다. **회선 서버 URI**에 SIP/CSTA 게이트웨이의 SIP URI를 지정합니다.

8.  작업을 마치면 **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

