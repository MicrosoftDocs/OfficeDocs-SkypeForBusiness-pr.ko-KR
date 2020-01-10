---
title: 비즈니스용 Skype 서버에서 통화 허용 제어 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 허용 제어 기능을 사용 하도록 설정 합니다.
ms.openlocfilehash: e88c0e87f9c920420ce2091ac2d75d04db6ca98f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002568"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="be891-103">비즈니스용 Skype 서버에서 통화 허용 제어 사용</span><span class="sxs-lookup"><span data-stu-id="be891-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="be891-104">비즈니스용 Skype Server Enterprise Voice에서 통화 허용 제어 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="be891-105">통화 허용 제어 배포에 대 한 네트워크 설정을 구성한 후에는 CAC를 사용 하도록 설정 하 여 대역폭 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="be891-106">비즈니스용 Skype Server Management Shell을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="be891-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="be891-107">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="be891-108">Set-csnetworkconfiguration cmdlet을 실행 하 여 네트워크에서 CAC를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-108">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network.</span></span> <span data-ttu-id="be891-109">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-109">For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="be891-110">네트워크에서 CAC를 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="be891-111">비즈니스용 Skype 서버 제어판을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="be891-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="be891-112">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be891-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="be891-113">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="be891-114">**전역** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="be891-115">목록에서 **전역** 을 클릭 한 다음 **편집** 메뉴에서 **세부 정보 표시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="be891-116">**전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="be891-117">배포 전체에서 통화 허용 제어를 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="be891-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be891-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="be891-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be891-119">See also</span></span>

[<span data-ttu-id="be891-120">Get-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="be891-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="be891-121">Set-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="be891-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="be891-122">제거-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="be891-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
