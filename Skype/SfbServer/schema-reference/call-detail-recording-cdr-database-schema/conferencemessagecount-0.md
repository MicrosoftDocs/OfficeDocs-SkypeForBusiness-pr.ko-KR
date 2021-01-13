---
title: ConferenceMessageCount 보기
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813298"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="d0a6c-104">ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="d0a6c-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="d0a6c-105">ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="d0a6c-106">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0a6c-107">ConferenceMessageCount 보기에는 [ConferenceSessionDetails](conferencesessiondetails.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d0a6c-108">**열**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-108">**Column**</span></span>|<span data-ttu-id="d0a6c-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-109">**Data Type**</span></span>|<span data-ttu-id="d0a6c-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0a6c-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-111">**UserUri**</span></span> <br/> |<span data-ttu-id="d0a6c-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d0a6c-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d0a6c-113">메시지를 보낸 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="d0a6c-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="d0a6c-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d0a6c-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d0a6c-116">메시지를 보낸 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="d0a6c-117">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d0a6c-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="d0a6c-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d0a6c-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="d0a6c-120">메시지를 보낸 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="d0a6c-121">자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d0a6c-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="d0a6c-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="d0a6c-123">smallint</span><span class="sxs-lookup"><span data-stu-id="d0a6c-123">smallint</span></span>  <br/> |<span data-ttu-id="d0a6c-124">회의 세션 중 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

