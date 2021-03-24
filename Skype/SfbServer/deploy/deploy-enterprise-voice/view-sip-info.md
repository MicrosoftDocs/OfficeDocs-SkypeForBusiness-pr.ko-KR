---
title: 비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '요약: 비즈니스용 Skype 서버에서 SIP 트렁크에 대한 정보를 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103234"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="73132-103">비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="73132-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="73132-104">**요약:** 비즈니스용 Skype 서버에서 SIP 트렁크에 대한 정보를 보는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="73132-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="73132-105">SIP 트렁크는 Ip를 통해 비즈니스용 Skype 서버 음성 전화 네트워크를 PSTN(Public Switched Telephone Network)에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73132-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="73132-106">이전 버전의 제품에서는 트렁크를 사용하여 중재 서버에서 PSTN 게이트웨이로 아웃바운드 통화를 라우팅하고 각 게이트웨이는 단일 트렁크로 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73132-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="73132-107">따라서 PSTN 게이트웨이와 SIP 트렁크는 기본적으로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="73132-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="73132-108">관리자는 연결된 PSTN 게이트웨이에 대한 정보를 보기만 하여 개별 SIP 트렁크에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73132-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="73132-109">그러나 비즈니스용 Skype 서버에서는 이제 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 더 이상 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73132-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="73132-110">따라서 관리자는 개별 SIP 트렁크에 대한 정보를 보기 위해 새 [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet을 사용하여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73132-110">In turn, that means that administrators must use the new [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="73132-111">모든 SIP 트렁크에 대한 정보를 확인</span><span class="sxs-lookup"><span data-stu-id="73132-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="73132-112">다음 명령은 조직에서 사용 중이면 모든 SIP 트렁크에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73132-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="73132-113">특정 SIP 트렁크에 대한 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="73132-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="73132-114">이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73132-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="73132-115">풀에 할당된 모든 SIP 트렁크에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="73132-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="73132-116">이 예에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="73132-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```