---
title: 비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '요약: 비즈니스용 Skype 서버에서 SIP trunks에 대 한 정보를 보는 방법에 대해 알아보세요.'
ms.openlocfilehash: f67fe998408b9c99311f1a86c35e08200de99431
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766931"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="93f0b-103">비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="93f0b-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="93f0b-104">**요약:** 비즈니스용 Skype 서버의 SIP trunks에 대 한 정보를 보는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="93f0b-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="93f0b-105">SIP trunks는 PSTN (공공 교환 전화 네트워크)과 함께 비즈니스용 Skype 서버와 Voice over IP 전화 네트워크를 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="93f0b-106">이전 버전의 제품에서 trunks는 중재 서버에서 PSTN 게이트웨이로 나가는 호출을 라우팅하는 데 사용 되었으며, 각 게이트웨이는 단일 트렁크로 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="93f0b-107">결과적으로 PSTN 게이트웨이와 SIP 트렁크는 본질적으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="93f0b-108">관리자는 연결 된 PSTN 게이트웨이에 대 한 정보를 보고 간단히 개별 SIP 트렁크에 대 한 정보를 볼 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="93f0b-109">그러나 비즈니스용 Skype Server에서는 이제 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks 더 이상 1이 아닌 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="93f0b-110">다시 말해, 관리자는 개별 SIP 트렁크에 대 한 정보를 볼 수 있도록 새 [CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="93f0b-111">모든 SIP trunks에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="93f0b-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="93f0b-112">다음 명령은 조직에서 사용 중인 모든 SIP trunks에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="93f0b-113">특정 SIP 트렁크에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="93f0b-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="93f0b-114">이 명령은 Id PstnGateway: 192.168.0.240와 함께 SIP 트렁크에 대 한 정보만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="93f0b-115">풀에 할당 된 모든 SIP trunks에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="93f0b-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="93f0b-116">이 예제에서는 풀 atl-cs-001.litwareinc.com에 할당 된 모든 SIP trunks에 대 한 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
