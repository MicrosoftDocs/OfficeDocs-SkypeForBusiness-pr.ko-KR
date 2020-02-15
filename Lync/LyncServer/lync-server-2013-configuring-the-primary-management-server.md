---
title: 'Lync Server 2013: 기본 관리 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6640e13209700d50aac04c43728175a4fcb4e6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="5a3f6-102">Lync Server 2013에서 기본 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="5a3f6-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a3f6-103">_**마지막으로 수정 된 항목:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="5a3f6-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="5a3f6-104">Microsoft Lync Server 2013에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 관리자가 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다. 이 컴퓨터에서 System Center Operations Manager 2007 R2 또는 System Center Operations Manager 2012을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="5a3f6-105">또한 Operations Manager 백 엔드 데이터베이스로 작동 하려면 지원 되는 버전의 SQL Server를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="5a3f6-106">System Center Operations Manager 2012를 사용 하는 경우 다음 SQL Server 버전을 백 엔드 데이터베이스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="5a3f6-107">SQL Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="5a3f6-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="5a3f6-108">SQL Server 2008 R2 서비스 팩 2</span><span class="sxs-lookup"><span data-stu-id="5a3f6-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="5a3f6-109">System Center Operations Manager 2007 R2를 사용 하는 경우 SQL Server 2005 서비스 팩 4 또는 SQL Server 2008 서비스 팩 3을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="5a3f6-110">System Center Operations Manager 2007 r 2의 백 엔드 데이터베이스로 SQL Server 2008 R2를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="5a3f6-111">System Center Operations Manager 2007 r 2에서 작동 하도록 SQL Server 2008 R2를 구성 하는 방법에 대 한 자세한 내용은이 설명서의 부록 1을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="5a3f6-112">System Center Operations Manager 2012 또는 System Center Operations Manager 2007 r 2를 설치 하는 경우에는 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="5a3f6-113">운영 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="5a3f6-113">Operational database</span></span>

  - <span data-ttu-id="5a3f6-114">Server</span><span class="sxs-lookup"><span data-stu-id="5a3f6-114">Server</span></span>

  - <span data-ttu-id="5a3f6-115">콘솔용</span><span class="sxs-lookup"><span data-stu-id="5a3f6-115">Console</span></span>

  - <span data-ttu-id="5a3f6-116">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="5a3f6-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="5a3f6-117">웹 콘솔</span><span class="sxs-lookup"><span data-stu-id="5a3f6-117">Web console</span></span>

  - <span data-ttu-id="5a3f6-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="5a3f6-118">Reporting</span></span>

  - <span data-ttu-id="5a3f6-119">데이터 웨어하우스</span><span class="sxs-lookup"><span data-stu-id="5a3f6-119">Data warehouse</span></span>

<span data-ttu-id="5a3f6-120">이러한 구성 요소 및 구성 요소의 설치에 대해서는 이 문서에서 자세히 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="5a3f6-121">System Center Operations Manager 2007 r 2에 대 한 자세한 내용은 Operations Manager 2007 R2 설명서 <http://go.microsoft.com/fwlink/p/?linkid=257526> 및 System Center operations Manager 2012 설명서를 참조 하십시오 <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="5a3f6-122">SQL Server 2005 또는 SQL Server 2008 서비스 팩 1을 백 엔드 데이터베이스로 사용 하려는 경우에는 이러한 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="5a3f6-123">System Center Operations Manager 2012를 사용 하는 경우 백 엔드 데이터베이스로 SQL Server 2012을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="5a3f6-124">SQL Server 2012에 대 한 자세한 내용은 온라인 설명서 for SQL Server 2012를 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="5a3f6-125">기본 관리 서버는 Lync Server 배포 당 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="5a3f6-126">또한 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 r 2를 사용할 수 있지만 두 응용 프로그램을 동시에 실행할 수는 없습니다 (둘 중 하나를 선택 해야 함).</span><span class="sxs-lookup"><span data-stu-id="5a3f6-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="5a3f6-127">예를 들어 System Center Operations Manager 2012을 실행 하는 경우 모든 System Center 에이전트에서 System Center Operations Manager 2012도 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="5a3f6-128">System Center Operations Manager 2012 및 System Center Operations Manager 2007 r 2를 실행 하는 에이전트를 실행 하는 에이전트도 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3f6-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

