---
title: 비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '요약: 비즈니스용 Skype 서버에서 음성 정책, PSTN 사용 레코드 및 음성 경로를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 5ce6b6b3e93804f648529043b9189110d25cbb08
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197149"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="d6134-103">비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="d6134-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="d6134-104">**요약:** 비즈니스용 Skype 서버에서 음성 정책, PSTN 사용 레코드, 음성 경로를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="d6134-105">음성 정책, PSTN 사용 레코드 및 음성 경로는 동맹 관계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-105">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="d6134-106">통화 기능 집합을 선택한 다음 정책을 할당 하 여 음성 정책을 할당 받은 사용자 또는 그룹에 대해 권한이 부여 된 권한을 지정 하는 PSTN 사용 레코드 집합을 설정 하 여 음성 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-106">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="d6134-107">또한 음성 경로에는 사용 하도록 승인 된 사용자와 경로를 일치 시키는 PSTN 사용 레코드도 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-107">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="d6134-108">즉, 사용자는 일치 하는 PSTN 사용 레코드가 있는 경로를 사용 하는 호출만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-108">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="d6134-109">새 엔터프라이즈 음성 배포의 권장 워크플로는 적절 한 PSTN 사용 레코드가 포함 된 음성 정책을 구성한 다음, 각 PSTN 사용 레코드에 적절 한 경로를 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d6134-110">*사용자* 범위를 사용 하 여 음성 정책을 만들어 개별 사용자 또는 그룹에 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6134-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="d6134-111">각 작업을 수행 하는 자세한 단계는이 섹션의 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6134-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d6134-112">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="d6134-112">In this section</span></span>

- [<span data-ttu-id="d6134-113">비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="d6134-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="d6134-114">비즈니스용 Skype에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="d6134-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="d6134-115">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="d6134-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="d6134-116">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d6134-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="d6134-117">비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6134-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="d6134-118">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="d6134-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

