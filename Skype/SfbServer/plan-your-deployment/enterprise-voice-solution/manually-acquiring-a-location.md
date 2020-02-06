---
title: 비즈니스용 Skype 서버에서 위치를 수동으로 가져오는 사용자 환경 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 비즈니스용 Skype Server Enterprise Voice에서 SIP 트렁크 공급자를 사용 하 여 E9-1 배포에서 로밍 사용자에 대 한 계획
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802718"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="c9d15-103">비즈니스용 Skype 서버에서 위치를 수동으로 가져오는 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c9d15-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="c9d15-104">비즈니스용 Skype Server Enterprise Voice에서 SIP 트렁크 공급자를 사용 하 여 E9-1 배포에서 로밍 사용자에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="c9d15-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c9d15-105">클라이언트가 네트워크 외부에 있거나 정의 되지 않은 서브넷에 있는 경우에는 사용자가 수동으로 위치를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-105">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="c9d15-106">그러나 비상 전화 중에는 먼저 국내/지역 E9-1-1-긴급 통화 응답 센터 (ECRC) 발송자에 게 전달 되기 전에 해당 통화가 공공 안전 응답 시점 (PSAP)으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-106">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="c9d15-107">ECRC는 호출자에 게 위치를 구두로 다음 제공 된 정보를 기반으로 해당 PSAP로 호출을 착신 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-107">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="c9d15-108">**위치 정보 서비스에서 자동으로 제공 되지 않는 위치를 입력 하 라는 메시지가 표시 되 게 하려면**</span><span class="sxs-lookup"><span data-stu-id="c9d15-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="c9d15-109">예를 들어 클라이언트가 정의 되지 않은 서브넷, 가정용, 호텔 또는 네트워크 외부의 모든 위치에 있는 경우 사용자가 위치를 입력 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="c9d15-110">위치 정책의 **위치** 설정을 구성 하 여 클라이언트 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="c9d15-111">이 값을 No로 설정 하면 사용자에 게 위치를 묻지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="c9d15-112">이 값을 예/y e s로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되지만 메시지가 해제 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="c9d15-113">이 값을 포기로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되 고, 프롬프트를 해제 하려고 할 때의 고 지 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="c9d15-114">모든 경우에 사용자는 평소 대로 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-114">In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="c9d15-115">사용자가 위치를 수동으로 입력 하는 경우 위치는 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소로 매핑되고 클라이언트에 있는 사용자별 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="c9d15-116">사용자가 이전에 저장 된 위치로 돌아갈 때 비즈니스용 Skype 클라이언트는 자동으로 해당 위치로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c9d15-117">클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자의 테이블에 저장 된 위치를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d15-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

