---
title: IM 또는 회의 세션 보관 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97c88214d5480c36bbff88890e6960e930dd937
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="64106-102">Lync Server 2013에서 IM 또는 회의 세션 보관 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="64106-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64106-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="64106-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="64106-104">Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 IM, 회의 세션 또는 두 가지 모두의 보관을 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="64106-105">여기에는 다음 보관 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="64106-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="64106-106">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="64106-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="64106-107">보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="64106-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="64106-108">보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64106-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="64106-109">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64106-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="64106-110">보관을 사용 하려면 외부 통신을 위해 또는 Lync Server 2013에 있는 사용자에 대해 보관 정책을 사용 하도록 설정할지 여부를 지정 하는 보관 정책 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="64106-111">기본적으로 보관은 내부 또는 외부 통신 중 하나에 대해 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64106-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="64106-112">어느 정책에서든 보관을 사용하도록 설정하려면 이 섹션에 설명된 대로 먼저 배포 환경과 특정 사이트/풀(선택 사항)에 대해 적합한 보관 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="64106-113">보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64106-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="64106-114">Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 있는 보관을 배포 하는 것을 결정 한 경우 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지에서</span><span class="sxs-lookup"><span data-stu-id="64106-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="64106-115">토폴로지 작성기를 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="64106-116">자세한 내용은 작업 설명서에서 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013의 보관 데이터베이스 옵션 변경을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64106-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="64106-117">IM 또는 회의 세션의 보관을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="64106-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="64106-118">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64106-119">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="64106-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64106-120">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64106-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64106-121">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="64106-122">보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성을 선택 하 고 **편집**을 클릭 한 다음 **자세한 정보 표시**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="64106-123">메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="64106-124">IM 세션 및 전화 회의 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="64106-125">정책에 대해 보관을 사용하지 않도록 설정하려면 **보관 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="64106-126">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64106-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64106-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64106-127">See Also</span></span>


[<span data-ttu-id="64106-128">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="64106-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="64106-129">Lync Server 2013에서 보관 정책 구성 및 할당</span><span class="sxs-lookup"><span data-stu-id="64106-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

