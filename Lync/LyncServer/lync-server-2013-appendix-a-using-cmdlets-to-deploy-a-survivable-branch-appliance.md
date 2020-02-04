---
title: 'Lync Server 2013: 부록 A: Cmdlet을 사용하여 SBA(Survivable Branch Appliance) 배포'
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
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>부록 A: Lync Server 2013에서 Cmdlet을 사용하여 SBA(Survivable Branch Appliance) 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-07_

이 항목에서는 Lync Server Management Shell을 사용 하 여 Survivable Branch 기기를 배포 하는 방법을 설명 합니다. 중앙 사이트에서이 절차를 수행 합니다.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>원격으로 Survivable Branch 기기를 배포 하려면

1.  [Lync Server 2013의 토폴로지에 지점 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md) 의 절차에 따라 새 분기 사이트를 추가 합니다.

2.  지점 사이트를 도메인에 참가 합니다.

3.  RTCUniversalSBATechnicians 그룹을 로컬 관리자 그룹에 추가 합니다.

4.  서버를 다시 시작 하 고 RTCUniversalSBATechnicians 그룹의 구성원으로 로그온 합니다.

5.  Lync Server 관리 셸에서 다음 명령을 입력 하 고 개체 틀을 조직의 올바른 정보로 바꿉니다.
    
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

