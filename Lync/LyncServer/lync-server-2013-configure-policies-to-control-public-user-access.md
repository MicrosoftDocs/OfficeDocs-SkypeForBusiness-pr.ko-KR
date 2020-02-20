---
title: 'Lync Server 2013: 공용 사용자 액세스를 제어 하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a6e5d94cef7c9f25bb1c4091a981603f66da82
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="f3780-102">Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f3780-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3780-103">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f3780-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f3780-104">공용 im (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 인터넷 서비스, Yahoo\!및 AOL의 Windows Live 네트워크를 포함 하 여 공용 메신저 서비스 공급자가 제공 하는 im 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="f3780-105">공용 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="f3780-106">공용 인스턴트 메시징 연결은 배포 및 사용자의 구성을 기반으로 하는 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="f3780-107">또한 공용 IM 공급자에서 서비스를 프로 비전 하는 방법에 따라서도 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="f3780-108">공용 공급자를 사용 하도록 배포를 구축 하는 방법에 대 한 자세한 내용은 "공용 IM 연결 구축 가이드 for Microsoft Lync Server, Office Communications Server 및 Live Communications Server" 가이드를 참조 하십시오.[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="f3780-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f3780-109">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f3780-110">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f3780-111">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="f3780-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="f3780-112">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="f3780-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f3780-113">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-113">has been announced.</span></span> <span data-ttu-id="f3780-114">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3780-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f3780-115">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f3780-116">메신저로.</span><span class="sxs-lookup"><span data-stu-id="f3780-116">Messenger.</span></span> <span data-ttu-id="f3780-117">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f3780-118">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f3780-119">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f3780-120">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f3780-121">Microsoft Lync Server 공용 IM 연결 프로 비전 사이트에 액세스 하려면 다음 링크를 사용 합니다.[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="f3780-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="f3780-122">공용 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="f3780-123">구성할 수 있는 정책 유형에 대 한 자세한 내용은 배포 설명서 또는 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스에 대 한 지원 구성을](lync-server-2013-configuring-support-for-external-user-access.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3780-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="f3780-124">한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f3780-125">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f3780-126">즉, 정책 설정이 정책이 영향을 주는 개체에 대해 자세히 설정 된다는 것을 의미 하며 개체에 대 한 영향을 더 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="f3780-p106">IM 초대의 경우 응답 여부는 클라이언트 소프트웨어에 따라 다릅니다. 사용자가 구성한 규칙(사용자 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단되는 경우가 아니면 요청이 수락됩니다. 또한 사용자가 자신의 **허용** 목록에 없는 사용자에 대해 모든 IM을 차단하도록 선택한 경우 IM 초대가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3780-130">조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 공용 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="f3780-131">그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="f3780-132">페더레이션을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서에서 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013의 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3780-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="f3780-133">또한 공용 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우이 정책은 Lync Server에 대해 사용 하도록 설정 되 고 정책을 사용 하도록 구성 된 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="f3780-134">Lync Server에 로그인 할 수 있는 공용 사용자를 지정 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서에서 lync <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3780-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="f3780-135">다음 절차에 따라 하나 이상의 공용 IM 공급자 사용자의 액세스를 지원하기 위한 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="f3780-136">공용 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="f3780-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="f3780-137">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3780-138">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3780-139">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3780-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3780-140">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f3780-141">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f3780-142">공용 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="f3780-p109">새 사이트 정책을 만들려면 **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다. **사이트 선택**의 목록에서 적절한 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="f3780-p110">새 사용자 정책을 만들려면 **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다. **새 외부 액세스 정책**의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 공용 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnablePublicUsers**).</span><span class="sxs-lookup"><span data-stu-id="f3780-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="f3780-147">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f3780-148">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명**에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="f3780-149">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="f3780-150">정책에 대한 공용 사용자 액세스를 사용하도록 설정하려면 **공용 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="f3780-151">정책에 대한 공용 사용자 액세스를 사용하지 않도록 설정하려면 **공용 사용자와의 통신 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="f3780-152">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-152">Click **Commit**.</span></span>

<span data-ttu-id="f3780-153">공용 사용자 액세스를 사용하도록 설정하려면 조직에서 페더레이션 지원도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="f3780-154">자세한 내용은 [Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3780-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="f3780-155">사용자 정책의 경우에는 공용 사용자와 공동 작업하도록 할 공용 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3780-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="f3780-156">자세한 내용은 [Lync Server 2013에서 사용자별 정책 할당](lync-server-2013-assigning-per-user-policies.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3780-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3780-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3780-157">See Also</span></span>


[<span data-ttu-id="f3780-158">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="f3780-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="f3780-159">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="f3780-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

