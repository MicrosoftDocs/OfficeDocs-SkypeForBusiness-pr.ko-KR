---
title: 'Lync Server 2013: 보관 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f718ac939fc665c0464d4986f51279d3afdee8a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="25a1a-102">Lync Server 2013의 보관 개요</span><span class="sxs-lookup"><span data-stu-id="25a1a-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25a1a-103">_**마지막으로 수정한 주제:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="25a1a-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="25a1a-104">Lync Server 2013에서 보관 하면 Lync Server 2013를 통해 전송 되는 통신을 보관할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="25a1a-105">초기 Lync Server 2013 배포의 일부로 보관을 구현 하거나 기존 배포에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="25a1a-106">보관 데이터 저장소에 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 사용 하려면 토폴로지 작성기를 사용 하 여 토폴로지에 데이터베이스를 추가한 다음 토폴로지를 다시 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="25a1a-107">모든 사용자가 Exchange 2013에 있고 사서함이 원본 위치 유지에 배치 되어 있는 경우 토폴로지를 업데이트할 필요는 없지만, Exchange 2013에서 보관 된 데이터를 저장 하는 데 Microsoft Exchange 통합만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="25a1a-108">보관을 구현 하는 경우 보관 되는 항목을 지정 하도록 구성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="25a1a-109">기본적으로 보관 되는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-109">By default, nothing is archived.</span></span> <span data-ttu-id="25a1a-110">Lync Server 2013 제어판을 사용 하 여 보관을 구성 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="25a1a-111">내부 통신, 외부 통신 또는 둘 다에 대해 보관을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="25a1a-112">조직의 전체 조직과 선택적으로 특정 사이트, 특정 풀 및 특정 사용자 및 사용자 그룹에 대해 보관 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a1a-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="25a1a-113">조직에 적합 한 옵션을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관을 위한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-archiving.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25a1a-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="25a1a-114">보관 정책 및 구성을 구현 하는 방법과 보관할 수 있는 정보에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25a1a-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

