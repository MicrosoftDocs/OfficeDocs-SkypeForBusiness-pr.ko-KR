---
title: 'Lync Server 2013: 주 관리 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b34c685ef59c6315b9d1a667f0715aa4300a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="d9d56-102">Lync Server 2013에서 주 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="d9d56-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d56-103">_**마지막으로 수정한 주제:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="d9d56-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="d9d56-104">Microsoft Lync Server 2013 관리자에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다. 이 컴퓨터에서 System Center Operations Manager 2007 R2 또는 System Center Operations Manager 2012을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="d9d56-105">또한 Operations Manager 백 엔드 데이터베이스로 작동 하려면 지원 되는 버전의 SQL Server를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="d9d56-106">System Center Operations Manager 2012를 사용 하는 경우 다음 버전의 SQL Server를 백 엔드 데이터베이스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="d9d56-107">SQL Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="d9d56-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="d9d56-108">SQL Server 2008 R2 서비스 팩 2</span><span class="sxs-lookup"><span data-stu-id="d9d56-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="d9d56-109">System Center Operations Manager 2007 R2를 사용 하는 경우 SQL Server 2005 서비스 팩 4 또는 SQL Server 2008 서비스 팩 3 중 하나를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="d9d56-110">System Center Operations Manager 2007 R2 용 백 엔드 데이터베이스로 SQL Server 2008 R2를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="d9d56-111">이 설명서의 부록 1을 참조 하 여 SQL Server 2008 R2를 System Center Operations Manager 2007 R2와 함께 사용 하도록 구성 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d9d56-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="d9d56-112">System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 설치 하는 경우 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="d9d56-113">운영 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="d9d56-113">Operational database</span></span>

  - <span data-ttu-id="d9d56-114">서버</span><span class="sxs-lookup"><span data-stu-id="d9d56-114">Server</span></span>

  - <span data-ttu-id="d9d56-115">콘솔</span><span class="sxs-lookup"><span data-stu-id="d9d56-115">Console</span></span>

  - <span data-ttu-id="d9d56-116">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d9d56-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="d9d56-117">웹 콘솔</span><span class="sxs-lookup"><span data-stu-id="d9d56-117">Web console</span></span>

  - <span data-ttu-id="d9d56-118">보고</span><span class="sxs-lookup"><span data-stu-id="d9d56-118">Reporting</span></span>

  - <span data-ttu-id="d9d56-119">데이터 웨어하우스</span><span class="sxs-lookup"><span data-stu-id="d9d56-119">Data warehouse</span></span>

<span data-ttu-id="d9d56-120">이 문서에서는 이러한 구성 요소와 설치에 대해 자세히 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="d9d56-121">System Center Operations Manager 2007 R2에 대 한 자세한 내용은 Operations Manager 2007 R2 설명서 <http://go.microsoft.com/fwlink/p/?linkid=257526> 와 System Center operations Manager 2012 설명서를 참조 하세요. <http://go.microsoft.com/fwlink/p/?linkid=257527></span><span class="sxs-lookup"><span data-stu-id="d9d56-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="d9d56-122">백 엔드 데이터베이스로 SQL Server 2005 또는 SQL Server 2008 서비스 팩 1을 사용 하는 경우에는 이러한 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="d9d56-123">System Center Operations Manager 2012를 사용 하는 경우 백 엔드 데이터베이스로 SQL Server 2012을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="d9d56-124">SQL Server 2012에 대 한 자세한 내용은 SQL Server 2012의 온라인 설명서를 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d56-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="d9d56-125">Lync Server 배포 당 하나의 주 관리 서버만을 사용할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d56-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="d9d56-126">또한 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 사용할 수 있지만 두 응용 프로그램을 동시에 실행할 수는 없습니다 (둘 중 하나를 선택 해야 함).</span><span class="sxs-lookup"><span data-stu-id="d9d56-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="d9d56-127">예를 들어 System Center Operations Manager 2012를 실행 하는 경우 모든 시스템 센터 에이전트는 System Center Operations Manager 2012도 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="d9d56-128">일부 에이전트는 System Center Operations Manager 2012 및 System Center Operations Manager 2007 R2를 실행 하는 다른 에이전트를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d56-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

