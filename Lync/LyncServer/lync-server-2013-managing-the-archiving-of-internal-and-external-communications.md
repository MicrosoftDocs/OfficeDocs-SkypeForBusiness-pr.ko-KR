---
title: 내부 및 외부 통신의 아카이빙 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="0ca22-102">Lync Server 2013의 내부 및 외부 통신 보관 관리</span><span class="sxs-lookup"><span data-stu-id="0ca22-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ca22-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0ca22-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0ca22-104">Lync Server 2013에서 Microsoft Exchange 통합을 사용 하지 않거나 해당 사서함이 있는 Exchange 2013에서 홈이 아닌 사용자가 있는 경우 보관 정책을 사용 하 여 내부 통신 및 외부 통신을 사용 하도록 설정 및 해제 합니다. 원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="0ca22-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0ca22-105">여기에는 다음과 같은 보관 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="0ca22-106">Lync Server 2013을 배포할 때 기본적으로 생성 되는 전역 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0ca22-107">특정 사이트 또는 사용자에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 사용자 수준 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="0ca22-108">보관 정책을 처음에 설정 했지만 배포 후에 정책을 변경, 추가, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="0ca22-109">Lync Server 2013 제어판에서 **보관 및 모니터링** 그룹의 **보관 정책** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 사용자 수준에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="0ca22-110">Lync Server 저장소를 Exchange 2013 저장소와 통합 하는 경우 Exchange 사용자 정책이 Lync Server 2013 보관 정책 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="0ca22-111">정책 계층 구조를 포함 하 여 정책이 구현 되는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ca22-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0ca22-112">보관 구현을 제어 하려면 IM 또는 회의 보관 여부, 중요 한 모드 사용, 제거 옵션 등의 보관 구성에 대 한 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="0ca22-113">기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="0ca22-114">보관 정책에서 내부 또는 외부 통신에 대 한 보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="0ca22-115">자세한 내용은 운영 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ca22-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="0ca22-116">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca22-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0ca22-117">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ca22-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ca22-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0ca22-118">In This Section</span></span>

  - [<span data-ttu-id="0ca22-119">특정 사이트 또는 사용자에 대 한 내부 또는 외부 통신의 보관을 사용 하거나 사용 하지 않도록 설정 하 여 Lync Server 2013에서 보관 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca22-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [<span data-ttu-id="0ca22-120">Lync Server 2013에서 보관 정책을 변경 하 여 조직, 사이트 또는 사용자에 대 한 내부 또는 외부 통신 보관을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0ca22-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [<span data-ttu-id="0ca22-121">Lync Server 2013에서 사용자에 게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="0ca22-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="0ca22-122">Exchange Server 통합을 사용 하는 경우 Lync Server 2013에서 보관할 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0ca22-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="0ca22-123">Lync Server 2013에서 보관 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="0ca22-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

