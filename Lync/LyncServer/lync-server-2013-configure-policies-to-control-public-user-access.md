---
title: 'Lync Server 2013: 공용 사용자 액세스를 제어하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="800cb-102">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="800cb-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="800cb-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="800cb-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="800cb-104">공용 im (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 인터넷 서비스, Yahoo\!및 AOL의 Windows Live 네트워크를 포함 하 여 공용 메신저 서비스 공급자가 제공 하는 im 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="800cb-105">공용 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="800cb-106">공용 인스턴트 메시징 연결은 배포 및 사용자의 구성에 의존 하는 추가 된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="800cb-107">또한 공용 IM 공급자에서 서비스를 제공 하는 방법에 따라서도 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="800cb-108">공용 공급자를 사용 하도록 배포를 프로 비전 하는 방법에 대 한 자세한 내용은 "공용 IM 연결 가이드 Microsoft Lync Server, Office Communications Server 및 Live Communications Server" 가이드를 참조 하세요.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="800cb-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="800cb-109">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="800cb-110">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="800cb-111">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="800cb-112">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="800cb-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="800cb-113">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-113">has been announced.</span></span> <span data-ttu-id="800cb-114">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="800cb-115">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="800cb-116">받으려면.</span><span class="sxs-lookup"><span data-stu-id="800cb-116">Messenger.</span></span> <span data-ttu-id="800cb-117">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="800cb-118">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="800cb-119">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="800cb-120">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="800cb-121">Microsoft Lync Server 공용 IM 연결 프로 비전 사이트에 액세스 하려면 다음 링크를 사용 합니다.[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="800cb-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="800cb-122">공용 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="800cb-123">구성할 수 있는 정책의 유형에 대 한 자세한 내용은 배포 설명서 또는 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성을](lync-server-2013-configuring-support-for-external-user-access.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="800cb-124">하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="800cb-125">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="800cb-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="800cb-126">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="800cb-127">IM 초대의 경우 응답은 클라이언트 소프트웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="800cb-128">외부 보낸 사람이 사용자 구성 규칙 (즉, 사용자의 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단 되지 않는 한 요청이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="800cb-129">또한 사용자가 **허용** 목록에 없는 사용자의 모든 IM을 차단 하는 경우 메신저 대화 초대가 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="800cb-130">조직을 위해 페더레이션을 설정 하지 않은 경우에도 정책을 구성 하 여 공용 사용자 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="800cb-131">그러나 구성 하는 정책은 조직에 페더레이션이 설정 되어 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="800cb-132">페더레이션 사용에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="800cb-133">또한 공용 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우에는 Lync Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="800cb-134">Lync Server에 로그인 할 수 있는 공용 사용자를 지정 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013에서 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="800cb-135">하나 이상의 공용 IM 공급자 사용자가 액세스를 지원 하도록 정책을 구성 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="800cb-136">공용 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="800cb-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="800cb-137">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="800cb-138">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="800cb-139">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="800cb-140">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="800cb-141">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="800cb-142">전역 정책을 구성 하 여 공용 사용자 액세스를 지원 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="800cb-143">새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="800cb-144">**사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="800cb-145">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="800cb-146">**새 외부 액세스 정책**에서 사용자 정책에 대 한 설명 (예: 공용 사용자에 게 통신을 사용 하도록 설정 하는 사용자 정책에 대해 **public사용자** 를 지정 하는 경우)의 **이름** 필드에 고유한 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="800cb-147">기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="800cb-148">) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="800cb-149">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="800cb-150">정책에 대 한 공용 사용자 액세스를 사용 하도록 설정 하려면 **공용 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="800cb-151">정책에 대해 공용 사용자 액세스를 사용 하지 않도록 설정 하려면 **공용 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="800cb-152">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-152">Click **Commit**.</span></span>

<span data-ttu-id="800cb-153">공용 사용자 액세스를 사용 하도록 설정 하려면 조직의 페더레이션에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="800cb-154">자세한 내용은 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="800cb-155">사용자 정책 인 경우 공용 사용자와 공동 작업을 수행할 수 있는 공용 사용자에 게 정책만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800cb-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="800cb-156">자세한 내용은 [Lync Server 2013에서 사용자별 정책 지정](lync-server-2013-assigning-per-user-policies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800cb-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="800cb-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="800cb-157">See Also</span></span>


[<span data-ttu-id="800cb-158">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="800cb-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="800cb-159">Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="800cb-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

