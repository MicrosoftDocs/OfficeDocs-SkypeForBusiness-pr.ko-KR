---
title: 비즈니스용 Skype 서버에서 위치를 수동으로 다운로드하기 위한 사용자 환경 정의
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: SIP 트렁크 공급자를 사용하여 E9-1-1 배포의 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825428"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="905b1-103">비즈니스용 Skype 서버에서 위치를 수동으로 다운로드하기 위한 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="905b1-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="905b1-104">SIP 트렁크 공급자를 사용하여 E9-1-1 배포의 비즈니스용 Skype 서버 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="905b1-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="905b1-105">클라이언트가 네트워크 외부 또는 정의되지 않은 서브넷에 있는 경우 사용자는 위치를 수동으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-105">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="905b1-106">그러나 긴급 통화 중에는 통화가 PSAP(Public Safety Answering Point)로 라우팅되기 전에 먼저 ECRC(국가/지역 E9-1-1 긴급 통화 응답 센터) 디스패치로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-106">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="905b1-107">ECRC는 발신자에 위치를 구두로 쿼리한 다음 제공된 정보에 따라 통화를 적절한 PSAP로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-107">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="905b1-108">**위치 정보 서비스에서 위치를 자동으로 제공하지 않는 경우 사용자에게 위치를 입력하라는 메시지가 표시되어 있나요?**</span><span class="sxs-lookup"><span data-stu-id="905b1-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="905b1-109">예를 들어 클라이언트가 정의되지 않은 서브넷, 집, 장소 또는 네트워크 외부에 있는 경우 사용자가 위치를 입력해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="905b1-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="905b1-110">위치 정책에서 **위치** 필수 설정을 구성하여 클라이언트 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="905b1-111">이 값을 No로 설정하면 사용자에게 위치를 묻는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="905b1-112">이 값을 '예'로 설정하면 사용자에게 위치를 입력하라는 메시지가 표시되지만 메시지를 지우는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="905b1-113">이 값을 고지로 설정하면 사용자에게 위치를 묻는 메시지가 표시될 것이고 메시지를 삭제하려고 하면 고지 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="905b1-114">모든 경우에 사용자는 평소처럼 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-114">In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="905b1-115">사용자가 위치를 수동으로 입력하면 위치가 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소에 매핑되고 클라이언트에 있는 사용자 테이블에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="905b1-116">사용자가 이전에 저장한 위치로 돌아오면 비즈니스용 Skype 클라이언트가 자동으로 해당 위치로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="905b1-117">클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자 테이블에 저장된 위치를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="905b1-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

