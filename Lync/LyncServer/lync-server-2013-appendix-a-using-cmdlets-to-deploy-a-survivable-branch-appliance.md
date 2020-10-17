---
title: 'Lync Server 2013: 부록 A: cmdlet을 사용 하 여 Sba (survivable 분기 기기 배포'
description: 'Lync Server 2013: 부록 A: cmdlet을 사용 하 여 Sba (survivable Branch 기기를 배포 하는 방법을 소개 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1fe5d86900ec5da95ed9020720149a5015f19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561874"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>부록 A: cmdlet을 사용 하 여 Lync Server 2013에 Sba (survivable 분기 기기 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-07_

이 항목에서는 Lync Server 관리 셸을 사용 하 여 Sba (survivable Branch 기기를 배포 하는 방법에 대해 설명 합니다. 이 절차는 중앙 사이트에서 수행합니다.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Sba (survivable Branch 기기를 원격으로 배포 하려면

1.  [Lync Server 2013의 토폴로지에 분기 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md) 의 절차에 따라 새 분기 사이트를 추가 합니다.

2.  분기 사이트를 도메인에 참가시킵니다.

3.  RTCUniversalSBATechnicians 그룹을 로컬 Administrators 그룹에 추가합니다.

4.  서버를 다시 시작한 다음 RTCUniversalSBATechnicians 그룹의 구성원으로 로그온합니다.

5.  Lync Server 관리 셸에서 다음 명령을 입력 하 고 자리 표시자를 조직의 올바른 정보로 바꿉니다.
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

