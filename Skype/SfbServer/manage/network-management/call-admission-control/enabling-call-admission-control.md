---
title: 통화 입장 제어 사용
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
description: " CAC(통화 가능 제어) 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816508"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="1c94b-103">비즈니스용 Skype에서 통화 허용 컨트롤을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1c94b-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="1c94b-104">CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="1c94b-105">CAC 네트워크를 구성한 후에는 대역폭 제한을 적용할 수 있도록 CAC를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="1c94b-106">비즈니스용 Skype 서버 제어판을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="1c94b-107">비즈니스용 Skype 서버 제어판에서 CAC를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1c94b-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1c94b-108">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c94b-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1c94b-110">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 전역을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c94b-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="1c94b-111">**전역** 페이지에서 **전역** 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="1c94b-112">모든 비즈니스용 Skype 서버 배포에 대해 하나의 네트워크만 구성할 수 있으므로 목록에 네트워크 구성이 두 개 이상 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="1c94b-113">전역 구성은 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="1c94b-114">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1c94b-115">**전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택하고 **커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="1c94b-p103">**커밋** 을 클릭하면 구성 테스트가 실행됩니다. **전역 설정 편집** 대화 상자가 닫히고 **전역** 페이지로 돌아갑니다. 네트워크 구성에서 오류나 불일치 사항이 검색되어 구성이 제대로 작동하지 않는 경우(예: 모든 지역이 지역 간 경로를 통해 다른 모든 지역에 연결되어 있지 않은 경우)에는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="1c94b-p104">네트워크 구성을 변경하는 경우 전역 구성을 열고 **커밋** 을 클릭하여 유효성 검사를 실행할 수 있습니다. 먼저 CAC를 사용하지 않도록 설정할 필요는 없으며, 확인란을 선택한 대로 두고 **커밋** 을 클릭하면 됩니다. 구성을 변경하지 않아도 언제든지 이 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c94b-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c94b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c94b-122">See Also</span></span>

[<span data-ttu-id="1c94b-123">통화 수당 제어 계획</span><span class="sxs-lookup"><span data-stu-id="1c94b-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="1c94b-124">통화 허용 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="1c94b-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="1c94b-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1c94b-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="1c94b-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1c94b-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="1c94b-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1c94b-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
