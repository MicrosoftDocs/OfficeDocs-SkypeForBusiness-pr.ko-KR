---
title: 조직에 대한 외부 액세스 정책 관리
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
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
description: Edge 서버를 하나 이상 배포한 후에는 조직에 대해 지원할 유형의 외부 액세스를 사용하도록 설정해야 합니다.
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221662"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="62a7d-103">조직에 대한 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="62a7d-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="62a7d-104">Edge 서버를 하나 이상 배포한 후에는 조직에 대해 지원할 유형의 외부 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="62a7d-p101">조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 글로벌 정책이 만들어지지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="62a7d-109">**전역 정책**   Edge 서버를 배포할 때 전역 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="62a7d-110">기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="62a7d-111">전역 수준의 외부 사용자 액세스를 지원하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원하도록 전역 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="62a7d-112">전역 정책은 조직의 모든 사용자에게 적용되지만 사이트 정책 및 사용자 정책이 전역 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="62a7d-113">전역 정책을 삭제하는 경우에는 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="62a7d-114">대신, 기본 설정으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="62a7d-115">**사이트 정책**    하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스 지원을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="62a7d-116">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="62a7d-117">예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="62a7d-118">기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="62a7d-119">**사용자 정책**   하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스 지원을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="62a7d-120">사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="62a7d-121">예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="62a7d-122">사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="62a7d-123">한 정책 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="62a7d-124">비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="62a7d-125">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="62a7d-126">이러한 옵션에는 다음과 같은 유형의 외부 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="62a7d-127">**페더레이션 사용자와의 통신 사용**   페더레이션 파트너 도메인에 대한 사용자 액세스를 지원하려면 이 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="62a7d-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="62a7d-128">이 설정은 사용자가 다른 SIP 페더레이션 도메인과 통신 하는 기능과 Microsoft 365 또는 Office 365 같은 호스트 된 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="62a7d-129">**원격 사용자와의 통신 사용**   방화벽 외부에 있는 조직 사용자(예: 재택 근무자, 출장 중인 사용자)가 인터넷을 통해 Skype for Business Server에 연결할 수 있도록 하려면 이 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="62a7d-130">**공용 사용자와의 통신 사용**   내부 사용자가 공용 IM 공급자 연락처에서 제공된 연락처)와 통신할 수 있도록 하려면 이 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="62a7d-131">외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 조직에서 외부 사용자 액세스 사용을 제어하는 정책을 구성해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="62a7d-132">외부 사용자 액세스를위한 정책 작성, 구성 및 적용에 대한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안함](../access-edge/enable-or-disable-remote-user-access.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62a7d-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="62a7d-133">**Windows PowerShell cmdlet을 사용하여 외부 액세스 정책을 보려면**</span><span class="sxs-lookup"><span data-stu-id="62a7d-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="62a7d-134">비즈니스용 Skype 서버 관리 셸 및 **Get-CsExternalAccessPolicy** cmdlet을 사용하여 외부 액세스 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="62a7d-135">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="62a7d-136">모든 외부 액세스 정책에 대한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="62a7d-137">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="62a7d-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
