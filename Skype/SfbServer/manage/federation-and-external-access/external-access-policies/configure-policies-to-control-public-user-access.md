---
title: 공용 사용자 액세스를 제어하도록 정책 구성
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ublic im (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 공용 IM 서비스 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있습니다.
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818309"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="b529d-103">비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="b529d-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="b529d-104">공용 인스턴트 메시징 (IM) 연결을 사용 하면 조직의 사용자가 공용 IM 서비스 공급자가 제공 하는 IM 서비스 사용자와 통신 하는 데 IM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="b529d-105">공용 사용자가 비즈니스용 Skype Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="b529d-106">공용 인스턴트 메시징 연결은 배포 및 사용자의 구성에 의존 하는 추가 된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="b529d-107">또한 공용 IM 공급자에서 서비스를 제공 하는 방법에 따라서도 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="b529d-108">공용 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="b529d-109">한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b529d-110">비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="b529d-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b529d-111">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="b529d-112">IM 초대의 경우 응답은 클라이언트 소프트웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-112">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="b529d-113">외부 보낸 사람이 사용자 구성 규칙 (즉, 사용자의 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단 되지 않는 한 요청이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-113">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="b529d-114">또한 사용자가 **허용** 목록에 없는 사용자의 모든 IM을 차단 하는 경우 메신저 대화 초대가 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-114">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="b529d-115">조직을 위해 페더레이션을 설정 하지 않은 경우에도 정책을 구성 하 여 공용 사용자 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="b529d-116">그러나 구성 하는 정책은 조직에 페더레이션이 설정 되어 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="b529d-117">페더레이션 사용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](../access-edge/enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b529d-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="b529d-118">또한 공용 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우 비즈니스용 Skype Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="b529d-119">비즈니스용 Skype Server에 로그인 할 수 있는 공용 사용자를 지정 하는 방법에 대 한 자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b529d-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="b529d-120">하나 이상의 공용 IM 공급자 사용자가 액세스를 지원 하도록 정책을 구성 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="b529d-121">공용 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b529d-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="b529d-122">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b529d-123">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b529d-124">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b529d-125">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b529d-126">전역 정책을 구성 하 여 공용 사용자 액세스를 지원 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b529d-127">새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="b529d-128">**사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="b529d-129">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b529d-130">**새 외부 액세스 정책**에서 사용자 정책에 대 한 설명 (예: 공용 사용자에 게 통신을 사용 하도록 설정 하는 사용자 정책에 대해 **public사용자** 를 지정 하는 경우)의 **이름** 필드에 고유한 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="b529d-131">기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b529d-132">) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="b529d-133">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="b529d-134">정책에 대 한 공용 사용자 액세스를 사용 하도록 설정 하려면 **공용 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="b529d-135">정책에 대해 공용 사용자 액세스를 사용 하지 않도록 설정 하려면 **공용 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="b529d-136">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-136">Click **Commit**.</span></span>

<span data-ttu-id="b529d-137">공용 사용자 액세스를 사용 하도록 설정 하려면 조직의 페더레이션에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="b529d-138">자세한 내용은 [비즈니스용 Skype 서버에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b529d-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="b529d-139">사용자 정책 인 경우 공용 사용자와 공동 작업을 수행할 수 있는 공용 사용자에 게 정책만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b529d-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b529d-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b529d-140">See Also</span></span>

[<span data-ttu-id="b529d-141">조직의 SIP 페더레이션 제공자 관리</span><span class="sxs-lookup"><span data-stu-id="b529d-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
