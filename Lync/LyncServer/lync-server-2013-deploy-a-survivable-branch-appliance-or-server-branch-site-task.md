---
title: Sba (survivable Branch 기기 또는 서버-분기 사이트 작업 배포
description: Sba (survivable Branch 기기 또는 서버-분기 사이트 작업을 배포 합니다.
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
ms.openlocfilehash: 6b84f603f185bd507111d4767a22e9009fc0e8b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545304"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="83bf7-103">Lync Server 2013-분기 사이트 작업을 사용 하 여 Sba (survivable Branch 기기 또는 서버 배포</span><span class="sxs-lookup"><span data-stu-id="83bf7-103">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83bf7-104">_**마지막으로 수정 된 항목:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="83bf7-104">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="83bf7-105">[Sba (survivable Branch 기기 또는 Lync server 2013을 사용 하는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)의 작업을 성공적으로 완료 한 후에는 분기 사이트에서이 항목에 설명 된 두 가지 절차 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bf7-105">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="83bf7-106">이 절차를 수행하려면 RTCUniversalSBATechnicians 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bf7-106">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="83bf7-107">SBA(Survivable Branch Appliance)를 배포하려면</span><span class="sxs-lookup"><span data-stu-id="83bf7-107">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="83bf7-108">Sba (survivable Branch 기기 배포는 Sba (survivable Branch 기기 공급 업체가 웹 UI (사용자 인터페이스)를 통해 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bf7-108">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="83bf7-109">Sba (survivable 분기 기기를 배포 하는 방법에 대 한 자세한 내용은 Sba (survivable Branch 어플라이언스 공급 업체 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="83bf7-109">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="83bf7-110">지속 가능 분기 서버를 배포하려면</span><span class="sxs-lookup"><span data-stu-id="83bf7-110">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="83bf7-111">다른 Lync Server 2013 서버 역할을 설치 하는 것과 마찬가지로 Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2를 실행 하는 컴퓨터에 Lync Server 2013을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bf7-111">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="83bf7-112">Lync Server 설치에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-lync-server.md">Lync server 2013 배포</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="83bf7-112">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="83bf7-113">**다음 단계**: [Lync Server 2013에서 분기 사이트 복구를 위한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="83bf7-113">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83bf7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83bf7-114">See Also</span></span>


[<span data-ttu-id="83bf7-115">부록 A: cmdlet을 사용 하 여 Lync Server 2013에 Sba (survivable 분기 기기 배포</span><span class="sxs-lookup"><span data-stu-id="83bf7-115">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

