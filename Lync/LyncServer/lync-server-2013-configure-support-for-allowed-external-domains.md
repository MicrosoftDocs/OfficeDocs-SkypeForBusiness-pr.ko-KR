---
title: 'Lync Server 2013: 허용 되는 외부 도메인에 대 한 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="b3d14-102">Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="b3d14-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d14-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b3d14-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b3d14-p101">페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 있는 특정 도메인을 관리할 수 있습니다. 하나 이상의 특정 외부 도메인을 허용된 페더레이션 도메인으로 구성합니다. 이렇게 하려면 각 도메인을 허용된 도메인 목록에 추가합니다. 조직에서 파트너 검색을 사용하는 경우에도 해당 도메인이 1,000명 이상의 사용자와 통신해야 하거나 초당 20개가 넘는 메시지를 보내야 할 수 있는 페더레이션 파트너인 경우에는 이와 같이 구성합니다. 조직에서 파트너 검색을 사용하지 않는 경우에는 허용된 도메인 목록에 추가하는 외부 도메인의 사용자만 조직 사용자와의 IM 및 회의에 참가할 수 있습니다. 페더레이션 도메인에 대한 액세스를 페더레이션 파트너의 액세스 에지 서비스를 실행하는 특정 서버로 제한하려면 허용된 도메인 목록의 각 도메인에 대해 액세스 에지 서비스를 실행하는 서버의 도메인 이름을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3d14-110">이 절차에서는 특정 도메인에 대한 지원을 구성하는 방법에 대해 설명하지만 페더레이션 사용자에 대한 지원을 구현하려면 조직에서 페더레이션 사용자를 지원하도록 설정하고 페더레이션 사용자와 공동 작업할 수 있는 사용자를 제어하는 정책을 구성하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="b3d14-111">페더레이션 사용자에 대 한 지원을 사용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d14-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="b3d14-112">페더레이션을 제어 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3d14-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="b3d14-113">허용 도메인 목록에 외부 도메인을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b3d14-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="b3d14-114">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3d14-115">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3d14-116">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3d14-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3d14-117">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭한 다음 **페더레이션 도메인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="b3d14-118">**페더레이션 도메인** 페이지에서 **새로 만들기**를 클릭한 다음 **허용 도메인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="b3d14-119">**새 페더레이션 도메인**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="b3d14-120">**도메인 이름 또는 FQDN**에 페더레이션 파트너 도메인의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b3d14-p104">이 이름은 고유해야 하며, 액세스 에지 서비스를 실행하는 이 서버의 기존 허용 도메인과 같을 수 없습니다. 이름은 256자까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="b3d14-p105">페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 <STRONG>contoso.com</STRONG>을 입력하면 <STRONG>it.contoso.com</STRONG> 도메인도 검색 결과에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="b3d14-125">페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="b3d14-126">Lync Server 2013에서는이를 방지 하 여 목록을 동기화 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="b3d14-127">이 페더레이션 도메인에 대한 액세스를 액세스 에지 서비스를 실행하는 특정 서버의 사용자로 제한하려면 **액세스 에지 서비스(FQDN)** 에 액세스 에지 서비스를 실행하는 페더레이션 도메인 서버의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="b3d14-128">추가 정보를 제공하려면 **설명**에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="b3d14-129">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="b3d14-130">허용할 각 페더레이션 파트너 도메인에 대해 4~6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="b3d14-131">페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="b3d14-132">자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d14-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="b3d14-133">또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d14-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="b3d14-134">자세한 내용은 [Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3d14-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

