---
title: 비즈니스용 Skype 서버의 Locations 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 각 레코드는 E9-1-1 통화와 같은 응급 통화에서 하나의 위치 참조를 나타냅니다.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821518"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7a312-103">비즈니스용 Skype 서버의 Locations 테이블</span><span class="sxs-lookup"><span data-stu-id="7a312-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7a312-104">각 레코드는 E9-1-1 통화와 같은 응급 통화에서 하나의 위치 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="7a312-105">**열**</span><span class="sxs-lookup"><span data-stu-id="7a312-105">**Column**</span></span>|<span data-ttu-id="7a312-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7a312-106">**Data Type**</span></span>|<span data-ttu-id="7a312-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7a312-107">**Key/Index**</span></span>|<span data-ttu-id="7a312-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="7a312-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a312-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="7a312-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="7a312-110">datetime</span><span class="sxs-lookup"><span data-stu-id="7a312-110">datetime</span></span>  <br/> |<span data-ttu-id="7a312-111">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="7a312-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7a312-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-112">Time of session request.</span></span> <span data-ttu-id="7a312-113">**SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="7a312-114">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a312-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7a312-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="7a312-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="7a312-116">int</span><span class="sxs-lookup"><span data-stu-id="7a312-116">int</span></span>  <br/> |<span data-ttu-id="7a312-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="7a312-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7a312-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-118">ID number to identify the session.</span></span> <span data-ttu-id="7a312-119">**SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="7a312-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a312-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7a312-121">**위치**</span><span class="sxs-lookup"><span data-stu-id="7a312-121">**Location**</span></span> <br/> |<span data-ttu-id="7a312-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="7a312-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="7a312-123">응급 통화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7a312-123">Location of emergency call.</span></span>  <br/> |
   

