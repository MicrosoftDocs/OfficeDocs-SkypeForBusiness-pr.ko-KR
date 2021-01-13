---
title: 원격 사용자 액세스를 컨트롤하는 정책 구성
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 원격 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 구성합니다. 원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817303"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="23e61-104">비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어하는 정책 구성</span><span class="sxs-lookup"><span data-stu-id="23e61-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="23e61-105">원격 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="23e61-106">원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="23e61-107">사이트 정책은 글로벌 정책보다 우선 적용되며 사용자 정책은 사이트 정책 및 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="23e61-108">구성할 수 있는 정책 유형에 대한 자세한 내용은 비즈니스용 Skype 서버에 대한 외부 액세스 및 페더링 [관리를 참조하세요.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="23e61-109">한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="23e61-110">비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="23e61-111">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="23e61-112">조직에 대해 원격 사용자 액세스를 사용하도록 설정하지 않았더라도 원격 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="23e61-113">그러나 구성하는 정책은 조직에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="23e61-114">또한 원격 사용자 액세스를 제어하기 위한 사용자 정책을 지정하는 경우 해당 정책은 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있으며 정책을 사용하도록 구성된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="23e61-115">원격 위치에서 비즈니스용 Skype 서버에 로그인할 수 있는 사용자를 지정하는 데 대한 자세한 내용은 외부 사용자 액세스 정책 할당을 [참조하세요.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="23e61-116">원격 사용자 액세스를 제어하는 데 사용할 각 외부 액세스 정책을 구성하려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="23e61-117">이 절차에서는 원격 사용자와의 통신을 가능하게 하는 정책을 구성하는 방법에 대해서만 설명하지만, 원격 사용자 액세스를 지원하기 위해 구성하는 각 정책은 페더레이션 사용자 액세스 및 공용 사용자 액세스도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="23e61-118">페더링 사용자를 지원하도록 정책을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 페더링된 사용자 액세스를 제어하는 정책 [구성을 참조하세요.](configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="23e61-119">공용 사용자를 지원하기 위한 정책을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 조직의 SIP 페더링 공급자 [관리(Manage SIP federated providers)를 참조하세요.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="23e61-120">원격 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="23e61-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="23e61-121">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23e61-122">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="23e61-123">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="23e61-124">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="23e61-125">원격 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책, **편집** 을 차례로 클릭한 다음 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="23e61-p105">새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="23e61-p106">새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 에서 사용자 정책에서 다루는 내용을 나타내는 고유 이름을 **이름** 필드에 만듭니다(예: 원격 사용자에 대한 통신을 가능하게 하는 사용자 정책의 경우 **EnableRemoteUsers**).</span><span class="sxs-lookup"><span data-stu-id="23e61-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="23e61-130">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="23e61-131">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="23e61-132">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="23e61-133">정책에 대해 원격 사용자 액세스를 사용하도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="23e61-134">정책에 대해 원격 사용자 액세스를 사용하지 않도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="23e61-135">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-135">Click **Commit**.</span></span>

<span data-ttu-id="23e61-136">원격 사용자 액세스를 사용하도록 설정하려면 조직에서 원격 사용자 액세스에 대한 지원을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="23e61-137">자세한 내용은 페더ation 및 공용 IM 연결 사용 또는 사용 안 [하도록 설정 을 참조 합니다.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="23e61-138">사용자 정책의 경우에는 원격으로 연결할 수 있도록 하려는 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e61-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="23e61-139">자세한 내용은 외부 사용자 액세스 [정책 할당을 참조합니다.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="23e61-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
