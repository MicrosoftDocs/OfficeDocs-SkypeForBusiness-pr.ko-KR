---
title: 'Lync Server 2013: 보관 정책 구성 및 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f10de18f97bb8274514418b2cf478ccb03edd64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="880c2-102">Lync Server 2013에서 보관 정책 구성 및 할당</span><span class="sxs-lookup"><span data-stu-id="880c2-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="880c2-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="880c2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="880c2-104">Lync Server 2013에서는 정책을 사용 하 여 Lync Server 2013에 있는 사용자의 내부 통신 및 외부 통신에 대 한 보관을 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="880c2-105">여기에는 다음과 같은 보관 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="880c2-106">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="880c2-107">특정 사이트 또는 사용자에 대해 보관이 구현되는 방식을 지정하도록 만들어서 사용하는 선택적인 사이트 수준 및 사용자 수준 정책</span><span class="sxs-lookup"><span data-stu-id="880c2-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="880c2-108">보관을 배포할 때 처음으로 보관 정책을 설정하게 되며, 배포 후에 정책을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="880c2-109">Lync Server 2013 제어판에서는 **보관 및 모니터링** 그룹의 **보관 정책** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 사용자 수준에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="880c2-110">보관의 구현을 제어하려면 IM 또는 회의 보관 여부, 중요 모드 및 제거 옵션 사용 등의 옵션을 보관 구성에서 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="880c2-111">기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서 모든 옵션이 사용하도록 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="880c2-112">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="880c2-113">자세한 내용은 작업 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="880c2-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="880c2-114">Lync Server 저장소와 Exchange 2013 저장소를 통합 하는 경우 Exchange 사용자 정책은 Lync Server 2013 보관 정책 보다 우선 하지만 사서함이 원본 위치 유지 상태로 설정 된 Exchange 2013에 있는 사용자에 한 해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="880c2-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="880c2-115">정책 계층 구조를 포함 하 여 정책이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="880c2-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="880c2-116">배포 후 정책을 관리 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="880c2-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="880c2-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="880c2-117">In This Section</span></span>

  - [<span data-ttu-id="880c2-118">Lync Server 2013에서 보관에 대 한 글로벌 정책 구성</span><span class="sxs-lookup"><span data-stu-id="880c2-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="880c2-119">Lync Server 2013에서 보관용 사이트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="880c2-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="880c2-120">Lync Server 2013에서 사용자에 대 한 보관 정책 설정</span><span class="sxs-lookup"><span data-stu-id="880c2-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

