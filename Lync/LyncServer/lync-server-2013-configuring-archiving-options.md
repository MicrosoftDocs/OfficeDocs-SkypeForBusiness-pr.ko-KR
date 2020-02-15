---
title: 'Lync Server 2013: 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 243414dea5b7ca411e4511c3a82f269c9981147e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="a37b1-102">Lync Server 2013에서 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="a37b1-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37b1-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="a37b1-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="a37b1-104">Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 보관이 구현 되는 방식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="a37b1-105">여기에는 다음 보관 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="a37b1-106">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a37b1-107">보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a37b1-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="a37b1-108">보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="a37b1-109">Lync Server 2013 제어판에서는 **보관 및 모니터링** 그룹의 **보관 구성** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 풀 수준에서 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="a37b1-110">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a37b1-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="a37b1-111">배포 후 구성을 관리 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a37b1-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a37b1-112">보관을 사용 하려면 외부 통신을 위해 또는 Lync Server 2013에 있는 사용자에 대해 보관 정책을 사용 하도록 설정할지 여부를 지정 하는 보관 정책 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="a37b1-113">기본적으로 보관은 내부 또는 외부 통신 중 하나에 대해 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="a37b1-114">어느 정책에서든 보관을 사용하도록 설정하려면 이 섹션에 설명된 대로 먼저 배포 환경과 특정 사이트/풀(선택 사항)에 대해 적합한 보관 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="a37b1-115">보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a37b1-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a37b1-116">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에는 보관 정책을 구성 하 여 내부 통신, 외부 통신 또는 둘 모두에 대해 보관을 사용 하도록 설정할지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="a37b1-117">기본적으로 Lync Server 2013 보관 데이터베이스를 사용할 때 데이터를 보관 하기 위해 내부 또는 외부 통신에 대해 보관을 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="a37b1-118">정책에서 보관을 사용하도록 설정하기 전에 이 섹션에 설명된 대로 배포와 특정 사이트 및 풀(선택 사항)에 적합한 보관 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37b1-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="a37b1-119">Lync Server 2013 보관 데이터베이스에 대 한 보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a37b1-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a37b1-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a37b1-120">In This Section</span></span>

  - [<span data-ttu-id="a37b1-121">Lync Server 2013의 전역 수준에서 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="a37b1-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="a37b1-122">Lync Server 2013에서 사이트에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="a37b1-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="a37b1-123">Lync Server 2013의 풀에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="a37b1-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

