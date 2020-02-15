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
ms.openlocfilehash: fe615b0bf434b0c87a452a35528aa565c85fe5d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="97604-102">Lync Server 2013의 보관 개요</span><span class="sxs-lookup"><span data-stu-id="97604-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97604-103">_**마지막으로 수정 된 항목:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="97604-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="97604-104">Lync Server 2013의 보관은 Lync Server 2013를 통해 전송 되는 통신을 보관 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97604-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="97604-105">초기 Lync Server 2013 배포의 일부로 보관을 구현 하거나 기존 배포에이를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97604-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="97604-106">보관 데이터를 저장 하는 데 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 사용 하려면 토폴로지 작성기를 사용 하 여 토폴로지에 데이터베이스를 추가한 다음 토폴로지를 다시 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="97604-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="97604-107">모든 사용자가 Exchange 2013에 있고 사서함을 원본 위치 유지 상태로 설정 하는 경우에는 토폴로지를 업데이트할 필요가 없지만 Microsoft Exchange 통합을 사용 하 여 보관 된 데이터를 Exchange 2013에 저장 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97604-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="97604-108">보관을 구현할 때는 보관을 구성하여 보관되는 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97604-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="97604-109">기본적으로는 아무런 항목도 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97604-109">By default, nothing is archived.</span></span> <span data-ttu-id="97604-110">Lync Server 2013 제어판을 사용 하 여 보관을 구성 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="97604-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="97604-111">내부 통신이나 외부 통신 또는 둘 다에 대해 보관을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97604-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="97604-112">전체 조직에 대한 보관 설정을 구성할 수 있으며, 원하는 경우 특정 사이트/풀/사용자 및 사용자 그룹에 대해 보관 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97604-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="97604-113">조직에 적합 한 옵션을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-archiving.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97604-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="97604-114">보관 정책 및 구성을 구현 하는 방법과 보관할 수 있는 정보에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관 작동 방법을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97604-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

