---
title: 비즈니스용 Skype 서버에서 통화 가능 제어 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 비즈니스용 Skype 서버 2013에서 통화 Enterprise Voice.
ms.openlocfilehash: 2b8096a9223250cec88e57e68fdc201f5591fd92
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109864"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="2b535-103">비즈니스용 Skype 서버에서 통화 가능 제어 사용</span><span class="sxs-lookup"><span data-stu-id="2b535-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="2b535-104">비즈니스용 Skype 서버 2013에서 통화 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2b535-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="2b535-105">통화 허용 제어 배포에 대한 네트워크 설정을 구성한 후 CAC를 사용하도록 설정하여 대역폭 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2b535-106">비즈니스용 Skype 서버 관리 셸을 사용하여 통화 제어를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2b535-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="2b535-107">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2b535-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2b535-p101">Set-CsNetworkConfiguration cmdlet을 실행하여 네트워크에서 CAC를 사용하도록 설정합니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="2b535-110">네트워크에서 CAC를 사용하지 않도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2b535-111">비즈니스용 Skype 서버 제어판을 사용하여 통화 가능 제어를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2b535-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2b535-112">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="2b535-113">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="2b535-114">**전역** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="2b535-115">목록에서 **전역** 을 클릭한 다음 **편집** 메뉴에서 **세부 정보 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="2b535-116">**전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2b535-117">배포 전체에서 통화 허용 제어를 사용하지 않도록 설정하려면 이 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="2b535-118">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b535-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2b535-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b535-119">See also</span></span>

[<span data-ttu-id="2b535-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b535-120">Get-CsNetworkConfiguration</span></span>](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="2b535-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b535-121">Set-CsNetworkConfiguration</span></span>](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="2b535-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b535-122">Remove-CsNetworkConfiguration</span></span>](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)