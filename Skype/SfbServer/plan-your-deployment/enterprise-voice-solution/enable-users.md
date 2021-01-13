---
title: 비즈니스용 Skype 서버에서 사용자가 E9-1-1을 사용할 수 있도록 설정
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 비즈니스용 Skype 서버의 E9-1-1 배포에 대한 위치 정책에 Enterprise Voice 사용자 및 로밍 사용자를 지원하는 방법을 포함하여 결정됩니다.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825748"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="62b6d-103">비즈니스용 Skype 서버에서 사용자가 E9-1-1을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="62b6d-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="62b6d-104">비즈니스용 Skype 서버의 E9-1-1 배포에 대한 위치 정책에 Enterprise Voice 사용자 및 로밍 사용자를 지원하는 방법을 포함하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="62b6d-105">클라이언트를 등록하는 동안 비즈니스용 Skype 서버는 위치 정책을 사용하여 사용 가능한 사용자에 대해 E9-1-1 Enterprise Voice 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="62b6d-106">이 정책에는 E9-1-1 구현 방법을 정의하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="62b6d-107">예를 들어 위치 정책에는 긴급 전화 문자열과 같은 정보가 포함되고 위치 정보 서비스에서 위치를 자동으로 제공하지 않는 경우 사용자가 위치를 수동으로 입력해야 하는지 여부가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="62b6d-108">위치 정책의 전체 정의는 비즈니스용 Skype 서버의 위치 정책 [계획을 참조하세요.](location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="62b6d-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="62b6d-109">비즈니스용 Skype 서버는 서브넷을 기반으로 클라이언트 또는 전역, 사이트당 또는 사용자 정책에 따라 사용자에게 위치 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="62b6d-110">사용자를 설정하는 방법을 결정하기 위해서는 먼저 다음과 같은 질문을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="62b6d-111">**모든 사용자를 설정하시겠습니까? 아니면 해당 기업의 특정 영역으로만 지원을 제한하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="62b6d-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="62b6d-112">전역 위치 정책을 사용하여 기업 내 모든 사용자에게 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="62b6d-113">그러나 비즈니스용 Skype 서버 네트워크 사이트에 위치 정책을 할당한 다음 사이트에 서브넷을 추가하여 엔터프라이즈 내에서 선택한 위치로 E9-1-1 지원을 제한하고 사이트당 E9-1-1 라우팅 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="62b6d-114">**사용자 정책을 통해 개별 사용자를 설정할 계획이 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="62b6d-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="62b6d-115">E9-1-1 지원을 사용자 지정하려는 경우 특정 사용자 또는 공통 영역 전화 연락처 개체에 직접 위치 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="62b6d-116">**클라이언트가 네트워크 외부에서 로밍하거나 정의되지 않은 서브넷에서 연결할 경우에도 해당 클라이언트에 대해 E9-1-1을 설정해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="62b6d-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="62b6d-117">사용자에게 전역, 사이트 또는 사용자당 위치 정책이 할당된 경우 클라이언트가 정의된 서브넷 내에 있지 않은 경우 또는 위치 정보 서비스에서 위치를 찾을 수 없는 경우 클라이언트에 위치를 수동으로 입력해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b6d-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="62b6d-118">자세한 내용은 비즈니스용 Skype 서버에서 위치를 수동으로 다운로드하기 위한 사용자 환경 [정의를 참조하세요.](manually-acquiring-a-location.md)</span><span class="sxs-lookup"><span data-stu-id="62b6d-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

