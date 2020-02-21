---
title: 'Lync Server 2013: 미디어 포트 범위 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f345b97851aac264bb3b7ef05978d80d851099ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="8b7bd-102">Lync Server 2013에서 미디어 포트 범위 설정 구성</span><span class="sxs-lookup"><span data-stu-id="8b7bd-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b7bd-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8b7bd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8b7bd-104">미디어 포트 범위 설정은 클라이언트 성능에 큰 영향을 줄 수 있으므로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="8b7bd-105">Lync Server 관리 셸을 사용 하 여 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="8b7bd-106">미디어 포트 범위 설정</span><span class="sxs-lookup"><span data-stu-id="8b7bd-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b7bd-107">설정</span><span class="sxs-lookup"><span data-stu-id="8b7bd-107">Setting</span></span></th>
<th><span data-ttu-id="8b7bd-108">설명</span><span class="sxs-lookup"><span data-stu-id="8b7bd-108">Description</span></span></th>
<th><span data-ttu-id="8b7bd-109">Lync Server 관리 셸 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8b7bd-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="8b7bd-110">Cmdlet 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b7bd-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b7bd-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="8b7bd-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-p102">사용자가 서버에서 전송된 포트 범위를 미디어 및 신호 전달에 사용해야 하는지 여부를 지정합니다. 하위 값인 MinMediaPort 및 MaxMediaPort와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-114"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8b7bd-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="8b7bd-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="8b7bd-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b7bd-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="8b7bd-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-p103">미디어에 사용할 시작 포트 번호를 지정합니다. MaxMediaPort와 함께 포트 범위를 지정합니다. 권장되는 최소 범위는 40포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-120"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8b7bd-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="8b7bd-121">ClientMediaPort(클라이언트 미디어에 사용할 시작 포트 번호를 나타냄)</span><span class="sxs-lookup"><span data-stu-id="8b7bd-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b7bd-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="8b7bd-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-p104">미디어에 사용할 최대 포트 번호를 지정합니다. MinMediaPort와 함께 포트 범위를 지정합니다. 권장되는 최소 범위는 40포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="8b7bd-126"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8b7bd-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="8b7bd-127">ClientMediaPortRange(클라이언트 미디어에 사용할 수 있는 총 포트 수를 나타내며, 기본값은 40임)</span><span class="sxs-lookup"><span data-stu-id="8b7bd-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="8b7bd-128">미디어 포트 범위 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="8b7bd-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="8b7bd-129">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8b7bd-130">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="8b7bd-131">이 cmdlet는 회의 구성 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="8b7bd-132">변경 하려는 매개 변수 및 값을 사용 하 여 다음 cmdlet을 실행 합니다 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="8b7bd-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b7bd-133">특정 사이트에 대한 추가 회의 구성 설정 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="8b7bd-134">사이트 ID로 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="8b7bd-135">사이트에 대한 새 회의 구성 설정을 만들면 사이트 설정이 전역 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="8b7bd-136">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b7bd-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

