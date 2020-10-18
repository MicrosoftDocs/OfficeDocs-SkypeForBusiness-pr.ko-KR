---
title: 'Lync Server 2013: 프런트 엔드 서버 및 프런트 엔드 풀 설정'
description: 'Lync Server 2013: 프런트 엔드 서버 및 프런트 엔드 풀을 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d746bf342f6937c068e32caddd484b708a123910
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577244"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="6e80b-103">Lync Server 2013에 대 한 프런트 엔드 서버 및 프런트 엔드 풀 설정</span><span class="sxs-lookup"><span data-stu-id="6e80b-103">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e80b-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6e80b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6e80b-105">이 섹션에서는 Lync Server 2013을 설치 하는 과정을 안내 하 고 프런트 엔드 서버 및 프런트 엔드 서버와 배치 된 되는 모든 서버 역할을 포함 하 여 Standard Edition server 및 프론트 엔드 풀에 대 한 서버 역할을 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e80b-105">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="6e80b-106">서버 역할을 설치 하 고 설정 하려면 서버 역할을 설치 하는 각 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e80b-106">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="6e80b-107">배포 마법사를 사용 하 여 로컬 구성 저장소 설치, 프런트 엔드 서버 설치, 인증서 구성, 서비스 시작 등 네 가지 배포 단계를 모두 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e80b-107">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e80b-108">서버 역할을 설정하기 전에 토폴로지를 제대로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e80b-108">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="6e80b-109">토폴로지를 게시 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Lync Server 2013에서 토폴로지 디자인 마무리 및 구현을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e80b-109">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e80b-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6e80b-110">In This Section</span></span>

  - [<span data-ttu-id="6e80b-111">Lync Server 2013에서 로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="6e80b-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="6e80b-112">Lync Server 2013 용 서버 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="6e80b-112">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="6e80b-113">Lync Server 2013에서 서버에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="6e80b-113">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="6e80b-114">Lync Server 2013의 서버에서 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="6e80b-114">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="6e80b-115">Lync Server 2013에서 풀 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="6e80b-115">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="6e80b-116">Lync Server 2013에서 Standard Edition server 테스트</span><span class="sxs-lookup"><span data-stu-id="6e80b-116">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

