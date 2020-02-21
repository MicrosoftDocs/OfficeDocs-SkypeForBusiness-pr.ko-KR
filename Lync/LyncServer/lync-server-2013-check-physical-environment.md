---
title: 'Lync Server 2013: 실제 환경 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e85f99250161433ba895f287521367d1b76cec1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="52ba8-102">물리적 환경 검사 수행</span><span class="sxs-lookup"><span data-stu-id="52ba8-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52ba8-103">_**마지막으로 수정 된 항목:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="52ba8-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="52ba8-104">Lync Server 2013 배포의 성능, 가용성 및 기능을 확인 하기 전에 실제 환경을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="52ba8-105">예를 들어 서버 대화방 온도를 낮추지 않거나 네트워크 케이블을 교체 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="52ba8-106">최상의 결과를 위해 다음과 같은 물리적 환경 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="52ba8-107">**실제 보안**   잠금, 문 및 제한 된 액세스 대화방과 같은 물리적 보안 보호를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="52ba8-108">승인 되지 않은 항목과 강제 입력 및 장비 손상 징후를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="52ba8-109">**온도 및 습도**   높은 온도, 불량 공기 흐름 및 습도로 인해 하드웨어 구성 요소가 과열 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="52ba8-110">온도와 습도를 확인 하 여 난방 및 공기 조절 같은 환경 시스템이 하드웨어 제조업체의 사양 내에서 적합 한 조건을 유지 하 고 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="52ba8-111">최근에 새 장비가 설치 된 경우에도 서버에서 주고 받은 air이 unimpeded 하 고 제조업체 사양을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="52ba8-112">**장치 및 구성 요소**   Lync Server 2013 조직은 작동 하는 물리적 네트워크와 관련 하드웨어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="52ba8-113">라우터, 스위치, 허브, 실제 케이블 및 커넥터가 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="52ba8-114">이러한 검사를 수행 하는 방법에 대 한 자세한 내용은 설치 사이트 및 선택한 서버 하드웨어에 따라 크게 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="52ba8-115">이 검사를 처음 수행할 때 하드웨어 설명서를 참조 하 고 나중에 참조할 수 있도록 원하는 매개 변수를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="52ba8-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="52ba8-116">필요한 서버 공간 환경</span><span class="sxs-lookup"><span data-stu-id="52ba8-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52ba8-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52ba8-117">Parameter</span></span></th>
<th><span data-ttu-id="52ba8-118">원하는 값 또는 범위</span><span class="sxs-lookup"><span data-stu-id="52ba8-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52ba8-119">Temperature</span><span class="sxs-lookup"><span data-stu-id="52ba8-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52ba8-120">~</span><span class="sxs-lookup"><span data-stu-id="52ba8-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52ba8-121">서버 면 앞면</span><span class="sxs-lookup"><span data-stu-id="52ba8-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="52ba8-122">Hot aisle/콜드 aisle</span><span class="sxs-lookup"><span data-stu-id="52ba8-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52ba8-123">Unimpeded 배기 여유 공간</span><span class="sxs-lookup"><span data-stu-id="52ba8-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

