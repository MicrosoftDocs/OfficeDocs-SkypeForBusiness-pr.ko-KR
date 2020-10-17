---
title: 'Lync Server 2013: 디렉터에서 서비스 시작'
description: 'Lync Server 2013: 디렉터에서 서비스를 시작 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c134099fb328b8647ed7a9176987c06eeb8070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541814"
---
# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="65c54-103">Lync Server 2013의 디렉터에서 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="65c54-103">Start services on the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65c54-104">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="65c54-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="65c54-105">로컬 구성 저장소를 설치 하 고, Lync Server 구성 요소를 설치 하 고, 디렉터에 인증서를 구성한 후에는 서버에서 Lync Server 서비스를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-105">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="65c54-106">다음 절차에 따라 배포의 각 디렉터에서 서비스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-106">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="65c54-107">디렉터에서 서비스를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="65c54-107">To start services on a Director</span></span>

1.  <span data-ttu-id="65c54-108">Lync Server 배포 마법사의 **Lync server 2013** 페이지에서 **4 단계: 서비스 시작**옆에 있는 **실행** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-108">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="65c54-109">**서비스 시작** 페이지에서 **다음** 을 클릭 하 여 서버에서 Lync Server 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-109">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="65c54-110">**명령 실행** 페이지에서 모든 서비스가 정상적으로 시작되었으면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-110">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="65c54-111">**4단계: 서비스 시작** 아래의 **서비스 상태(선택 사항)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-111">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="65c54-112">서버의 MMC ( **서비스** Microsoft Management Console)에서 모든 Lync server 2013 서비스가 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c54-112">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

