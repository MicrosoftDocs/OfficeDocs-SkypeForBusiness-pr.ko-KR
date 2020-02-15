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
ms.openlocfilehash: 436870bd932a0cf92168555d298bf81aff1de667
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="fbc31-102">Lync Server 2013에서 보관 배포</span><span class="sxs-lookup"><span data-stu-id="fbc31-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbc31-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fbc31-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fbc31-104">Lync Server 2013에서는 Lync Server의 IM (인스턴트 메시징) 콘텐츠 및 회의 통신을 보관 하기 위한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc31-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="fbc31-105">보관 저장소를 Exchange 2013 저장소에 통합 하거나, Lync Server 2013 보관 데이터를 저장 하는 SQL Server 데이터베이스를 사용 하거나, Lync Server 2013 및 Exchange 2013 storage를 모두 사용 하 여 보관 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc31-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="fbc31-106">정책 및 보관 구성을 사용 하 여 데이터를 보관 하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc31-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="fbc31-107">자세한 내용은 계획 설명서의 [Lync server 2013에서 보관](lync-server-2013-planning-for-archiving.md) 계획, 계획 설명서, 배포 설명서 또는 작업 설명서의 [lync Server 2013에서 보관 작동 방법](lync-server-2013-how-archiving-works.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbc31-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="fbc31-108">이 섹션의 정보를 사용하여 보관을 처음으로 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc31-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="fbc31-109">배포 후에 보관 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc31-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="fbc31-110">일상적인 관리에 대 한 보관 지원을 구현 하거나 조직의 새 요구 사항을 충족 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013 아카이빙 관리](lync-server-2013-managing-archiving.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbc31-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbc31-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fbc31-111">In This Section</span></span>

  - [<span data-ttu-id="fbc31-112">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="fbc31-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="fbc31-113">Lync Server 2013의 보관을 위한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="fbc31-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="fbc31-114">Lync Server 2013에서 보관을 위한 시스템 및 인프라 설정</span><span class="sxs-lookup"><span data-stu-id="fbc31-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="fbc31-115">기존 Lync Server 2013 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="fbc31-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="fbc31-116">Lync Server 2013에서 보관에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="fbc31-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

