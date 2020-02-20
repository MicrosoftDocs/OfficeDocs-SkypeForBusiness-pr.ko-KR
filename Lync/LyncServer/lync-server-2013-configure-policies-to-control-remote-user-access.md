---
title: 'Lync Server 2013: 원격 사용자 액세스를 제어 하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429d1751f9b9628df98c05112838715de2b249d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="b5f1d-102">Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="b5f1d-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5f1d-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b5f1d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b5f1d-104">원격 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="b5f1d-105">원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="b5f1d-106">사이트 정책은 글로벌 정책보다 우선 적용되며 사용자 정책은 사이트 정책 및 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="b5f1d-107">구성할 수 있는 정책 유형에 대 한 자세한 내용은 [Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="b5f1d-108">한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b5f1d-109">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b5f1d-110">즉, 정책 설정이 정책이 영향을 주는 개체에 대해 자세히 설정 된다는 것을 의미 하며 개체에 대 한 영향을 더 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5f1d-111">조직에 대해 원격 사용자 액세스를 사용하도록 설정하지 않았더라도 원격 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="b5f1d-112">그러나 구성하는 정책은 조직에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="b5f1d-113">원격 사용자 액세스를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="b5f1d-114">또한 원격 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우이 정책은 Lync Server에 대해 사용 하도록 설정 되 고 정책을 사용 하도록 구성 된 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="b5f1d-115">원격 위치에서 Lync Server에 로그인 할 수 있는 사용자를 지정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b5f1d-116">원격 사용자 액세스를 제어하는 데 사용할 각 외부 액세스 정책을 구성하려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5f1d-117">이 절차에서는 원격 사용자와의 통신을 가능하게 하는 정책을 구성하는 방법에 대해서만 설명하지만, 원격 사용자 액세스를 지원하기 위해 구성하는 각 정책은 페더레이션 사용자 액세스 및 공용 사용자 액세스도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="b5f1d-118">페더레이션 사용자를 지원 하기 위한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="b5f1d-119">공용 사용자를 지원 하기 위한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="b5f1d-120">원격 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="b5f1d-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="b5f1d-121">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5f1d-122">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5f1d-123">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5f1d-124">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b5f1d-125">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b5f1d-126">원격 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책, **편집**을 차례로 클릭한 다음 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b5f1d-p105">새 사이트 정책을 만들려면 **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다. **사이트 선택**의 목록에서 적절한 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="b5f1d-p106">새 사용자 정책을 만들려면 **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다. **새 외부 액세스 정책**에서 사용자 정책에서 다루는 내용을 나타내는 고유 이름을 **이름** 필드에 만듭니다(예: 원격 사용자에 대한 통신을 가능하게 하는 사용자 정책의 경우 **EnableRemoteUsers**).</span><span class="sxs-lookup"><span data-stu-id="b5f1d-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="b5f1d-131">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b5f1d-132">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명**에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="b5f1d-133">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="b5f1d-134">정책에 대해 원격 사용자 액세스를 사용하도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="b5f1d-135">정책에 대해 원격 사용자 액세스를 사용하지 않도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="b5f1d-136">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-136">Click **Commit**.</span></span>

<span data-ttu-id="b5f1d-137">원격 사용자 액세스를 사용하도록 설정하려면 조직에서 원격 사용자 액세스에 대한 지원을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="b5f1d-138">자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="b5f1d-139">사용자 정책의 경우에는 원격으로 연결할 수 있도록 하려는 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="b5f1d-140">자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5f1d-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

