---
title: 'Lync Server 2013: 보관을 위한 전역 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="a68db-102">Lync Server 2013에서 보관할 글로벌 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a68db-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a68db-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a68db-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a68db-104">프런트 엔드 서버를 배포 하는 경우 Lync Server는 보관을 위한 전역 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="a68db-105">기본적으로 글로벌 정책에서는 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="a68db-106">전역 정책은 사이트 또는 사용자 정책을 설정 하거나, 전역 정책을 재정의 하거나, Microsoft Exchange 통합을 일부 또는 모두에 대해 사용 하는 경우가 아니면 전체 배포에 대해 보관을 사용할 수 있는지 여부를 제어 합니다. 사용자.</span><span class="sxs-lookup"><span data-stu-id="a68db-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="a68db-107">Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013에 속한 사용자에 게 전역 정책이 적용 되지 않으며 사서함이 원본 위치 유지에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="a68db-108">전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 운영 설명서 [에서 보관을 사용 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68db-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a68db-109">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a68db-110">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68db-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a68db-111">보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="a68db-112">자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013에서 보관 옵션 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68db-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="a68db-113">Lync Server 보관 데이터베이스를 사용할 때 보관할 전역 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="a68db-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="a68db-114">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a68db-115">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="a68db-116">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68db-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a68db-117">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="a68db-118">**보관 정책** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a68db-119">**보관 정책 편집-전역**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="a68db-120">**Name**에서 global의 기본 이름을 사용 하지 않으려면 전역 정책의 새 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="a68db-121">**설명**에서 정책에 대 한 정보를 제공 합니다 (예: *divisionName*의 글로벌 정책).</span><span class="sxs-lookup"><span data-stu-id="a68db-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="a68db-122">사이트 정책 또는 사용자 정책을 통해 구체적으로 제어 되지 않은 모든 사이트 및 사용자에 대 한 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="a68db-123">사이트 정책 또는 사용자 정책을 통해 구체적으로 제어 되지 않은 모든 사이트 및 사용자에 대해 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="a68db-124">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a68db-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

