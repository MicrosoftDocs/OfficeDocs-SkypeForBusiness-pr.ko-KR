---
title: 'Lync Server 2013: 부록 A: cmdlet을 사용 하 여 Sba (survivable 분기 기기 배포'
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
ms.openlocfilehash: b260347eaf1642c9ff86c347539439e50de179b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="970f4-102">부록 A: cmdlet을 사용 하 여 Lync Server 2013에 Sba (survivable 분기 기기 배포</span><span class="sxs-lookup"><span data-stu-id="970f4-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="970f4-103">_**마지막으로 수정 된 항목:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="970f4-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="970f4-104">이 항목에서는 Lync Server 관리 셸을 사용 하 여 Sba (survivable Branch 기기를 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="970f4-105">이 절차는 중앙 사이트에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="970f4-106">Sba (survivable Branch 기기를 원격으로 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="970f4-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="970f4-107">[Lync Server 2013의 토폴로지에 분기 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md) 의 절차에 따라 새 분기 사이트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="970f4-108">분기 사이트를 도메인에 참가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="970f4-109">RTCUniversalSBATechnicians 그룹을 로컬 Administrators 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="970f4-110">서버를 다시 시작한 다음 RTCUniversalSBATechnicians 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="970f4-111">Lync Server 관리 셸에서 다음 명령을 입력 하 고 자리 표시자를 조직의 올바른 정보로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="970f4-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
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

