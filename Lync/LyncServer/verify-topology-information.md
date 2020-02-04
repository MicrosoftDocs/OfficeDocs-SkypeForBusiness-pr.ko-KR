---
title: 토폴로지 정보 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec6c73f274cb67b527aaf1147f20e83959487255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="b1889-102">토폴로지 정보 확인</span><span class="sxs-lookup"><span data-stu-id="b1889-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1889-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b1889-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b1889-104">병합이 성공적으로 완료 되었는지 확인 하는 첫 번째 단계는 Lync Server 2013와 병합 한 Office Communications Server 2007 R2 토폴로지 정보를 보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="b1889-105">토폴로지 작성기에서 **BackCompatSite** 노드는 병합 한 각 Office 통신 서버 2007 R2 풀 및 서버의 FQDN (정규화 된 도메인 이름)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="b1889-106">토폴로지 작성기에서 BackCompatSite을 보려면</span><span class="sxs-lookup"><span data-stu-id="b1889-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="b1889-107">Office Communications Server 2007 R2 환경에서 Office Communications Server 2007 R2 관리 도구를 열고 레거시 풀 및 서버의 Fqdn을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="b1889-108">Lync Server 2013 환경에서 토폴로지 작성기를 열고 **BackCompatSite** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="b1889-109">병합 하는 풀 및 서버의 Fqdn이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1889-110">프런트 엔드 서버 또는 Standard Edition 서버에서 collocated 하는 서버 역할에 대 한 <STRONG>BackCompatSite</STRONG> 에는 정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="b1889-111">Office Communications Server 2007 R2 및 Lync Server 2013 간 상호 운용성에 필요한 서버 역할만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="b1889-112">![토폴로지 작성기 BackCompatSite 대화 상자](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "토폴로지 작성기 BackCompatSite 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="b1889-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="b1889-113">Lync Server 2013 제어판을 사용 하 여 병합 된 토폴로지를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="b1889-114">Lync Server 2013 제어판에서 병합 된 토폴로지의 각 서버 FQDN, 풀 FQDN 및 사이트 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="b1889-115">병합 된 서버는 **BackCompatSite**의 **사이트** 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="b1889-116">Lync Server 2013 제어판에서 병합 된 토폴로지를 보려면</span><span class="sxs-lookup"><span data-stu-id="b1889-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="b1889-117">Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="b1889-118">**토폴로지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="b1889-119">**상태** 탭에서 병합 한 서버와 풀이 **사이트** 열에서 **BackCompatSite** 을 찾아 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="b1889-120">![병합된 토폴로지를 보여 주는 Lync Server 제어판](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "병합된 토폴로지를 보여 주는 Lync Server 제어판")</span><span class="sxs-lookup"><span data-stu-id="b1889-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="b1889-121">병합 된 풀에 대 한 자세한 정보를 보려면 **Get-CsPool** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="b1889-122">이 cmdlet은 토폴로지 작성기 및 Lync Server 2013 제어판에서 사용할 수 있는 정보 외에도 Lync Server 2013 풀에서 실행 되는 서비스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1889-123">토폴로지 작성기에서 병합 마법사를 실행 한 후에 토폴로지를 게시 하면 컨퍼런스 디렉터리가 Lync Server 2013에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="b1889-124"><STRONG>CsConferenceDirectory</STRONG> cmdlet을 실행 하 여 회의 디렉터리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="b1889-125">병합 된 풀에서 서비스를 보려면</span><span class="sxs-lookup"><span data-stu-id="b1889-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="b1889-126">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="b1889-127">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="b1889-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="b1889-129">통합 된 회의 디렉터리를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="b1889-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="b1889-130">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="b1889-131">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="b1889-132">병합 하는 풀 또는 서버의 모든 컨퍼런스 디렉터리가 현재 Lync Server 2013에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1889-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

