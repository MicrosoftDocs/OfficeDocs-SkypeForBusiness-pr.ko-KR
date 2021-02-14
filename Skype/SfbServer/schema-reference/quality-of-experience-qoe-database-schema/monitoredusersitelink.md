---
title: MonitoredUserSiteLink 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 한 링크를 나타냅니다.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806358"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ae98e-104">MonitoredUserSiteLink 테이블</span><span class="sxs-lookup"><span data-stu-id="ae98e-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ae98e-p102">MonitoredUserSiteLink 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 한 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae98e-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ae98e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="ae98e-107">**Column**</span></span>|<span data-ttu-id="ae98e-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="ae98e-108">**Data Type**</span></span>|<span data-ttu-id="ae98e-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="ae98e-109">**Key/Index**</span></span>|<span data-ttu-id="ae98e-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="ae98e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae98e-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ae98e-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ae98e-112">int</span><span class="sxs-lookup"><span data-stu-id="ae98e-112">int</span></span>  <br/> |<span data-ttu-id="ae98e-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="ae98e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ae98e-114">[UserSite 테이블에서 참조됩니다.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="ae98e-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ae98e-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ae98e-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ae98e-116">int</span><span class="sxs-lookup"><span data-stu-id="ae98e-116">int</span></span>  <br/> |<span data-ttu-id="ae98e-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="ae98e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ae98e-118">[UserSite 테이블의 참조입니다.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="ae98e-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

