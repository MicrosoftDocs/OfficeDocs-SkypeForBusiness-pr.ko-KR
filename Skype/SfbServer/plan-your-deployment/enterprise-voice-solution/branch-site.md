---
title: 비즈니스용 Skype 서버의 분기 사이트 SIP 트렁크
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 비즈니스용 Skype 서버 2016의 분기 사이트에서 SIP 트렁크에 Enterprise Voice.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813718"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="c5415-103">비즈니스용 Skype 서버의 분기 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="c5415-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="c5415-104">비즈니스용 Skype 서버 2016의 분기 사이트에서 SIP 트렁크에 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c5415-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c5415-105">경우에 따라 선택한 분기 사이트에서 분산된 SIP 트렁크를 구현해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="c5415-106">분기 사이트에 SIP 트렁크가 필요한지 여부와 분기 사이트에 SIP 트렁크를 배포하기 위한 지원되는 토폴로지 옵션에 대한 자세한 내용은 비즈니스용 [Skype 서버에서 SIP](sip-trunking.md)트렁크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5415-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="c5415-107">예 분기 사이트 SIP 트렁크 요구 사항 분석</span><span class="sxs-lookup"><span data-stu-id="c5415-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="c5415-108">분기 사이트 SIP 트렁크를 배포하기로 결정한 경우 사이트별 비용 분석을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="c5415-109">예를 들어 워싱턴주 레드몬드에 중앙 사이트가 있는 기업과 뉴욕에 분기 사이트가 있는 기업은 분석을 수행하여 뉴욕 사이트에서 로컬 서비스 공급자로 SIP 트렁크를 구현할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="c5415-110">뉴욕에서 분산된 SIP 트렁크가 비용 효율적인지 여부를 확인하려면 SIP 트렁크가 사용되는 DID(내선 직접 호출) 번호를 식별하고 뉴욕에서 레드몬드(425)가 아닌 지역으로 전화를 건 횟수를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="c5415-111">중앙 사이트에서 분기 사이트에 대해 DID가 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="c5415-112">예를 들어 Redmond 중앙 사이트는 뉴욕 분기 사이트의 DID 번호를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="c5415-113">분산된 SIP 트렁크를 구현하는 데 드는 비용이 해당 호출 비용보다 적을 경우 뉴욕 분기 사이트에서 SIP 트렁크를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="c5415-114">기타 분기 사이트 SIP 트렁크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5415-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="c5415-115">게이트웨이 대신 SIP 트렁크 배포 선택은 각 옵션의 PSTN(Public Switched Telephone Network) 시거리 요금 간의 차이에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="c5415-116">분기 사이트 SIP 트렁크를 배포하는 경우 탄력성 및 대역폭 요구 사항도 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="c5415-117">분기 사이트와 중앙 사이트 간의 링크가 탄력적이며 대역폭이 충분하면 SIP 트렁크 또는 게이트웨이를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="c5415-118">분기 사이트에 Survivable Branch Appliance를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c5415-119">분기 사이트와 중앙 사이트 간의 링크가 탄력적이지 않은 경우 SIP 어플라이언스를 배포하거나 분기 사이트에 게이트웨이 또는 SIP 트렁크를 사용하여 SIP 서버를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c5415-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

