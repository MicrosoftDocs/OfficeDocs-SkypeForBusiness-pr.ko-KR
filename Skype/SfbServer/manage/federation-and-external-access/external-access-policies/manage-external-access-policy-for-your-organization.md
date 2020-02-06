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
description: 하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818279"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="7938d-103">조직에 대한 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="7938d-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="7938d-104">하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="7938d-105">기본적으로 조직에 대해 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 외부 사용자 액세스를 지원 하도록 구성 된 정책은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="7938d-106">외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="7938d-107">다음 정책 범위를 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="7938d-108">기본적으로 전역 정책은 만들어지지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="7938d-109">**전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="7938d-110">기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="7938d-111">전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="7938d-112">전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="7938d-113">전역 정책을 삭제 해도 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="7938d-114">대신 기본 설정으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="7938d-115">**사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="7938d-116">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="7938d-117">예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="7938d-118">기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="7938d-119">**사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="7938d-120">사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="7938d-121">예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="7938d-122">사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="7938d-123">하나의 정책 수준에서 적용 되는 정책 설정이 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7938d-124">비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="7938d-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7938d-125">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="7938d-126">이러한 옵션에는 다음과 같은 외부 액세스 유형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="7938d-127">**페더레이션 사용자**   와의 통신 사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="7938d-128">이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 통신 하는 기능 뿐만 아니라 Microsoft Office 365와 같은 호스트 공급자도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="7938d-129">**원격 사용자**   와 통신 설정 방화벽 외부에 있는 사용자 (예: 출장 중인 가정용 사용자)와 인터넷을 통해 비즈니스용 Skype 서버에 연결할 수 있도록 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="7938d-130">**공용 사용자**   와 통신 사용 내부 사용자가 공용 IM 공급자 연락처와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="7938d-131">외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 먼저 조직의 외부 사용자 액세스 사용을 제어 하는 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="7938d-132">외부 사용자 액세스에 대 한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](../access-edge/enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7938d-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="7938d-133">**Windows PowerShell cmdlet을 사용 하 여 외부 액세스 정책을 보려면**</span><span class="sxs-lookup"><span data-stu-id="7938d-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="7938d-134">비즈니스용 Skype Server Management Shell 및 **CsExternalAccessPolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="7938d-135">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="7938d-136">모든 외부 액세스 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="7938d-137">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7938d-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
