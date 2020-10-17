---
title: 'Lync Server 2013: 전역 수준에서 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 939928b99c4372f3dafe9536365481fb737478a6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517545"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="2e392-102">Lync Server 2013의 전역 수준에서 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="2e392-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e392-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2e392-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2e392-104">토폴로지에 보관을 추가 하 고 토폴로지를 게시 하면 Lync Server는 보관용 글로벌 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="2e392-105">기본적으로 전역 구성에서는 보관 옵션이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="2e392-106">전역 구성에서는 전역 구성을 재정의 하는 사이트 또는 풀 구성을 설정 하지 않은 경우 전체 배포에 사용할 수 있는 옵션을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="2e392-107">전역, 사이트 및 풀 구성에 대 한 계층 구조를 비롯 하 여 보관 구성이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e392-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e392-108">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="2e392-109">전역 수준에서 보관 옵션을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="2e392-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="2e392-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2e392-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="2e392-112">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e392-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2e392-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="2e392-114">**보관 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2e392-115">**보관 설정 편집 - 전역**의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="2e392-116">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="2e392-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="2e392-117">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="2e392-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="2e392-118">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="2e392-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="2e392-119">또한 **보관 설정 편집 - 전역** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="2e392-120">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관이 실패할 경우 IM(인스턴트 메시징) 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="2e392-121">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="2e392-122">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="2e392-123">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="2e392-124">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="2e392-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="2e392-125">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e392-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

