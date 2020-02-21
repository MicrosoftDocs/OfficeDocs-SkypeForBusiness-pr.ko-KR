---
title: 'Lync Server 2013: 토폴로지 디자인 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452bd18d19fa61a0479ee8040361290b0b99d702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="a1fdd-102">Lync Server 2013에서 토폴로지 디자인 확인</span><span class="sxs-lookup"><span data-stu-id="a1fdd-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1fdd-103">_**마지막으로 수정 된 항목:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="a1fdd-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="a1fdd-104">토폴로지 작성기가 토폴로지를 자동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="a1fdd-105">모든 토폴로지 오류는 유효성 검사 오류로 식별 되며 서버 역할 옆에 유효성 검사 오류 아이콘으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="a1fdd-106">또한 토폴로지가 배포의 토폴로지를 올바르게 나타내는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="a1fdd-107">게시 전에 토폴로지를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a1fdd-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="a1fdd-108">모든 단순 URL이 올바르게 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="a1fdd-109">SQL Server 기반 서버가 온라인 상태이 고 필요한 방화벽 규칙을 포함 하 여 토폴로지 작성기가 설치 된 컴퓨터에서 해당 서버를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="a1fdd-110">파일 공유를 사용할 수 있으며 적절 한 사용 권한이 정의 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="a1fdd-111">배포 요구 사항을 충족하는 올바른 서버 역할이 토폴로지에 정의되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="a1fdd-112">Active Directory 도메인 서비스에 서버가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="a1fdd-113">서버를 도메인에 가입시킨 경우에는 이 확인이 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="a1fdd-114">토폴로지를 확인한 결과 유효성 검사 오류가 없으면 토폴로지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="a1fdd-115">유효성 검사 오류가 있는 경우에는 토폴로지를 게시하기 전에 먼저 오류를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="a1fdd-116">토폴로지를 게시 하는 방법에 대 한 자세한 내용은 [Publish the topology in The Lync Server 2013](lync-server-2013-publish-the-topology.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1fdd-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

