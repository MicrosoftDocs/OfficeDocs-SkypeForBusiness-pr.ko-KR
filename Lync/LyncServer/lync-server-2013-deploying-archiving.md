---
title: 'Lync Server 2013: 보관 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="eaa9a-102">Lync Server 2013에서 보관 배포</span><span class="sxs-lookup"><span data-stu-id="eaa9a-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaa9a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eaa9a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eaa9a-104">Lync Server 2013는 Lync Server의 IM (인스턴트 메시징) 콘텐츠 및 회의 통신을 보관 하는 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="eaa9a-105">보관 저장소를 Exchange 2013 저장소와 통합 하거나, Lync Server 2013 보관 데이터를 저장 하는 SQL Server 데이터베이스를 사용 하거나, Lync Server 2013 및 Exchange 2013 저장소를 모두 사용 하 여 아카이빙 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="eaa9a-106">정책 및 보관 구성을 사용 하 여 데이터를 보관 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="eaa9a-107">자세한 내용은 계획 설명서의 [Lync server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 및 lync server 2013의 계획 문서, 배포 설명서 또는 운영 설명서에서 보관을 수행 [하는 방법](lync-server-2013-how-archiving-works.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="eaa9a-108">이 섹션의 정보를 사용 하 여 초기에 보관을 설정 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="eaa9a-109">배포 후에는 보관 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="eaa9a-110">일일 관리에 대 한 보관 지원을 구현 하거나 조직의 새로운 요구 사항을 충족 하는 방법에 대 한 자세한 내용은 운영 설명서에서 [Lync Server 2013 보관 관리](lync-server-2013-managing-archiving.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa9a-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eaa9a-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="eaa9a-111">In This Section</span></span>

  - [<span data-ttu-id="eaa9a-112">Lync Server 2013에서 보관 하는 방식</span><span class="sxs-lookup"><span data-stu-id="eaa9a-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="eaa9a-113">Lync Server 2013의 보관용 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="eaa9a-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="eaa9a-114">Lync Server 2013에서 보관할 시스템 및 인프라 설정</span><span class="sxs-lookup"><span data-stu-id="eaa9a-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="eaa9a-115">기존 Lync Server 2013 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="eaa9a-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="eaa9a-116">Lync Server 2013에서 보관에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="eaa9a-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

