---
title: 'Lync Server 2013: 보관 및 모니터링 데이터베이스 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08eea156d1b12f607270ea3b6d7472519128e472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523175"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="064a6-102">Lync Server 2013에서 보관 및 모니터링 데이터베이스 백업</span><span class="sxs-lookup"><span data-stu-id="064a6-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="064a6-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="064a6-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="064a6-104">보관 또는 모니터링을 배포한 경우 조직의 SQL Server 백업 정책에 따라 이러한 데이터베이스를 백업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="064a6-105">보관 및 모니터링 설정은 중앙 관리 저장소를 백업할 때 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="064a6-106">자세한 내용은 <A href="lync-server-2013-backing-up-core-data-and-settings.md">Lync Server 2013의 핵심 데이터 및 설정 백업</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="064a6-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="064a6-107">보관 및 모니터링에 대해서는 SQL Server Management Studio와 같은 SQL Server 도구를 사용하여 수동 백업을 수행하거나 SQL Server 관리 도구를 사용하여 자동 정기 백업을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

