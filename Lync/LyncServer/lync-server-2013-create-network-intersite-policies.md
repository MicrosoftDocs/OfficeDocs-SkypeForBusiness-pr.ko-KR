---
title: 'Lync Server 2013: 네트워크 사이트 간 정책 만들기'
description: 'Lync Server 2013: 네트워크 사이트 간 정책을 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9666efcb9c6da459a8e50eeae66cd1a513b46f65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562274"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="ed32d-103">Lync Server 2013에서 네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ed32d-103">Create network intersite policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed32d-104">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ed32d-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ed32d-105">*네트워크 사이트 간 정책은* 서로 간에 직접 WAN 링크가 있는 사이트 간 대역폭 제한을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-105">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="ed32d-106">자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed32d-106">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ed32d-107">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ed32d-107">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ed32d-108">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ed32d-108">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ed32d-109">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ed32d-109">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ed32d-110">Remove-csnetworkintersitepolicy을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-110">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed32d-111">네트워크 사이트 간 정책은 두 네트워크 사이트 간에 직접 상호 링크가 있는 경우에 <EM>만</EM> 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-111">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="ed32d-112">예제 토폴로지 북미 지역에는 리노 및 앨버커키 사이트 간의 직접 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-112">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="ed32d-113">이러한 두 사이트에는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-113">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="ed32d-114">다음은 20Mb 링크 프로필을 적용 하는 예제 \_ 입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-114">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="ed32d-115">네트워크 사이트 간 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ed32d-115">To create a network intersite policy</span></span>

1.  <span data-ttu-id="ed32d-116">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed32d-117">New-CsNetworkInterSitePolicy cmdlet을 실행 하 여 네트워크 간 정책을 만들고 직접 상호 연결 된 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-117">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="ed32d-118">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-118">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="ed32d-119">필요한 경우 직접 상호 연결이 있는 모든 네트워크 사이트 쌍에 대해 네트워크 사이트 간 정책을 만들려면 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32d-119">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

