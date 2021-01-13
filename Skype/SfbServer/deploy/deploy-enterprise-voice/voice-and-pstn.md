---
title: 비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '요약: 비즈니스용 Skype 서버에서 음성 정책, PSTN 사용 레코드 및 음성 경로를 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830450"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="3424f-103">비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="3424f-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="3424f-104">**요약:** 비즈니스용 Skype 서버에서 음성 정책, PSTN 사용 레코드 및 음성 경로를 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3424f-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="3424f-p101">음성 정책, PSTN 사용 레코드 및 음성 경로는 완전하게 관련되어 있습니다. 음성 정책을 구성하려면 전화 걸기 기능 집합을 선택한 다음, PSTN 사용 현황 레코드 집합을 정책에 할당합니다. 그러면 음성 정책이 할당되는 사용자 또는 그룹에 대해 부여되는 권한을 지정합니다. 또한 음성 경로에도 PSTN 사용 레코드가 할당됩니다. 이 레코드는 경로 사용 권한이 부여된 사용자와 경로를 일치시키는 데 사용됩니다. 즉, 사용자는 일치하는 PSTN 사용 레코드를 가진 경로를 사용하는 전화만 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3424f-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="3424f-109">새 Enterprise Voice 배포에 권장되는 워크플로는, 먼저 해당하는 PSTN 사용 레코드를 포함하는 음성 정책을 구성한 다음 각 PSTN 사용 레코드에 적절한 경로를 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3424f-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3424f-110">사용자 범위를 사용하여 음성 정책을  *만들어*  개별 사용자 또는 그룹에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3424f-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="3424f-111">이러한 각 작업을 수행하는 자세한 단계는 이 섹션의 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3424f-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3424f-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3424f-112">In this section</span></span>

- [<span data-ttu-id="3424f-113">음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="3424f-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="3424f-114">비즈니스용 Skype에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="3424f-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="3424f-115">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="3424f-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="3424f-116">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3424f-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="3424f-117">비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="3424f-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="3424f-118">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="3424f-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

