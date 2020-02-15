---
title: 마이그레이션을 위한 클라이언트 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c5c530b51b24b23f266786cd763994c4798d1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41999193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="6ae0b-102">마이그레이션을 위한 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6ae0b-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae0b-103">_**마지막으로 수정 된 항목:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="6ae0b-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="6ae0b-104">이 항목에는 Lync Server 2013로 마이그레이션하기 전에 수행 해야 하는 권장 클라이언트 배포 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="6ae0b-105">이러한 구성 변경은 Office Communications Server 2007 r 2에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6ae0b-106">이러한 단계는 마이그레이션 전에 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="6ae0b-107">자세한 내용은 [Lync Server 2013에서 클라이언트 및 장치 계획](lync-server-2013-planning-for-clients-and-devices.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="6ae0b-108">마이그레이션 전에 클라이언트를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="6ae0b-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="6ae0b-109">가장 최근 Office Communications Server 2007 R2 서버, 클라이언트 및 장치 업데이트 (핫픽스)를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="6ae0b-110">Office Communications Server 2007 R2 업데이트 적용</span><span class="sxs-lookup"><span data-stu-id="6ae0b-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="6ae0b-111">Communicator 2007 R2의 누적 업데이트 패키지에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="6ae0b-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="6ae0b-112">장치의 소프트웨어 업데이트 가져오기</span><span class="sxs-lookup"><span data-stu-id="6ae0b-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="6ae0b-113">Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 Office Communications Server 2007 R2 클라이언트만 설치 된 최신 업데이트를 허용 하 고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="6ae0b-114">Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 Lync Server 2013 클라이언트가 로그인 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="6ae0b-115">다음 표에 나와 있는 버전 필터 [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) 를 추가 하려면 **클라이언트 버전 필터링 구성** 에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="6ae0b-116">각 버전 필터에 대해 **차단** 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae0b-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="6ae0b-117">클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ae0b-117">Client</span></span></th>
    <th><span data-ttu-id="6ae0b-118">사용자 에이전트 헤더</span><span class="sxs-lookup"><span data-stu-id="6ae0b-118">User agent header</span></span></th>
    <th><span data-ttu-id="6ae0b-119">Version</span><span class="sxs-lookup"><span data-stu-id="6ae0b-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6ae0b-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6ae0b-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-121">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="6ae0b-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-122">15 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="6ae0b-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ae0b-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="6ae0b-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-124">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="6ae0b-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-125">5 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="6ae0b-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ae0b-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6ae0b-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-127">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="6ae0b-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="6ae0b-128">4 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="6ae0b-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

