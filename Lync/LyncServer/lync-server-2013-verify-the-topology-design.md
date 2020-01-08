---
title: 'Lync Server 2013: 토폴로지 디자인 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="b8f0a-102">Lync Server 2013에서 토폴로지 디자인 확인</span><span class="sxs-lookup"><span data-stu-id="b8f0a-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f0a-103">_**마지막으로 수정한 주제:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="b8f0a-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="b8f0a-104">토폴로지 작성기는 토폴로지를 자동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="b8f0a-105">모든 토폴로지 오류는 유효성 검사 오류로 식별 되며 서버 역할 옆의 유효성 검사 오류 아이콘으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="b8f0a-106">또한 토폴로지가 배포에 대 한 토폴로지를 올바르게 나타내는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="b8f0a-107">게시 전에 토폴로지를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="b8f0a-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="b8f0a-108">모든 간단한 Url이 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="b8f0a-109">SQL Server 기반 서버가 온라인 상태 이며 필요한 방화벽 규칙을 포함 하 여 토폴로지 작성기가 설치 된 컴퓨터에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="b8f0a-110">파일 공유가 사용 가능 하며 적절 한 권한이 정의 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="b8f0a-111">배포 요구 사항에 맞는 올바른 서버 역할이 토폴로지에 정의 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="b8f0a-112">Active Directory 도메인 서비스에 서버가 존재 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="b8f0a-113">이 문제는 서버를 도메인에 조인한 경우 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="b8f0a-114">토폴로지를 확인 했 고 유효성 검사 오류가 없으면 토폴로지를 게시할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="b8f0a-115">유효성 검사 오류가 있는 경우 해당 오류를 수정 해야 토폴로지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="b8f0a-116">토폴로지 게시에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8f0a-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

