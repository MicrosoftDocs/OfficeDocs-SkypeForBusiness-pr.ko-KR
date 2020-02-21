---
title: A/V 회의에 대 한 Lync Server 2013 배포 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70761edccdf47ef204e9d38b118478abb6e3824f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="a7148-102">Lync Server 2013의 A/V 회의 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="a7148-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7148-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="a7148-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="a7148-104">다른 Lync Server 2013 구성 요소를 배포 하는 경우와 마찬가지로 A/V 회의를 배포 하려면 토폴로지 작성기를 사용 하 여 회의를 통합 하는 토폴로지를 만들고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="a7148-105">배포 순서</span><span class="sxs-lookup"><span data-stu-id="a7148-105">Deployment Sequence</span></span>

<span data-ttu-id="a7148-106">초기 토폴로지를 배포 하는 동시에 또는 하나 이상의 프런트 엔드 풀 또는 Standard Edition server를 배포한 후에 회의를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="a7148-107">회의 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="a7148-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="a7148-108">다음 표에서는 기존 토폴로지에 회의를 배포하는 데 필요한 단계를 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7148-109">단계</span><span class="sxs-lookup"><span data-stu-id="a7148-109">Phase</span></span></th>
<th><span data-ttu-id="a7148-110">단계</span><span class="sxs-lookup"><span data-stu-id="a7148-110">Steps</span></span></th>
<th><span data-ttu-id="a7148-111">역할 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="a7148-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="a7148-112">설명서</span><span class="sxs-lookup"><span data-stu-id="a7148-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7148-113"><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></span><span class="sxs-lookup"><span data-stu-id="a7148-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="a7148-114">프런트 엔드 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 회의가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="a7148-115">이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a7148-116">Lync Server 2013에서는 Office Web Apps와 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="a7148-117">Office Web Apps 서버를 설치 및 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7148-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="a7148-118">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="a7148-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="a7148-119">지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></span><span class="sxs-lookup"><span data-stu-id="a7148-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="a7148-120">지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</span><span class="sxs-lookup"><span data-stu-id="a7148-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="a7148-121">계획 설명서의 <a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항 결정</a></span><span class="sxs-lookup"><span data-stu-id="a7148-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="a7148-122">계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에 보관에 대 한 기술 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="a7148-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7148-123"><strong>회의를 지원하는 데 적절한 내부 토폴로지 만들기</strong></span><span class="sxs-lookup"><span data-stu-id="a7148-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="a7148-124">토폴로지 작성기를 실행 하 여 토폴로지에 회의를 추가 하 고 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="a7148-125">토폴로지를 정의하려면 로컬 Users 그룹의 구성원 계정 필요</span><span class="sxs-lookup"><span data-stu-id="a7148-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="a7148-126">토폴로지를 게시 하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이 며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)을 포함 하 고, 토폴로지 작성기가 필요한 Dacl을 구성할 수 있도록 하는 모든 권한을 갖는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="a7148-127">배포 설명서에서 <a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지를 정의 하 고 구성</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7148-128"><strong>회의 정책 및 지원 구성</strong></span><span class="sxs-lookup"><span data-stu-id="a7148-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="a7148-129">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7148-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="a7148-130">RTCUniversalServerAdmins 그룹 (Windows PowerShell만) 또는 사용자를 [] 또는 CSAdministrator 역할에 할당</span><span class="sxs-lookup"><span data-stu-id="a7148-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="a7148-131">작업 설명서의 <a href="lync-server-2013-conferencing-policies.md">Lync Server 2013에 있는 회의 정책</a></span><span class="sxs-lookup"><span data-stu-id="a7148-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7148-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7148-132">See Also</span></span>


[<span data-ttu-id="a7148-133">Lync Server 2013의 회의 개요</span><span class="sxs-lookup"><span data-stu-id="a7148-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="a7148-134">Lync Server 2013의 회의에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="a7148-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

