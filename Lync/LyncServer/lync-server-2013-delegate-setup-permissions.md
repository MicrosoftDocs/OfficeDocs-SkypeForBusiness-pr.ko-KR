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
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013에서 설치 권한 위임

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

Lync server 2013를 배포 하는 사용자 또는 그룹에 Domain Admins 그룹의 구성원 자격을 부여 하지 않으려는 경우 RTCUniversalServerAdmins 그룹의 구성원을 사용 하도록 설정 하 여 lync server 2013를 실행 하는 서버에서 **enable-CsTopology** Windows PowerShell cmdlet을 실행할 수 있습니다. 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은이 cmdlet을 실행할 수 없습니다. **허용-CsSetupPermission** cmdlet을 사용 하 고 lync server 2013를 실행 하는 서버에 대 한 컴퓨터 개체가 있는 OU (조직 구성 단위)를 지정 하 여 lync server를 실행 하는 서버에서 **CsTopology** 를 실행 하려면 관리자 권한 및 사용 권한을 부여 합니다.

Lync Server를 설치할 때 발생 하는 도메인 준비는 RTCUniversalServerAdmins 그룹의 멤버가 Enable-CsTopology cmdlet을 실행할 수 있도록 허용 하는 사용 권한을 자동으로 추가 하지 않습니다. 즉, 토폴로지를 활성화 하기 위해 기본적으로 도메인 관리자 여야 합니다. RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지를 사용 하도록 설정 하는 권한을 부여 하려면 부여-CsSetupPermissions 사용 권한 cmdlet을 실행 해야 합니다. 또한 Lync Server를 실행 하는 컴퓨터를 포함 하는 각 Active Directory 컨테이너에 대해이 cmdlet을 실행 해야 합니다.

이 cmdlet은 RTCUniversalServerAdmins 그룹에 대 한 권한만 부여 합니다. cmdlet은 다른 보안 그룹 또는 개별 사용자에 게 사용 권한을 부여 하는 데 사용할 수 없습니다.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> 는 RTCUniversalServerAdmins 그룹 구성원이 Lync Server 2013를 설정 하 고 배포 하는 데 사용할 수 있는 키 cmdlet입니다.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>RTCUniversalServerAdmins 그룹에 Enable-CsTopology를 실행 하는 기능을 추가 하려면

1.  위임 된 사용자가 **CsTopology**를 실행할 도메인에 대 한 domain Admins 그룹의 구성원으로 서버에 로그온 합니다.

2.  Lync Server 2013 관리 셸을 엽니다. Lync Server 2013 관리 셸은 각 프런트 엔드 서버 또는 Lync Server 2013 관리 도구가 설치 된 컴퓨터에 자동으로 설치 됩니다. Lync Server 2013 관리 셸에 대 한 자세한 내용은 운영 설명서의 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md) 참조 하세요.

3.  Lync Server 2013 관리 셸에서 다음 cmdlet을 실행 합니다.
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > OU가 최상위 수준이 아니면 전체 도메인 이름을 제공 해야 합니다.

    
    </div>
    
    다음 예제에서 OU는 contoso.com 도메인에 "Lync 서버"입니다.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

