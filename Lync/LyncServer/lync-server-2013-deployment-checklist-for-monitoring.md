---
title: 'Lync Server 2013: 모니터링을 위한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e455cb06c6890bb8925bc35a8d5f4c6775288f8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="6e5c2-102">Lync Server 2013의 모니터링을 위한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="6e5c2-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e5c2-103">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="6e5c2-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="6e5c2-104">모니터링은 각 프런트 엔드 서버에 이미 설치 되어 활성화 되어 있지만 실제로 Microsoft Lync Server 2013에 대 한 모니터링 데이터를 수집 하기 전에 먼저 수행 해야 하는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6e5c2-105">이러한 단계는 다음 검사 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e5c2-106">단계</span><span class="sxs-lookup"><span data-stu-id="6e5c2-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-107">단계</span><span class="sxs-lookup"><span data-stu-id="6e5c2-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-108">역할 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="6e5c2-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-109">설명서</span><span class="sxs-lookup"><span data-stu-id="6e5c2-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5c2-110"><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></span><span class="sxs-lookup"><span data-stu-id="6e5c2-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6e5c2-111">모니터링을 위한 백 엔드 데이터 저장소로 작동할 컴퓨터에 지원되는 버전의 Microsoft SQL Server를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-112">로컬 관리자 그룹의 구성원인 도메인 사용자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-113">지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></span><span class="sxs-lookup"><span data-stu-id="6e5c2-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="6e5c2-114">지원 가능성 가이드의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013에 제공 되는 서버 소프트웨어 및 인프라 지원</a></span><span class="sxs-lookup"><span data-stu-id="6e5c2-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5c2-115"><strong>모니터링을 지원하는 적절한 내부 토폴로지 만들기</strong></span><span class="sxs-lookup"><span data-stu-id="6e5c2-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="6e5c2-116">Lync Server 2013 토폴로지 작성기를 사용 하 여 모니터링 데이터베이스를 토폴로지에 추가한 다음 업데이트 된 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-117">토폴로지를 정의하려면 로컬 사용자 그룹의 구성원인 사용자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="6e5c2-118">토폴로지를 게시하려면 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-119">배포 가이드의 <a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013에서 모니터링 저장소를 프런트 엔드 풀과 연결</a></span><span class="sxs-lookup"><span data-stu-id="6e5c2-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5c2-120"><strong>적합한 모니터링 설정 사용</strong></span><span class="sxs-lookup"><span data-stu-id="6e5c2-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="6e5c2-121">전역 및/또는 사이트 범위에서 CDR(통화 정보 기록) 및/또는 QoE(체감 품질) 모니터링을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-122">RTCUniversalServerAdmins 그룹의 구성원인 사용자 또는 CsCdrConfiguration 및 CsQoEConfiguration cmdlet에 대한 액세스 권한을 제공하는 RBAC 역할이 지정된 사용자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5c2-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="6e5c2-123">운영 가이드의 <a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성</a></span><span class="sxs-lookup"><span data-stu-id="6e5c2-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

