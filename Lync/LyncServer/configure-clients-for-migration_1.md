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
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="91486-102">마이그레이션을 위한 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="91486-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91486-103">_**마지막으로 수정한 주제:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="91486-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="91486-104">이 항목에는 Lync Server 2013로 마이그레이션하기 전에 수행 해야 하는 권장 클라이언트 배포 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91486-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="91486-105">이러한 구성 변경은 Office Communications Server 2007 R2에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="91486-106">마이그레이션하기 전에 이러한 단계를 수행 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="91486-107">자세한 내용은 [Lync Server 2013의 클라이언트 및 장치 계획](lync-server-2013-planning-for-clients-and-devices.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91486-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="91486-108">마이그레이션하기 전에 클라이언트를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="91486-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="91486-109">가장 최근의 Office Communications Server 2007 R2 서버, 클라이언트 및 장치 업데이트 (핫픽스)를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="91486-110">Office Communications Server 2007 R2 업데이트 적용</span><span class="sxs-lookup"><span data-stu-id="91486-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="91486-111">Communicator 2007 R2의 누적 업데이트 패키지에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="91486-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="91486-112">장치 소프트웨어 업데이트 구하기</span><span class="sxs-lookup"><span data-stu-id="91486-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="91486-113">Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 로그인 하는 데 설치 된 최신 업데이트를 사용 하는 Office Communications Server 2007 R2 클라이언트만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="91486-114">Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 Lync Server 2013 클라이언트가 로그인 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="91486-115">다음 표에 나열 된 버전 필터 [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) 를 추가 하기 위해 **클라이언트 버전 필터링 구성** 에 설명 된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="91486-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="91486-116">각 버전 필터에 대해 작업 **블록**을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="91486-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="91486-117">클라이언트</span><span class="sxs-lookup"><span data-stu-id="91486-117">Client</span></span></th>
    <th><span data-ttu-id="91486-118">사용자 에이전트 헤더</span><span class="sxs-lookup"><span data-stu-id="91486-118">User agent header</span></span></th>
    <th><span data-ttu-id="91486-119">버전</span><span class="sxs-lookup"><span data-stu-id="91486-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="91486-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="91486-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="91486-121">OC</span><span class="sxs-lookup"><span data-stu-id="91486-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="91486-122">15 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="91486-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="91486-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="91486-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="91486-124">CWA</span><span class="sxs-lookup"><span data-stu-id="91486-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="91486-125">5 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="91486-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="91486-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="91486-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="91486-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="91486-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="91486-128">4 ...\*\* \*</span><span class="sxs-lookup"><span data-stu-id="91486-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

