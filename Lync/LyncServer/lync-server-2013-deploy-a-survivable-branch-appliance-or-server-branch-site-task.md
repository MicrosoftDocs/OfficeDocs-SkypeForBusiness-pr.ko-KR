---
title: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 분기 사이트 작업
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2edf70ccbc4817942775d953b7d43313d96e25c7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="b0aa4-102">Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 분기 사이트 작업</span><span class="sxs-lookup"><span data-stu-id="b0aa4-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0aa4-103">_**마지막으로 수정한 주제:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="b0aa4-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="b0aa4-104">[Survivable Branch 기기 또는 Lync server 2013를 사용 하 여 서버를 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)하는 작업을 성공적으로 완료 한 후 지점 사이트에서이 항목에 설명 된 두 가지 절차 중 하나를 수행 합니다-중앙 사이트 작업</span><span class="sxs-lookup"><span data-stu-id="b0aa4-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b0aa4-105">이 절차를 수행 하려면 RTCUniversalSBATechnicians 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="b0aa4-106">Survivable Branch 기기를 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="b0aa4-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="b0aa4-107">Survivable Branch 기기 배포는 웹 UI (사용자 인터페이스)를 통해 Survivable Branch 기기 공급 업체에서 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="b0aa4-108">Survivable Branch 기기 배포에 대 한 자세한 내용은 Survivable Branch 기기 공급 업체 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="b0aa4-109">Survivable Branch 서버를 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="b0aa4-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="b0aa4-110">다른 Lync Server 2013 서버 역할을 설치 하는 것과 마찬가지로 Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2를 실행 하는 컴퓨터에 Lync Server 2013을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b0aa4-111">Lync Server 설치에 대 한 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-lync-server.md">Lync server 2013 배포</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="b0aa4-112">**다음 단계**: [Lync Server 2013에서 지점 사이트 복원에 대 한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="b0aa4-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0aa4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0aa4-113">See Also</span></span>


[<span data-ttu-id="b0aa4-114">부록 A: Lync Server 2013에서 Cmdlet을 사용하여 SBA(Survivable Branch Appliance) 배포</span><span class="sxs-lookup"><span data-stu-id="b0aa4-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

