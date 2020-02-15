---
title: 'Lync Server 2013: 설치 권한 부여'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61fb0f5eac11016cf21dd8691ed9fa5f97bc804f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Lync Server 2013에서 설치 권한 부여

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-27_

**Grant-CsSetupPermission** cmdlet을 사용하여 지정된 Active Directory OU(조직 구성 단위)의 RTCUniversalServerAdmins 그룹에 Read, Write, ReadSPN 및 WriteSPN 권한을 추가할 수 있습니다. 그런 다음 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원은 Domain Admins 그룹의 구성원이 아닌 지정 된 도메인에서 Lync Server 2013을 실행 하는 서버를 설치할 수 있습니다.

**Test-CsSetupPermission** cmdlet을 통해 설치하는 권한을 확인합니다. 이렇게 하려면 **Grant-CsSetupPermission** cmdlet을 사용합니다.

**Revoke-CsSetupPermission** cmdlet을 통해 부여한 권한을 제거할 수 있습니다. 이렇게 하려면 **Grant-CsSetupPermission** cmdlet을 사용합니다.

<div>

## <a name="to-grant-setup-permissions"></a>설치 권한을 부여하려면

1.  설치 권한을 부여 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>설치 권한을 확인하려면

1.  **부여-CsSetupPermission** cmdlet을 사용 하 여 부여한 설치 권한을 확인할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>설치 권한을 해지하려면

1.  **부여-CsSetupPermission** cmdlet에 부여 된 설치 권한을 해지할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

