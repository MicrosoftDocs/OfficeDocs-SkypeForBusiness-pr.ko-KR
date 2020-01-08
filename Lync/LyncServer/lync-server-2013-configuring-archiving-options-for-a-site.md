---
title: 'Lync Server 2013: 사이트의 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="4bc79-102">Lync Server 2013에서 사이트에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="4bc79-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bc79-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="4bc79-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="4bc79-104">각 사이트에 대 한 보관 구성에서 옵션을 만들고 구성 하 여 특정 사이트에 적용할 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="4bc79-105">사이트 구성은 사이트 구성에 지정 된 사이트에 대해서만 전역 구성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="4bc79-106">풀 구성은 사이트 구성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="4bc79-107">전역, 사이트 및 풀 구성에 대 한 계층 구조를 포함 하 여 보관 구성이 작동 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc79-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bc79-108">보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4bc79-109">보관을 사용 하도록 설정 하려면 보관 정책을 지정 하 여 전역 수준에서 내부 및 외부 통신을 보관 하 고, 사이트 및 사용자 수준에 따라 적절 한 경우를 제어 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="4bc79-110">사용자 수준 정책을 구성 하는 경우에는 특정 사용자 에게도 사용자 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="4bc79-111">보관 정책 만들기 및 구성에 대 한 자세한 내용은 운영 설명서의 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013에서 내부 및 외부 통신 보관 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc79-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="4bc79-112">사이트 수준에서 보관 옵션을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="4bc79-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="4bc79-113">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4bc79-114">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4bc79-115">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc79-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4bc79-116">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="4bc79-117">**보관 구성** 페이지에서 **새로 만들기**를 클릭 한 다음 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="4bc79-118">**사이트 선택**에서 보관을 위해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="4bc79-119">**새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="4bc79-120">IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="4bc79-121">IM 세션과 회의 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 웹 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="4bc79-122">정책 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="4bc79-123">또한 **새 보관 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="4bc79-124">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="4bc79-125">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="4bc79-126">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="4bc79-127">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="4bc79-128">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="4bc79-129">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc79-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

