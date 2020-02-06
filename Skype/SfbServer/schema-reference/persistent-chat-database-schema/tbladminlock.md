---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 일부 관리자 명령을 실행 하는 데 필요한 관리자 잠금을 포함 합니다.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814696"
---
# <a name="tbladminlock"></a><span data-ttu-id="1b7be-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="1b7be-103">tblAdminLock</span></span>
 
<span data-ttu-id="1b7be-104">tblAdminLock 일부 관리자 명령을 실행 하는 데 필요한 관리자 잠금을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7be-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="1b7be-105">**열**</span><span class="sxs-lookup"><span data-stu-id="1b7be-105">**Columns**</span></span>

|<span data-ttu-id="1b7be-106">**열**</span><span class="sxs-lookup"><span data-stu-id="1b7be-106">**Column**</span></span>|<span data-ttu-id="1b7be-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="1b7be-107">**Type**</span></span>|<span data-ttu-id="1b7be-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="1b7be-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b7be-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="1b7be-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="1b7be-110">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="1b7be-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="1b7be-111">잠금 만료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7be-111">Lock expiration date and time.</span></span> <span data-ttu-id="1b7be-112">소유자는이 값을 정기적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7be-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="1b7be-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="1b7be-113">lockServerID</span></span>  <br/> |<span data-ttu-id="1b7be-114">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1b7be-114">int, not null</span></span>  <br/> |<span data-ttu-id="1b7be-115">잠금을 소유 하는 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7be-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="1b7be-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="1b7be-116">lockActorID</span></span>  <br/> |<span data-ttu-id="1b7be-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="1b7be-117">int, not null</span></span>  <br/> |<span data-ttu-id="1b7be-118">잠금을 소유 하는 주체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7be-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

