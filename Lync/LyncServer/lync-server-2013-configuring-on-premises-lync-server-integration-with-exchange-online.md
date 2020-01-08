---
title: Exchange Online을 사용 하 여 온-프레미스 Lync Server 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Exchange Online과 온-프레미스 Lync Server 2013 통합 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2018-03-30_

온-프레미스 Lync Server 2013 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App을 통해 상호 운용성을 구성할 수 있습니다. 상호 운용성 기능에는 Outlook Web App 인터페이스와의 단일 사인온 및 인스턴트 메시징 (IM) 및 현재 상태 통합이 포함 됩니다. 이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 Lync Server 배포에서 Edge 서버를 구성 해야 합니다.

  - 공유 SIP 주소 공간 구성

  - Edge 서버에서 호스팅 공급자 구성

  - 업데이트 된 중앙 관리 저장소의 복제 확인

Lync Server 2013이 Exchange Online과 통합 되는 경우 OWA에서 IM에 로그인 하려는 사용자는 원격 또는 외부 사용자로 간주 됩니다. 이 시나리오에서는이 사용자에 게 다음과 같은 옵션이 선택 된 외부 액세스 정책이 할당 되어 있어야 합니다.

**원격 사용자와의 통신 설정**

회사 사용자 (예: 재택 근무 중인 사용자)와 인터넷을 통해 Lync Server에 연결할 수 있으려면이 옵션을 사용 하도록 설정 합니다.

자세한 내용은 [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)를 참조 하세요.

<div>

## <a name="configure-a-shared-sip-address-space"></a>공유 SIP 주소 공간 구성

Exchange Online에서 온-프레미스 Lync Server 2013을 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다. Lync Server와 Exchange Online 서비스에서 모두 동일한 SIP 도메인 주소 공간이 지원 됩니다.

Lync Server Management Shell을 사용 하 여 다음 예제에 표시 된 매개 변수를 사용 하 여 **Set-CSAccessEdgeConfiguration** cmdlet을 실행 하 여 페더레이션의 Edge 서버를 구성 합니다.

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers **는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다. 이 속성은 내부 사용자가 Lync Server 및 Exchange Online을 사용 하 여 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.

Lync Server Management Shell을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Edge 서버에서 호스팅 공급자 구성

Lync Server Management Shell을 사용 하 여 Edge 서버에서 호스팅 공급자를 구성 합니다. 이렇게 하려면 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 합니다.

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 중국에서 21Vianet에서 운영 하는 Office 365를 사용 하는 경우이 예제 ("exap.um.outlook.com")의 <STRONG>Proxyfqdn</STRONG> 매개 변수 값을 21vianet이 운영 하는 서비스의 FQDN으로 바꿉니다. "exap.um.partner.outlook.cn".



</div>

  - **Id** 는 만들려는 호스팅 공급자에 대 한 고유한 문자열 값 식별자를 지정 합니다 (예: "Exchange Online"). 공백이 포함 된 값은 큰따옴표로 묶어야 합니다.

  - **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이를 **True**로 설정 해야 합니다.

  - **EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간 시나리오에 사용 되는지 여부를 나타냅니다. 이를 **True**로 설정 해야 합니다.

  - **HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Office Communications Server 또는 Lync server를 호스트 하는지 여부를 나타냅니다. 이를 **False**로 설정 해야 합니다.

  - **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다. Exchange Online의 FQDN은 exap.um.outlook.com입니다.

  - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다. 이를 **False**로 설정 해야 합니다.

  - **VerificationLevel** 는 호스트 된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다. # **Ource확인**을 지정 합니다. 이 옵션은 호스팅 공급자가 보낸 메시지에 포함 된 확인 수준에 따라 달라 집니다. 이 수준을 지정 하지 않으면 메시지가 비안정형로 거부 됩니다.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>업데이트 된 중앙 관리 저장소의 복제 확인

앞의 섹션에서 cmdlet을 사용 하 여 변경한 내용은 Edge 서버에 자동으로 적용 되며, 일반적으로 복제 하는 데 1 분 미만이 걸립니다. 복제 상태를 확인 하 고 다음 cmdlet을 사용 하 여 변경 내용이 Edge 서버에 적용 되었는지 확인할 수 있습니다.

Lync Server 배포의 서버 내부에서 복제 업데이트를 확인 하려면 다음 cmdlet을 실행 합니다.

    Get-CsManagementStoreReplicationStatus

변경 내용이 적용 되었는지 확인 하려면 Edge 서버에서 다음 cmdlet을 실행 합니다.

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>참고 항목


[호스팅된 Exchange UM에서 Lync Server 2013 사용자 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

