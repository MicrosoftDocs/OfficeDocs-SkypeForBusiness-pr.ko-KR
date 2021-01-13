---
title: 비즈니스용 Skype 서버에서 네트워크 중간 정책 만들기
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 사이트 간 정책을 만들 수 있습니다.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822478"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="a4d35-103">비즈니스용 Skype 서버에서 네트워크 중간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a4d35-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="a4d35-104">비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 사이트 간 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="a4d35-105">네트워크 사이트 간 정책은 사이트 간에 직접 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a4d35-106">네트워크 사이트 간 정책은  두 네트워크 사이트 간에 직접 교차 링크가 있는 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="a4d35-107">북미 지역의 예 토폴로지에는 리노 사이트와 앨버커키 사이트가 직접 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="a4d35-108">이러한 두 사이트에는 적절한 대역폭 정책 프로필을 적용하는 사이트 간 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="a4d35-109">다음은 사용자 프로필을 20Mb_Link 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="a4d35-110">네트워크 사이트 간 정책을 만들 경우</span><span class="sxs-lookup"><span data-stu-id="a4d35-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="a4d35-111">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a4d35-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a4d35-112">New-CsNetworkInterSitePolicy cmdlet을 실행하여 네트워크 사이트 간 정책을 만들고 직접 상호 연결되는 두 사이트에 적절한 대역폭 정책 프로필을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="a4d35-113">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="a4d35-114">필요에 따라 2단계를 반복하여 직접 교차 링크가 있는 모든 네트워크 사이트 쌍에 대한 네트워크 사이트 간 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4d35-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a4d35-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4d35-115">See also</span></span>

[<span data-ttu-id="a4d35-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a4d35-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a4d35-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a4d35-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a4d35-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a4d35-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a4d35-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a4d35-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
