---
title: 'Lync Server 2013: Lync Online 고객에 대 한 페더레이션 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e3b1e7a325a078d4769116697f957815f02487
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="e9007-102">Lync Server 2013에서 Lync Online 고객에 대 한 페더레이션 지원 구성</span><span class="sxs-lookup"><span data-stu-id="e9007-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9007-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e9007-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e9007-104">다음과 같은 방법으로 조직의 사용자에 게 통신 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="e9007-105">조직에서 Lync Server 2013 (온 *-프레미스 서비스*)을 배포 하 고 조직에서 lync 2013 사용자 계정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="e9007-106">호스팅 공급자를 사용 하 여 Microsoft Lync Online 2010 고객 계정을 설정 하 고 호스팅 공급자와 함께 사용자 계정을 설정 합니다 ( *온라인 서비스*라고 함).</span><span class="sxs-lookup"><span data-stu-id="e9007-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="e9007-107">조직에 Lync 2013을 배포 하는 경우 하나 이상의 Microsoft Lync Online 2010 고객의 도메인과 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="e9007-108">온-프레미스 Lync 2013 배포 사용자와 Lync Online 2010 고객 사용자 간 페더레이션을 사용 하도록 설정 하려면 Lync Online 고객의 도메인과 사용자에 대 한 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9007-109">이 문서에서는 Lync Online 2010 고객과의 페더레이션을 지원 하도록 조직을 구성 하는 절차만 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="e9007-110">이 문서에서는 페더레이션을 지원 하도록 Lync Online 2010 고객을 구성 하는 절차에 대해 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="e9007-111">Lync Online 서비스에 대 한 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>lync online을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9007-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9007-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e9007-112">In This Section</span></span>

  - [<span data-ttu-id="e9007-113">Lync Online 고객과 페더레이션 서버 2013의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e9007-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="e9007-114">Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성</span><span class="sxs-lookup"><span data-stu-id="e9007-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="e9007-115">Lync Online 고객과의 페더레이션에 대 한 사용자 액세스 구성 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9007-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="e9007-116">Lync Server 2013에서 Lync Online 고객과 통신을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9007-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

