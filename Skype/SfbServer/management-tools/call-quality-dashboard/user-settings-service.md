---
title: CQD (통화 품질 대시보드)에 대 한 사용자 설정 서비스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '요약: 통화 품질 대시보드의 리포지토리 API의 일부인 사용자 설정 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186849"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="cda23-104">CQD (통화 품질 대시보드)에 대 한 사용자 설정 서비스</span><span class="sxs-lookup"><span data-stu-id="cda23-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="cda23-105">**요약:** 통화 품질 대시보드의 리포지토리 API에 포함 된 사용자 설정 서비스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cda23-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cda23-107">사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="cda23-108">사용자 설정 서비스</span><span class="sxs-lookup"><span data-stu-id="cda23-108">User Settings Service</span></span>

<span data-ttu-id="cda23-109">사용자 설정은 응용 프로그램이 다양 한 용도에 대 한 메타 데이터를 저장 하는 데 사용할 수 있는 키-값 쌍으로, 사용자별 사용자 단위를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="cda23-110">각 사용자는 사용자 설정 저장소를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="cda23-111">소유자만 사용자 설정을 추가, 수정 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="cda23-112">**전역 설정**</span><span class="sxs-lookup"><span data-stu-id="cda23-112">**Global Settings**</span></span>
  
<span data-ttu-id="cda23-113">전역 설정은 시스템 사용자가 소유한 사용자 설정 이며, 모든 사용자는 읽기 전용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="cda23-114">전역 설정은 저장소를 만드는 동안 만들어지고 변경 되지 않는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="cda23-115">각 사용자는 동일한 키를 사용 하 여 사용자 설정을 만들어 전역 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="cda23-116">응용 프로그램이 유효한 사용자 설정을 요청할 때 API는 사용자 설정에 병합 된 전역 설정 집합을 반환 하 고, 각 사용자 설정이 각 전역 설정을 대체 합니다 (키가 동일한 경우).</span><span class="sxs-lookup"><span data-stu-id="cda23-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="cda23-117">또한 API는 응용 프로그램에서 재정의 되는 설정을 찾을 수 있도록 사용자 설정만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="cda23-118">미삭 작업은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="cda23-119">**작업**</span><span class="sxs-lookup"><span data-stu-id="cda23-119">**Operation**</span></span>|<span data-ttu-id="cda23-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="cda23-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cda23-121">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="cda23-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="cda23-122">사용자 설정 가져오기 지정 된 사용자에 대 한 설정 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="cda23-123">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="cda23-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="cda23-124">사용자 설정 가져오기 단일 사용자 설정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda23-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

