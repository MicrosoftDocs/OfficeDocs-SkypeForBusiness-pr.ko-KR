---
title: 'Lync Server 2013: 차단된 외부 도메인 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="ed123-102">Lync Server 2013에서 차단된 외부 도메인 지원 구성</span><span class="sxs-lookup"><span data-stu-id="ed123-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed123-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ed123-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ed123-104">페더레이션 파트너에 대 한 지원을 구성한 경우 조직과 페더레이션 할 때 차단 될 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="ed123-105">차단 된 도메인 목록은 차단 목록 (허용 되지 않는 명시적인 항목이 나열 됨)으로 작동 하며,이 옵션을 사용 하도록 설정한 경우 페더레이션 도메인 검색에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="ed123-106">자세한 내용은 [Lync Server 2013에서 페더레이션 파트너 검색 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed123-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="ed123-107">하나 이상의 외부 도메인이 조직에 연결 되지 않도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="ed123-108">이렇게 하려면 도메인을 차단 된 도메인 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="ed123-109">차단 된 도메인 목록에 외부 도메인을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ed123-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="ed123-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed123-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed123-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed123-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed123-113">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="ed123-114">**페더레이션 도메인**을 클릭 하 고 **새로 만들기**를 클릭 한 다음 **차단 된 도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="ed123-115">**새 페더레이션 도메인**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="ed123-116">**도메인 이름 (또는 FQDN)** 에 차단 하려는 페더레이션 파트너 도메인의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ed123-117">이름 길이가 256 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="ed123-118">페더레이션 파트너 도메인 이름에서 검색 하면 접미사 일치가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="ed123-119">예를 들어 <STRONG>contoso.com</STRONG>를 입력 하는 경우 검색 에서도 도메인 <STRONG>it.contoso.com</STRONG>반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="ed123-120">페더레이션 파트너 도메인은 동시에 차단 및 허용 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="ed123-121">Lync Server 2013에서이 문제가 발생 하 여 목록을 동기화 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="ed123-122">) **메모**에이 구성에 대해 다른 시스템 관리자와 공유 하려는 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="ed123-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="ed123-124">차단 하려는 각 페더레이션 파트너에 대해 4 ~ 6 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="ed123-125">페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직에서 페더레이션된 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="ed123-126">자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed123-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="ed123-127">또한 페더레이션 사용자와 공동 작업을 수행할 수 있는 사용자에 게 정책을 구성 하 고 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed123-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="ed123-128">자세한 내용은 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed123-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

