---
title: 원격 사용자 액세스를 제어하도록 정책 구성
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 원격 사용자가 비즈니스용 Skype Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 원격 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818299"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="c4231-104">비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="c4231-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="c4231-105">원격 사용자가 비즈니스용 Skype Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="c4231-106">원격 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c4231-107">사이트 정책은 글로벌 정책 보다 우선 하며 사용자 정책은 사이트 및 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="c4231-108">구성할 수 있는 정책의 유형에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="c4231-109">한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c4231-110">비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="c4231-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c4231-111">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="c4231-112">조직의 원격 사용자 액세스를 사용 하도록 설정 하지 않은 경우에도 원격 사용자 액세스를 제어 하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="c4231-113">그러나 사용자가 구성한 정책은 조직에 대해 원격 사용자 액세스를 사용할 수 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="c4231-114">또한 원격 사용자 액세스를 제어 하는 사용자 정책을 지정 하면 비즈니스용 Skype Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="c4231-115">원격 위치에서 비즈니스용 Skype 서버에 로그인 할 수 있는 사용자를 지정 하는 방법에 대 한 자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="c4231-116">다음 절차를 사용 하 여 원격 사용자 액세스를 제어 하는 데 사용할 각 외부 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="c4231-117">이 절차에서는 원격 사용자와의 통신을 사용 하도록 정책을 구성 하는 방법에 대해 설명 하지만 원격 사용자 액세스를 지원 하도록 구성 하는 각 정책은 페더레이션된 사용자 액세스 및 공용 사용자 액세스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="c4231-118">페더레이션 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="c4231-119">공용 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 조직의 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="c4231-120">원격 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c4231-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="c4231-121">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c4231-122">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c4231-123">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c4231-124">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c4231-125">원격 사용자 액세스를 지원 하도록 전역 정책을 구성 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c4231-126">새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="c4231-127">**사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c4231-128">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c4231-129">**새 외부 액세스 정책**에서 사용자 정책이 적용 되는 항목을 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: remote users에 대 한 통신을 사용 하도록 설정 하는 사용자 정책에 대 한 **enableremoteusers** ).</span><span class="sxs-lookup"><span data-stu-id="c4231-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="c4231-130">기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c4231-131">) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c4231-132">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="c4231-133">정책에 대 한 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="c4231-134">정책에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="c4231-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-135">Click **Commit**.</span></span>

<span data-ttu-id="c4231-136">원격 사용자 액세스를 사용 하도록 설정 하려면 조직에서 원격 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="c4231-137">자세한 내용은 [페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="c4231-138">사용자 정책 인 경우 원격으로 연결할 수 있도록 하는 사용자에 게도 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4231-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="c4231-139">자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4231-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
