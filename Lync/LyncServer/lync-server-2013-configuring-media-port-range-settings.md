---
title: 'Lync Server 2013: 미디어 포트 범위 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="c01b2-102">Lync Server 2013에서 미디어 포트 범위 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c01b2-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c01b2-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c01b2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c01b2-104">미디어 포트 범위 설정은 클라이언트 성능에 큰 영향을 미칠 수 있으므로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="c01b2-105">Lync Server Management Shell을 사용 하 여 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="c01b2-106">미디어 포트 범위 설정</span><span class="sxs-lookup"><span data-stu-id="c01b2-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c01b2-107">설정</span><span class="sxs-lookup"><span data-stu-id="c01b2-107">Setting</span></span></th>
<th><span data-ttu-id="c01b2-108">설명</span><span class="sxs-lookup"><span data-stu-id="c01b2-108">Description</span></span></th>
<th><span data-ttu-id="c01b2-109">Lync Server 관리 셸 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c01b2-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="c01b2-110">Cmdlet 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c01b2-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c01b2-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="c01b2-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="c01b2-112">서버에서 보낸 포트 범위를 클라이언트에서 미디어 및 신호에 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="c01b2-113">하위 값 MinMediaPort 및 MaxMediaPort와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="c01b2-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c01b2-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c01b2-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="c01b2-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c01b2-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="c01b2-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="c01b2-117">미디어에 사용할 시작 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="c01b2-118">MaxMediaPort와 결합 하 여 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="c01b2-119">권장 되는 최소 범위는 40 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="c01b2-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c01b2-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c01b2-121">ClientMediaPort (클라이언트 미디어에 사용할 시작 포트 번호를 나타냄)</span><span class="sxs-lookup"><span data-stu-id="c01b2-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c01b2-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="c01b2-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="c01b2-123">미디어에 사용할 가장 높은 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="c01b2-124">MinMediaPort와 결합 하 여 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="c01b2-125">권장 되는 최소 범위는 40 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="c01b2-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c01b2-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c01b2-127">ClientMediaPortRange (클라이언트 미디어에 사용할 수 있는 총 포트 수를 나타냅니다. 기본값은 40입니다.)</span><span class="sxs-lookup"><span data-stu-id="c01b2-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="c01b2-128">미디어 포트 범위 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c01b2-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="c01b2-129">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c01b2-130">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="c01b2-131">이 cmdlet은 회의 구성 설정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="c01b2-132">변경 하려는 매개 변수 및 값을 사용 하 여 다음 cmdlet을 실행 합니다 (이 cmdlet에 대 한 매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서 참조):</span><span class="sxs-lookup"><span data-stu-id="c01b2-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c01b2-133">특정 사이트에 대 한 추가 회의 구성 설정 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="c01b2-134">사이트 id에 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="c01b2-135">사이트에 대 한 새 회의 구성 설정을 만들면 사이트 설정이 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c01b2-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="c01b2-136">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c01b2-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

