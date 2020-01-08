---
title: 'Lync Server 2013: 네트워크 사이트 간 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="c749b-102">Lync Server 2013에서 네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c749b-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c749b-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c749b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c749b-104">*네트워크 사이트 간 정책은* 서로 직접적인 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="c749b-105">자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c749b-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="c749b-106">새로운 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="c749b-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="c749b-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="c749b-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="c749b-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="c749b-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="c749b-109">제거-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="c749b-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c749b-110">네트워크 사이트 간 정책은 두 네트워크 사이트 간에 직접 상호 연결 된 경우에 <EM>만</EM> 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="c749b-111">예제 토폴로지 지역에는 Reno 및 Albuquerque 사이트 간의 직접적인 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="c749b-112">이러한 두 사이트는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="c749b-113">다음 예에서는 20Mb\_링크 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="c749b-114">네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c749b-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="c749b-115">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c749b-116">CsNetworkInterSitePolicy cmdlet을 실행 하 여 네트워크 사이트 간 정책을 만들고 직접 교차 링크가 있는 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="c749b-117">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="c749b-118">필요에 따라 2 단계를 반복 하 여 직접 상호 연결 된 모든 네트워크 사이트 쌍에 대 한 네트워크 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c749b-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

