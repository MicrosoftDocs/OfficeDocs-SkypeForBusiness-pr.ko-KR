---
title: 'Lync Server 2013: Lync Server에서 보관용 사용자 정책 설정'
description: 'Lync Server 2013: Lync Server에서 보관에 대 한 사용자 정책을 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e33abf6cf16c9c1367162aa8beee91874f4c725
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554084"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="72d1c-103">Lync Server 2013에서 보관용 사용자 정책 설정</span><span class="sxs-lookup"><span data-stu-id="72d1c-103">Setting up user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72d1c-104">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="72d1c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="72d1c-105">Lync Server 2013에 있는 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정 하려면 하나 이상의 사용자 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 적절 한 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-105">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="72d1c-106">사용자 정책은 사이트 및 전역 정책에 우선 하지만 Lync Server 2013에 있는 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-106">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="72d1c-107">사용자가 항상 Lync Server에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-107">Users are always homed in Lync Server.</span></span> <span data-ttu-id="72d1c-108">Microsoft Exchange 통합이 사용 하도록 설정 된 경우 사서함이 Microsoft Exchange Server 2013 인 사용자는 Lync Server의 보관 정책을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-108">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="72d1c-109">보관을 사용 하는 이러한 사용자는 Exchange In-Place 보류에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-109">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="72d1c-110">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72d1c-110">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72d1c-111">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 exchange 2013에 있는 사용자에 대해 보관이 사용 하도록 설정 되어 있는지 여부를 제어 In-Place 유지 정책에 따라 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-111">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="72d1c-112">이러한 사용자에 대 한 보관을 사용 하려면 사서함이 보류 In-Place에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-112">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="72d1c-113">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72d1c-113">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="72d1c-114">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d1c-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="72d1c-115">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72d1c-115">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72d1c-116">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="72d1c-116">In This Section</span></span>

  - [<span data-ttu-id="72d1c-117">Lync Server 2013에서 보관에 대 한 사용자 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="72d1c-117">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="72d1c-118">Lync Server 2013의 사용자에 게 Lync Server 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="72d1c-118">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

