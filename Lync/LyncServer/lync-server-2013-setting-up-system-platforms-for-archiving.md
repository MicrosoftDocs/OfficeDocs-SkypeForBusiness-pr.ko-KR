---
title: 'Lync Server 2013: 보관용 시스템 플랫폼 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e1a8aea999fdf134b0152a9d37b2d36fc81ee8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="64e3f-102">Lync Server 2013에서 보관용 시스템 플랫폼 설정</span><span class="sxs-lookup"><span data-stu-id="64e3f-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64e3f-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="64e3f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="64e3f-104">보관 배포를 시작하기 전에 시스템 요구 사항을 충족하는 하드웨어에 필요한 운영 체제 및 기타 필수 구성 요소 소프트웨어를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="64e3f-105">**Lync server 2013 platform**   lync server 2013 배포에 보관 서버가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="64e3f-106">대신 통합 데이터 수집 에이전트가 프런트 엔드 서버 및 Standard Edition 서버에서 실행되어 보관할 데이터를 캡처하므로 보관을 호스팅하기 위해 별도로 필요한 시스템 플랫폼은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="64e3f-107">**데이터 저장소 플랫폼**   Lync Server 2013에서는 다음 중 하나를 사용 하 여 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="64e3f-108">**Microsoft exchange 통합**   exchange 2013 배포를 사용 하 여 Lync Server 2013 보관 데이터를 저장 하거나 보관 데이터를 저장 하기 위해 별도의 데이터베이스를 설정 하는 것이 아니라 exchange 배포에서 exchange 2013을 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="64e3f-109">Exchange 2013에 대 한 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64e3f-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="64e3f-110">**Sql server**   Microsoft Exchange 통합을 사용 하지 않고 대신 보관 데이터를 저장 하는 별도의 SQL server 데이터베이스를 사용 하려는 경우 보관을 배포 하기 전에 데이터베이스에 대 한 시스템 플랫폼을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="64e3f-111">특정 시스템 플랫폼 요구 사항은 보관 데이터베이스용으로 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012을 사용 하는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="64e3f-112">이러한 데이터베이스에 대 한 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Microsoft SQL Server 2008 R2 및 Microsoft SQL Server 2012 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64e3f-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="64e3f-113">**파일 서버 플랫폼**   lync server 2013에서는 프런트 엔드 서버 또는 Standard Edition 서버를 설정할 때 파일 저장소로 지정한 것과 동일한 위치에 lync server 보관 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="64e3f-114">보관 파일 저장용으로 별도의 위치를 지정할 수는 없으므로, 보관 파일 저장을 위해 별도의 시스템 플랫폼이 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="64e3f-115">Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 보관 된 Lync communications 파일은 해당 Exchange 서버에 있는 사용자에 대해 Exchange 2013 서버에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e3f-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

