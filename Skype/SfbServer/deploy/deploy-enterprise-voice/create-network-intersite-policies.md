---
title: 비즈니스용 Skype 서버에서 네트워크 사이트 간 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 정책 만들기
ms.openlocfilehash: f24d0ad289d9388c45a5dbd9a31aa60e8c41e357
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767921"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="4a890-103">비즈니스용 Skype 서버에서 네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4a890-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="4a890-104">비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4a890-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="4a890-105">네트워크 사이트 간 정책은 서로 직접적인 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4a890-106">네트워크 간 정책은 두 네트워크 사이트 간에 직접 상호 연결 된 경우에 *만* 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="4a890-107">예제 토폴로지 지역에는 Reno 및 Albuquerque 사이트 간의 직접적인 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="4a890-108">이러한 두 사이트에는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="4a890-109">다음 예제에서는 20Mb_Link 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="4a890-110">네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4a890-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="4a890-111">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4a890-112">CsNetworkInterSitePolicy cmdlet을 실행 하 여 네트워크 간 정책을 만들고 직접 교차 링크가 있는 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="4a890-113">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="4a890-114">필요에 따라 2 단계를 반복 하 여 직접 상호 연결 된 모든 네트워크 사이트 쌍에 대 한 네트워크 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a890-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4a890-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a890-115">See also</span></span>

[<span data-ttu-id="4a890-116">새로운 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4a890-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4a890-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4a890-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4a890-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4a890-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4a890-119">제거-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4a890-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
