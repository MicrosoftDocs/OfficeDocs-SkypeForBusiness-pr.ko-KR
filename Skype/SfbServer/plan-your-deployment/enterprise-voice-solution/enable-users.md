---
title: 비즈니스용 Skype 서버에서 E9에 대 한 사용자 사용-1-1
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 사용 하는 사용자와 로밍 사용자 지원 방법을 비롯 하 여 비즈니스용 Skype Server Enterprise Voice의 E9-1 배포에 대 한 위치 정책에 필요한 사항입니다.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802958"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="f9c8f-103">비즈니스용 Skype 서버에서 E9에 대 한 사용자 사용-1-1</span><span class="sxs-lookup"><span data-stu-id="f9c8f-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="f9c8f-104">사용 하는 사용자와 로밍 사용자 지원 방법을 비롯 하 여 비즈니스용 Skype Server Enterprise Voice의 E9-1 배포에 대 한 위치 정책에 필요한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="f9c8f-105">클라이언트 등록 중 비즈니스용 Skype Server는 위치 정책을 사용 하 여 Enterprise Voice 사용이 가능한 사용자의 E9-1-1 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="f9c8f-106">이 정책에는 E9-1-1이 구현 되는 방법을 정의 하는 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="f9c8f-107">예를 들어 위치 정책에는 긴급 전화 접속 문자열, 위치 정보 서비스에서 자동으로 위치를 제공 하지 않는 경우 사용자가 수동으로 위치를 입력 해야 하는지 여부 등의 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="f9c8f-108">위치 정책에 대 한 전체 정의는 [비즈니스용 Skype 서버에 대 한 계획 위치 정책을](location-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="f9c8f-109">비즈니스용 Skype Server는 위치 정책을 서브넷 또는 전역, 사이트별 또는 사용자별 정책에 따라 클라이언트에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="f9c8f-110">사용자를 설정 하는 방법을 결정 하려면 먼저 다음 질문에 대답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="f9c8f-111">**모든 사용자를 설정 하거나 엔터프라이즈의 특정 지리적 영역에 대 한 지원을 제한할 계획 입니까?**</span><span class="sxs-lookup"><span data-stu-id="f9c8f-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="f9c8f-112">전역 위치 정책을 사용 하 여 엔터프라이즈의 모든 사용자에 게 위치를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="f9c8f-113">그러나 비즈니스용 Skype Server 네트워크 사이트에 위치 정책을 할당 한 다음 사이트에 서브넷을 추가 하 여 E9-1-1 지원을 엔터프라이즈 내의 선택 된 위치로 제한 하 고 사이트별로 E9-1 라우팅 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="f9c8f-114">**사용자 정책을 통해 개별 사용자를 사용할 계획 입니까?**</span><span class="sxs-lookup"><span data-stu-id="f9c8f-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="f9c8f-115">E9-1-1 지원을 사용자 지정 하려는 경우 특정 사용자 또는 공용 지역 전화 연락처 개체에 위치 정책을 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="f9c8f-116">**클라이언트가 네트워크 외부에서 로밍 하거나 정의 되지 않은 서브넷에서 연결 하는 경우 E9-1-1에 대해 클라이언트를 계속 사용할 수 있게 하려면**</span><span class="sxs-lookup"><span data-stu-id="f9c8f-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="f9c8f-117">사용자에 게 전역, 사이트 또는 사용자 단위 위치 정책을 할당 한 경우에는 클라이언트가 정의 된 서브넷 내에 없거나 위치 정보 서비스에 위치를 찾을 수 없는 경우 수동으로 클라이언트에 위치를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="f9c8f-118">자세한 내용은 [비즈니스용 Skype 서버에서 수동으로 위치를 가져오기 위한 사용자 환경 정의](manually-acquiring-a-location.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9c8f-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

