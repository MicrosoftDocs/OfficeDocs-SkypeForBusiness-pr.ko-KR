---
title: 'Lync Server 2013: 설치 권한 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5660a78bcad4d125fbf32204331b433978a831d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013에서 설치 권한 위임

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

Lync server 2013을 배포 하는 사용자 또는 그룹에 Domain Admins 그룹의 구성원 자격을 부여 하지 않으려면 RTCUniversalServerAdmins 그룹의 구성원이 lync server 2013를 실행 하는 서버에서 **enable-cstopology** Windows PowerShell cmdlet을 실행할 수 있도록 설정 하면 됩니다. 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 이 cmdlet을 실행할 수 없습니다. **부여-CsSetupPermission** cmdlet을 사용 하 고 lync server 2013을 실행 하는 서버에 대 한 컴퓨터 개체가 있는 OU (조직 구성 단위)를 지정 하 여 lync server를 실행 하는 서버에서 **enable-cstopology** 를 실행 하는 관리자 권한 및 사용 권한을 부여 합니다.

Lync Server를 설치할 때 수행 되는 도메인 준비에는 RTCUniversalServerAdmins 그룹의 구성원이 Enable-cstopology cmdlet을 실행할 수 있도록 하는 권한이 자동으로 추가 되지 않습니다. 이는 기본적으로 토폴로지를 사용하려면 도메인 관리자여야 함을 의미합니다. RTCUniversalServerAdmins 그룹의 구성원에게 토폴로지를 사용할 수 있는 권한을 부여하려면 Grant-CsSetupPermissions cmdlet을 실행해야 합니다. 또한 Lync Server를 실행 하는 컴퓨터가 있는 각 Active Directory 컨테이너에 대해이 cmdlet을 실행 해야 합니다.

이 cmdlet은 RTCUniversalServerAdmins 그룹에만 사용 권한을 부여하며, 다른 보안 그룹 또는 개별 사용자에게 사용 권한을 부여하는 데는 사용할 수 없습니다.

<div>


> [!NOTE]  
> <STRONG>Enable-enable-cstopology</STRONG> 은 RTCUniversalServerAdmins 그룹 구성원이 Lync Server 2013을 설정 및 배포할 수 있도록 하는 키 cmdlet입니다.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>RTCUniversalServerAdmins 그룹에 Enable-CsTopology를 실행할 수 있는 권한을 추가하려면

1.  위임된 사용자가 **Enable-CsTopology**를 실행하는 도메인에 대한 Domain Admins 그룹의 구성원으로 서버에 로그온합니다.

2.  Lync Server 2013 관리 셸을 엽니다. Lync Server 2013 관리 셸은 각 프런트 엔드 서버 또는 Lync Server 2013 관리 도구가 설치 된 컴퓨터에 자동으로 설치 됩니다. Lync Server 2013 관리 셸에 대 한 자세한 내용은 작업 설명서에서 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md) 을 참조 하십시오.

3.  Lync Server 2013 관리 셸에서 다음 cmdlet을 실행 합니다.
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > OU가 최상위 수준이 아닌 경우 전체 도메인 이름을 제공해야 합니다.

    
    </div>
    
    다음 예에서 OU는 contoso.com 도메인에 있는 "Lync Server"입니다.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

