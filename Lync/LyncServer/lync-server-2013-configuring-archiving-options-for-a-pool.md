---
title: 'Lync Server 2013: 풀에 대 한 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae5547320a9af0f11870ad0dc92ba03e40d8af4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="20ba6-102">Lync Server 2013에서 풀에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="20ba6-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20ba6-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="20ba6-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="20ba6-104">각 풀에 대 한 보관 구성에서 옵션을 만들고 구성 하 여 특정 풀에 적용할 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-104">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="20ba6-105">풀 구성은 전역 구성 및 사이트 구성 보다 우선 하지만 풀 구성에 지정 된 풀에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-105">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="20ba6-106">전역, 사이트 및 풀 구성에 대 한 계층 구조를 포함 하 여 보관 구성이 작동 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20ba6-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20ba6-107">보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="20ba6-108">자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013에서 보관 옵션 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20ba6-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="20ba6-109">풀 수준에서 보관 옵션을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="20ba6-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="20ba6-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20ba6-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="20ba6-112">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20ba6-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20ba6-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="20ba6-114">**보관 구성** 페이지에서 **새로 만들기**를 클릭 한 다음 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="20ba6-115">**서비스 선택**에서 보관을 위해 구성할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="20ba6-116">**새 보관 설정**의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="20ba6-117">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="20ba6-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="20ba6-118">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="20ba6-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="20ba6-119">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="20ba6-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="20ba6-120">또한 **새 보관 설정** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="20ba6-121">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="20ba6-122">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="20ba6-123">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="20ba6-124">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="20ba6-125">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="20ba6-126">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20ba6-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

