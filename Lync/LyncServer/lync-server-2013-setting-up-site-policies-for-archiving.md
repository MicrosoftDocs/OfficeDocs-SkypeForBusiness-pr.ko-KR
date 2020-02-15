---
title: 'Lync Server 2013: 보관용 사이트 정책 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fd9e63ad6aec440c090b4303a32cba37953e1d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b6435-102">Lync Server 2013에서 보관용 사이트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b6435-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6435-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b6435-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b6435-104">이러한 각 사이트에 대해 보관 정책을 만들고 구성 하 여 특정 사이트에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="b6435-105">사이트 정책은 전역 정책에 우선 하지만 사용자 정책은 사이트 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="b6435-106">보관 정책은 Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우에만 적용 되 고 Exchange 2013에 포함 되지 않고 사서함을 원본 위치 유지 상태로 설정 하는 일부 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="b6435-107">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 작업 설명서 [에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6435-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6435-108">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하 고 사서함을 원본 위치 유지 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b6435-109">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6435-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="b6435-110">보관 정책에서 내부 또는 외부 통신의 보관을 사용하도록 설정하기 전에 보관 구성에서 해당하는 모든 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="b6435-111">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6435-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="b6435-112">사이트에 대 한 보관 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b6435-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="b6435-113">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b6435-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="b6435-115">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="b6435-116">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 작업 설명서 [에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6435-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="b6435-117">**새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="b6435-118">**사이트 선택**에서 정책을 적용할 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="b6435-119">**새 보관 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="b6435-120">**이름**에 사이트 정책의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="b6435-121">**설명**에서 사이트 정책에 대 한 정보를 입력 합니다 (예: Redmond의 사이트 정책).</span><span class="sxs-lookup"><span data-stu-id="b6435-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="b6435-122">지정 된 사이트의 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="b6435-123">지정 된 사이트에 대 한 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="b6435-124">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6435-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

