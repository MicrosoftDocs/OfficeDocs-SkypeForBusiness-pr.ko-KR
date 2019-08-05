---
title: MonitoredUserSiteLink 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196549"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="10d72-104">MonitoredUserSiteLink 테이블</span><span class="sxs-lookup"><span data-stu-id="10d72-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="10d72-105">MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="10d72-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="10d72-106">각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10d72-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="10d72-107">**열**</span><span class="sxs-lookup"><span data-stu-id="10d72-107">**Column**</span></span>|<span data-ttu-id="10d72-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="10d72-108">**Data Type**</span></span>|<span data-ttu-id="10d72-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="10d72-109">**Key/Index**</span></span>|<span data-ttu-id="10d72-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="10d72-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10d72-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="10d72-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="10d72-112">int</span><span class="sxs-lookup"><span data-stu-id="10d72-112">int</span></span>  <br/> |<span data-ttu-id="10d72-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="10d72-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="10d72-114">[Usersite 테이블](usersite.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d72-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="10d72-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="10d72-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="10d72-116">int</span><span class="sxs-lookup"><span data-stu-id="10d72-116">int</span></span>  <br/> |<span data-ttu-id="10d72-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="10d72-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="10d72-118">[Usersite 테이블](usersite.md)의 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="10d72-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

