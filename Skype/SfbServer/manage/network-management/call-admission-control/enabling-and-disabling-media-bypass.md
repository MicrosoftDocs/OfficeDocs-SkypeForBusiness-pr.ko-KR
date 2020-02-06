---
title: 미디어 바이패스 사용 및 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서의 절차를 사용 하 여 비즈니스용 Skype 서버 제어판을 사용 하 여 미디어 바이패스를 사용 하거나 사용 하지 않도록 설정 합니다.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817547"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="0610b-103">비즈니스용 Skype 서버에서 미디어 바이패스를 사용하도록 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="0610b-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="0610b-104">이 문서의 절차를 사용 하 여 비즈니스용 Skype 서버 제어판을 사용 하 여 미디어 바이패스를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="0610b-105">네트워크 미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="0610b-105">Enable network media bypass</span></span> 

<span data-ttu-id="0610b-106">미디어 바이패스 설정은 비즈니스용 Skype 서버 배포 전체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="0610b-107">미디어 바이패스는 호출을 사용 하 여 중재 서버를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="0610b-108">미디어 바이패스 사용 방법에 대 한 자세한 내용은 [미디어 바이패스 계획](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0610b-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="0610b-109">비즈니스용 Skype 서버 제어판에서 미디어 바이패스를 사용 하도록 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="0610b-110">미디어 바이패스를 사용 하도록 설정 하 고 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="0610b-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="0610b-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0610b-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0610b-113">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **전역**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0610b-114">**전역** 페이지에서 **전역** 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="0610b-115">항상 하나의 구성만 있으며 항상 전역 이라는 이름으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="0610b-116">**편집** 메뉴에서 **세부 정보 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="0610b-117">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="0610b-118">다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="0610b-119">**항상 건너뛰기**   이 옵션을 선택 하 여 모든 통화에서 미디어를 우회 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="0610b-120">호출 허용 제어 (CAC)를 사용 하는 경우이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="0610b-121">CAC를 사용 하도록 설정 하지 않은 경우 다음과 같은 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="0610b-122">대역폭 제어는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="0610b-123">우회가 발생 하는 경우를 결정할 때는 세밀 한 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="0610b-124">게이트웨이와 클라이언트 간에는 완전 한 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="0610b-125">**사이트 및 지역 구성**   사용 CAC를 사용 하는 경우이 옵션은 기본적으로 선택 되어 있으며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="0610b-126">이 옵션을 선택 하면 네트워크 구성 사이트 및 지역이 미디어 바이패스 가능 여부를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="0610b-127">이 옵션을 선택 하면 매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="0610b-128">대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만 **매핑되지 않은 사이트에 사용 안 함** 확인란을 클릭 하 고 대역폭 제약 조건이 있는 동일한 지역에 연결 된 일부 지점 사이트를 보유 하 고 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="0610b-129">매핑되지 않은 사이트에 대 한 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정 하는 대신 지점 사이트와 연결 된 서브넷만 지정 하므로 구성이 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="0610b-130">CAC를 사용 하는 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="0610b-131">**커밋을** 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="0610b-132">네트워크 미디어 바이패스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0610b-132">Disable network media bypass</span></span>

<span data-ttu-id="0610b-133">미디어 바이패스 설정은 비즈니스용 Skype 서버 배포 전체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="0610b-134">미디어 바이패스는 호출을 사용 하 여 중재 서버를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="0610b-135">미디어 바이패스 사용 방법에 대 한 자세한 내용은 [미디어 바이패스 계획](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0610b-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="0610b-136">비즈니스용 Skype Server 제어판에서 미디어 바이패스를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="0610b-137">미디어 바이패스를 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="0610b-137">To disable media bypass</span></span>

1.  <span data-ttu-id="0610b-138">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0610b-139">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0610b-140">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **전역**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0610b-141">**전역** 페이지에서 **전역** 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="0610b-142">항상 하나의 구성만 있으며 항상 전역 이라는 이름으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="0610b-143">**편집** 메뉴에서 **세부 정보 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="0610b-144">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="0610b-145">**커밋을** 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0610b-145">Click **Commit** to save your changes.</span></span>

  
