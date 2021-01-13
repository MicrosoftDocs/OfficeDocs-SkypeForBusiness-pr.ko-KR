---
title: CQD(통화 품질 대시보드)에 대한 사용자 설정 서비스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '요약: 통화 품질 대시보드용 리포지토리 API의 일부인 사용자 설정 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803039"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="10100-104">CQD(통화 품질 대시보드)에 대한 사용자 설정 서비스</span><span class="sxs-lookup"><span data-stu-id="10100-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="10100-105">**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 설정 서비스에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="10100-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="10100-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="10100-107">사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="10100-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="10100-108">사용자 설정 서비스</span><span class="sxs-lookup"><span data-stu-id="10100-108">User Settings Service</span></span>

<span data-ttu-id="10100-109">사용자 설정은 응용 프로그램이 사용자 기준 응용 프로그램 동작을 사용자 지정하는 등 다양한 목적으로 메타데이터를 저장하는 데 사용할 수 있는 키-값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="10100-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="10100-110">각 사용자는 사용자 설정에 대한 저장소를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="10100-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="10100-111">소유자만 사용자 설정을 추가, 수정 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="10100-112">**전역 설정**</span><span class="sxs-lookup"><span data-stu-id="10100-112">**Global Settings**</span></span>
  
<span data-ttu-id="10100-113">전역 설정은 시스템 사용자가 소유한 사용자 설정으로, 모든 사용자가 해당 설정에 대한 읽기 전용 액세스 권한을 습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="10100-114">전역 설정은 상수로, 리포지토리를 만들 때 만들어지며 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="10100-115">각 사용자는 동일한 키로 사용자 설정을 만들어 전역 설정을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="10100-116">응용 프로그램에서 유효 사용자 설정을 요청하면 API는 사용자 설정과 병합된 전역 설정 집합을 반환합니다. 각 사용자 설정은 키가 동일한 경우 각 전역 설정이 해당 전역 설정으로 바) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10100-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="10100-117">또한 API는 응용 프로그램에서 어떤 설정이 다시 정해진지 찾을 수 있도록 사용자 설정만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="10100-118">REST 작업은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10100-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="10100-119">**작업**</span><span class="sxs-lookup"><span data-stu-id="10100-119">**Operation**</span></span>|<span data-ttu-id="10100-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="10100-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="10100-121">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="10100-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="10100-122">사용자 설정으로 이동하면 지정된 사용자에 대한 설정 목록이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="10100-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="10100-123">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="10100-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="10100-124">사용자 설정에서 단일 사용자 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="10100-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

