---
title: 비즈니스용 Skype Server의 지점 사이트 SIP 트렁크
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 비즈니스용 Skype Server Enterprise Voice의 지사 사이트에서 SIP 트렁크에 대해 알아보세요.
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187794"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="d6073-103">비즈니스용 Skype Server의 지점 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="d6073-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="d6073-104">비즈니스용 Skype Server Enterprise Voice의 지사 사이트에서 SIP 트렁크에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d6073-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d6073-105">경우에 따라 선택한 지점 사이트에서 분산 SIP 트렁크을 구현 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="d6073-106">지점 사이트에 대 한 SIP 트렁크가 필요한 지 여부와 지점 사이트에서 SIP trunks를 배포 하기 위해 지원 되는 토폴로지 옵션에 대 한 자세한 내용은 [비즈니스용 Skype 서버의 sip 트렁크](sip-trunking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6073-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="d6073-107">예제 지점 사이트 SIP 트렁크 요구 사항 분석</span><span class="sxs-lookup"><span data-stu-id="d6073-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="d6073-108">지점 사이트의 SIP 트렁크를 배포 하기로 결정 한 경우 사이트별 비용 분석을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="d6073-109">예를 들어 Redmond, 워싱턴, 뉴욕에 있는 지사에 중앙 사이트가 있는 기업은 분석을 수행 하 여 뉴욕 사이트에서 로컬 서비스 공급자로 SIP 트렁크를 구현할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="d6073-110">뉴욕에 있는 분산 된 SIP 트렁크가 비용 효율적인 지 여부를 확인 하려면 직접 안쪽으로 거는 전화 접속 (예)에서 SIP 트렁크를 사용 하는 것을 확인 하 고 Redmond (425) 이외의 영역에 대해 뉴욕의 통화 수를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="d6073-111">중앙 사이트에서 지점 사이트를 종료 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="d6073-112">예를 들어 Redmond 중앙 사이트는 뉴욕 분기 사이트에 대 한 번호를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="d6073-113">분산 된 SIP 트렁크를 구현 하는 비용이 해당 통화 비용 보다 낮은 경우 뉴욕 지점 분기 사이트에서 SIP 트렁크를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="d6073-114">다른 지사 사이트 SIP 트렁크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6073-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="d6073-115">게이트웨이 대신 SIP 트렁크 배포 중에서 선택 하는 것은 각 옵션의 PSTN (공개 통신 네트워크) 시외 전화 요금 간의 차이를 기반으로 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="d6073-116">지점 사이트 SIP 트렁크를 배포 하는 경우에는 회복성 및 대역폭 요구 사항도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="d6073-117">지점 사이트와 중앙 사이트 간의 링크가 탄력적이 고 충분 한 대역폭을 보유 하 고 있는 경우 SIP 트렁크 또는 게이트웨이를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="d6073-118">지점 사이트에서 Survivable Branch 기기를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="d6073-119">지점 사이트와 중앙 사이트 간의 링크가 복원성이 없는 경우 Survivable Branch 기기를 배포 하거나 지점 사이트의 게이트웨이나 SIP 트렁크를 사용 하 여 Survivable Branch 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6073-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

