---
title: 미디어 우회 사용 및 사용 안 림
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서의 절차에 따라 비즈니스용 Skype 서버 제어판을 사용하여 미디어 우회를 활성화 또는 비활성화합니다.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816498"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="cbcb4-103">비즈니스용 Skype 서버에서 미디어 바이패스를 사용하도록 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="cbcb4-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="cbcb4-104">이 문서의 절차에 따라 비즈니스용 Skype 서버 제어판을 사용하여 미디어 우회를 활성화 또는 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="cbcb4-105">네트워크 미디어 우회 사용</span><span class="sxs-lookup"><span data-stu-id="cbcb4-105">Enable network media bypass</span></span> 

<span data-ttu-id="cbcb4-106">미디어 우회 설정은 비즈니스용 Skype 서버 배포에서 전역적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="cbcb4-107">미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="cbcb4-108">미디어 우회를 사용하는 경우에 대한 자세한 내용은 미디어 우회 계획 [을 참조합니다.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="cbcb4-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="cbcb4-109">비즈니스용 Skype 서버 제어판에서 미디어 우회를 사용하도록 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="cbcb4-110">미디어 바이패스를 사용하도록 설정 및 구성하려면</span><span class="sxs-lookup"><span data-stu-id="cbcb4-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="cbcb4-111">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cbcb4-112">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cbcb4-113">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 전역을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbcb4-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="cbcb4-p102">**전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="cbcb4-116">**편집** 메뉴에서 **자세히 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="cbcb4-117">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="cbcb4-118">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="cbcb4-119">**항상 우회**   모든 통화에서 미디어 우회를 시도하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="cbcb4-120">CAC(통화 가능 제어)를 사용하도록 설정한 경우 이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="cbcb4-121">CAC를 사용하도록 설정하지 않은 경우 다음 상황에서 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="cbcb4-122">대역폭을 제어할 필요가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="cbcb4-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="cbcb4-123">바이패스가 발생하는 시기를 확인하기 위해 세분화된 구성이 필요하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="cbcb4-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="cbcb4-124">게이트웨이와 클라이언트가 완전히 연결된 경우</span><span class="sxs-lookup"><span data-stu-id="cbcb4-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="cbcb4-125">**사이트 및 지역 구성 사용**   CAC를 사용하도록 설정하면 이 옵션이 기본적으로 선택되어 있으며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="cbcb4-126">이 옵션을 선택하면 네트워크 구성 사이트 및 지역이 미디어 바이패스가 가능한 때를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="cbcb4-127">이 옵션을 선택하면 매핑되지 않은 사이트에 바이패스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="cbcb4-128">대역폭 제약 조건이 없는 동일한 지역과 연결된 대규모 사이트가 하나 이상 있고(예: 대규모 중앙 사이트) 대역폭 제약 조건이 있는 동일한 지역과 연결된 분기 사이트도 몇 군데 있는 경우에만 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="cbcb4-129">매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면, 모든 서브넷이 모든 사이트와 연결되도록 지정할 필요 없이 서브넷이 분기 사이트와 연결되도록만 지정하면 되므로 구성이 능률적이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="cbcb4-130">CAC를 사용하도록 설정한 경우에는 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="cbcb4-131">**커밋** 을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="cbcb4-132">네트워크 미디어 우회를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="cbcb4-132">Disable network media bypass</span></span>

<span data-ttu-id="cbcb4-133">미디어 우회 설정은 비즈니스용 Skype 서버 배포에서 전역적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="cbcb4-134">미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="cbcb4-135">미디어 우회를 사용하는 경우에 대한 자세한 내용은 미디어 우회 계획 [을 참조합니다.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="cbcb4-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="cbcb4-136">비즈니스용 Skype 서버 제어판에서 미디어 우회를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="cbcb4-137">미디어 바이패스를 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="cbcb4-137">To disable media bypass</span></span>

1.  <span data-ttu-id="cbcb4-138">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cbcb4-139">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cbcb4-140">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 전역을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbcb4-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="cbcb4-p106">**전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="cbcb4-143">**편집** 메뉴에서 **자세히 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="cbcb4-144">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="cbcb4-145">**커밋** 을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcb4-145">Click **Commit** to save your changes.</span></span>

  
