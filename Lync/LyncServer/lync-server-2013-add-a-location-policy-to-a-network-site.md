---
title: 'Lync Server 2013: 네트워크 사이트에 위치 정책 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ca625746fc38d8cab9c25701a8bf22718e71e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529575"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="9bab7-102">Lync Server 2013에서 네트워크 사이트에 위치 정책 추가</span><span class="sxs-lookup"><span data-stu-id="9bab7-102">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bab7-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9bab7-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9bab7-104">다음 예에서는 [Lync Server 2013의 만들기 위치 정책](lync-server-2013-create-location-policies.md) 에 정의 된 **Redmond** 위치 정책을 기존 네트워크 사이트에 추가 하는 방법과 **redmond** 위치 정책을 사용 하는 새 네트워크 사이트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="9bab7-105">네트워크 사이트를 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bab7-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9bab7-106">**새-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="9bab7-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="9bab7-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="9bab7-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="9bab7-108">**설정-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="9bab7-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="9bab7-109">**CsNetworkSite를 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bab7-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="9bab7-110">기존 네트워크 사이트에 위치 정책을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="9bab7-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="9bab7-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9bab7-112">다음 cmdlet을 실행하여 기존 네트워크 사이트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="9bab7-113">**Redmond 태그가 지정** 된 위치 정책을 **redmond**라는 기존 네트워크 사이트에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="9bab7-114">새 네트워크 사이트에 위치 정책을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="9bab7-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="9bab7-115">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9bab7-116">다음 cmdlet을 실행하여 새 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="9bab7-117">네트워크 지역에 새 네트워크 사이트를 만들어 태그가 지정된 **Redmond** 위치 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bab7-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

