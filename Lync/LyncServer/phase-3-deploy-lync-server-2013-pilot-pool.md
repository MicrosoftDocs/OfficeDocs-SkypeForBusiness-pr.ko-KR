---
title: '3 단계: Lync Server 2013 파일럿 풀 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345fe1a110a4521fddde239681891a1491a17cca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="542b7-102">3 단계: Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="542b7-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="542b7-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="542b7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="542b7-104">이 섹션에서는 Lync Server 2013의 파일럿 풀을 배포 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="542b7-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="542b7-105">Lync Server 2013을 배포 하려면 토폴로지 작성기를 사용 하 여 배포 하려는 토폴로지와 구성 요소를 정의 하 고, Lync Server 2013 구성 요소를 배포 하기 위한 환경을 준비 하 고, 첫 번째 프런트 엔드에 토폴로지 디자인을 게시 해야 합니다. 서버를 선택한 다음 배포 구성 요소에 대 한 Lync Server 2013 소프트웨어를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="542b7-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="542b7-106">완료 되 면 Lync Server 2013 파일럿 풀 배포는 기존 Lync Server 2010 풀과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="542b7-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="542b7-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="542b7-107">In This Section</span></span>

  - [<span data-ttu-id="542b7-108">Lync Server에 대해 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="542b7-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="542b7-109">기존 배포에서 토폴로지 다운로드</span><span class="sxs-lookup"><span data-stu-id="542b7-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="542b7-110">Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="542b7-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="542b7-111">레거시 풀로 파일럿 풀 동시 사용 확인</span><span class="sxs-lookup"><span data-stu-id="542b7-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="542b7-112">레거시 에지 서버에 파일럿 풀 연결</span><span class="sxs-lookup"><span data-stu-id="542b7-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="542b7-113">XMPP 게이트웨이 액세스 정책 및 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="542b7-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

