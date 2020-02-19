---
title: 'Lync Server 2013: 사이트에 대 한 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9b679eabfc0538de5daf59ee1eb7742ade94228
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="8318e-102">Lync Server 2013에서 사이트에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="8318e-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8318e-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8318e-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8318e-p101">이러한 각 사이트에 대해 보관 구성에서 옵션을 만들고 구성하여 특정 사이트에 적용할 보관 옵션을 지정할 수 있습니다. 사이트 구성은 전역 구성을 무시하지만 사이트 구성에 지정된 사이트로만 제한됩니다. 풀 구성은 사이트 구성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-p101">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites. A site configuration overrides the global configuration, but only for the site specified in the site configuration. Pool configurations override site configurations</span></span>

<span data-ttu-id="8318e-107">전역, 사이트 및 풀 구성에 대 한 계층 구조를 비롯 하 여 보관 구성이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8318e-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8318e-108">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8318e-109">보관을 사용 하도록 설정 하려면 보관 정책을 지정 하 여 전역 수준에서 내부 및 외부 통신의 보관을 제어 하 고, 필요한 경우 사이트 수준과 사용자 수준에서 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="8318e-110">사용자 수준 정책을 구성 하는 경우에는 특정 사용자에 게 사용자 정책도 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="8318e-111">보관 정책을 만들고 구성 하는 방법에 대 한 자세한 내용은 작업 설명서의 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013에서 내부 및 외부 통신 보관 관리</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8318e-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="8318e-112">사이트 수준에서 보관 옵션을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="8318e-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="8318e-113">CsArchivingAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8318e-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="8318e-115">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8318e-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8318e-116">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="8318e-117">**보관 구성** 페이지에서 **새로 만들기**를 클릭한 다음 **사이트 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="8318e-118">**사이트 선택**에서 보관을 위해 구성할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="8318e-119">**새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="8318e-120">IM(인스턴트 메시징) 세션에 대해서만 보관을 사용하도록 설정하려면 **IM 세션 보관**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="8318e-121">IM 세션 및 회의 모두에 대해 보관을 사용하도록 설정하려면 **IM 및 웹 회의 세션 보관**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="8318e-122">정책에 대해 보관을 사용하지 않도록 설정하려면 **보관 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="8318e-123">또한 **새 보관 설정**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="8318e-124">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="8318e-125">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="8318e-126">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="8318e-127">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="8318e-128">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="8318e-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="8318e-129">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8318e-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

