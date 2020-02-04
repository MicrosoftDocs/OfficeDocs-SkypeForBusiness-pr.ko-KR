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
ms.openlocfilehash: 4092ddc3c86496053cc0ebbb367188490096de4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="936b7-102">Lync Server 2013에서 보관 및 모니터링 데이터베이스 백업</span><span class="sxs-lookup"><span data-stu-id="936b7-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="936b7-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="936b7-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="936b7-104">보관 또는 모니터링을 배포한 경우 조직의 SQL Server 백업 정책에 따라 이러한 데이터베이스를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936b7-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="936b7-105">보관 및 모니터링 설정은 중앙 관리 저장소를 백업할 때 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="936b7-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="936b7-106">자세한 내용은 <A href="lync-server-2013-backing-up-core-data-and-settings.md">Lync Server 2013의 핵심 데이터 및 설정 백업을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936b7-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="936b7-107">보관 및 모니터링을 위해 sql Server Management Studio와 같은 SQL Server 도구를 사용 하 여 수동 백업을 수행 하거나, SQL Server 관리 도구를 사용 하 여 정기 자동 백업을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936b7-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

