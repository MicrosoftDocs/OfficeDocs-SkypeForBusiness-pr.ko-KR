---
title: Lync Server에서 보관에 대 한 사용자 정책 만들기 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f772119bac58f9ddd436289c8f1df210665d858d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="dc8af-102">Lync Server 2013에서 보관에 대 한 사용자 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="dc8af-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc8af-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="dc8af-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="dc8af-104">Lync Server에 있는 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정 하려면 먼저 사용자 정책을 만든 다음 하나 이상의 사용자 또는 사용자 그룹에 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="dc8af-105">특정 사용자 및 사용자 그룹에 사용자 정책을 적용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 사용자에 게 Lync Server 보관 정책 적용](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="dc8af-106">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="dc8af-107">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 해당 사서함을 원본 위치 유지 상태로 전환 하는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="dc8af-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="dc8af-109">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="dc8af-110">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="dc8af-111">Lync Server에 있는 사용자에 대 한 보관 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="dc8af-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="dc8af-112">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc8af-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="dc8af-114">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc8af-115">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="dc8af-116">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="dc8af-117">**새 보관 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="dc8af-118">**이름**에 사용자 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="dc8af-119">**설명**에서 사용자 정책에 대한 정보를 입력합니다(예: 법률 부서용 사용자 정책).</span><span class="sxs-lookup"><span data-stu-id="dc8af-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="dc8af-120">사용자 정책에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="dc8af-121">사용자 정책에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="dc8af-122">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-122">Click **Commit**.</span></span>

<span data-ttu-id="dc8af-123">사용자 정책은 해당 정책을 지정한 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc8af-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="dc8af-124">특정 사용자에 게 사용자 정책을 적용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 사용자에 게 Lync Server 보관 정책 적용](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc8af-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

