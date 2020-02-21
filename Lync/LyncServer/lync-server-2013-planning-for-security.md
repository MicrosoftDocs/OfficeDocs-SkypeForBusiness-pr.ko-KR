---
title: 'Lync Server 2013: 보안 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db9ec867032875484c6bab3db3c433716fa7c889
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="e6578-102">Lync Server 2013의 보안 계획</span><span class="sxs-lookup"><span data-stu-id="e6578-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6578-103">_**마지막으로 수정 된 항목:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="e6578-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="e6578-104">이 보안 섹션을 사용 하 여 Lync Server 2013의 배포에 대 한 보안 위험을 평가 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="e6578-105">Lync Server 2013 배포가 적당 하더라도 네트워크에 자체 보안 설명서가 있는 구성 요소가 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="e6578-106">따라서이 섹션에서는 배포와 관련 된 모든 구성 요소 및 영역에 대 한 보안의 모든 측면을 설명 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="e6578-107">이 섹션을 시작 하 여 Lync Server 2013 배포의 보안을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="e6578-108">가장 일반적인 보안 위험을 평가 하 고 관리 하기 위한 일반적인 지침과 모범 사례를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="e6578-109">각 항목의 끝부분에는 추가 제품 및 보안 리소스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6578-110">보안은 끊임없이 발전 하 고 있는 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="e6578-111">새로운 위협과 솔루션이 발생 하면 오래 된 문서, 솔루션, 메서드 및 절차를 최신 자료로 대체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6578-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e6578-112">In This Section</span></span>

  - [<span data-ttu-id="e6578-113">Lync Server 2013의 주요 보안 기능</span><span class="sxs-lookup"><span data-stu-id="e6578-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="e6578-114">현대의 일상적인 컴퓨팅의 일반적인 보안 위협</span><span class="sxs-lookup"><span data-stu-id="e6578-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="e6578-115">Lync Server 2013에 대 한 바이러스 백신 검사 제외</span><span class="sxs-lookup"><span data-stu-id="e6578-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="e6578-116">Lync Server 2013의 보안 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="e6578-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="e6578-117">Lync Server 2013의 핵심 인프라에 대 한 위협 요소 해결</span><span class="sxs-lookup"><span data-stu-id="e6578-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="e6578-118">Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포</span><span class="sxs-lookup"><span data-stu-id="e6578-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

