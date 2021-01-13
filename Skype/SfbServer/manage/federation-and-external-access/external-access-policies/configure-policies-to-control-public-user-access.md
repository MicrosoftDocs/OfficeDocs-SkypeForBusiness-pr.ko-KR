---
title: 공용 사용자 액세스를 컨트롤하는하는 정책 구성
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ublic IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 공용 IM 서비스 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823594"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="ba198-103">비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어하는 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ba198-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="ba198-104">공용 IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 공용 IM 서비스 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="ba198-105">공용 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="ba198-106">공용 인스턴트 메시징 연결은 배포 및 사용자 구성을 사용하는 추가된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="ba198-107">또한 공용 IM 공급자의 서비스 프로비전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="ba198-108">공용 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="ba198-109">한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ba198-110">비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ba198-111">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="ba198-p103">IM 초대의 경우 응답 여부는 클라이언트 소프트웨어에 따라 다릅니다. 사용자가 구성한 규칙(사용자 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단되는 경우가 아니면 요청이 수락됩니다. 또한 사용자가 자신의 **허용** 목록에 없는 사용자에 대해 모든 IM을 차단하도록 선택한 경우 IM 초대가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="ba198-115">조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 공용 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="ba198-116">그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="ba198-117">페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 [안 하도록 설정 을 참조합니다.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="ba198-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="ba198-118">또한 공용 사용자 액세스를 제어하는 사용자 정책을 지정하는 경우 해당 정책은 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있으며 정책을 사용하도록 구성된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="ba198-119">비즈니스용 Skype 서버에 로그인할 수 있는 공용 사용자를 지정하는 데 대한 자세한 내용은 외부 사용자 액세스 정책 할당을 [참조하세요.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="ba198-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="ba198-120">다음 절차에 따라 하나 이상의 공용 IM 공급자 사용자의 액세스를 지원하기 위한 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="ba198-121">공용 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ba198-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="ba198-122">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba198-123">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba198-124">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ba198-125">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ba198-126">공용 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="ba198-p105">새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="ba198-p106">새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 공용 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnablePublicUsers**).</span><span class="sxs-lookup"><span data-stu-id="ba198-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="ba198-131">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ba198-132">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="ba198-133">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="ba198-134">정책에 대한 공용 사용자 액세스를 사용하도록 설정하려면 **공용 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="ba198-135">정책에 대한 공용 사용자 액세스를 사용하지 않도록 설정하려면 **공용 사용자와의 통신 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="ba198-136">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-136">Click **Commit**.</span></span>

<span data-ttu-id="ba198-137">공용 사용자 액세스를 사용하도록 설정하려면 조직에서 페더레이션 지원도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="ba198-138">자세한 내용은 비즈니스용 Skype 서버에서 페더전된 사용자 액세스를 제어하는 [정책 구성을 참조하세요.](configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="ba198-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="ba198-139">사용자 정책의 경우에는 공용 사용자와 공동 작업하도록 할 공용 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba198-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ba198-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba198-140">See Also</span></span>

[<span data-ttu-id="ba198-141">조직의 SIP 페더레이션 제공자 관리</span><span class="sxs-lookup"><span data-stu-id="ba198-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
