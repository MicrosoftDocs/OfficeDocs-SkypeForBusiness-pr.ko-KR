---
title: ConferenceMessageCount 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 보기는 사용자가 회의에 보낸 메시지 수에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196786"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="aa44e-104">ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="aa44e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="aa44e-105">ConferenceMessageCount 보기는 사용자가 회의에 보낸 메시지 수에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="aa44e-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa44e-107">ConferenceMessageCount 보기에는 [ConferenceSessionDetails 보기](conferencesessiondetails.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="aa44e-108">**열**</span><span class="sxs-lookup"><span data-stu-id="aa44e-108">**Column**</span></span>|<span data-ttu-id="aa44e-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="aa44e-109">**Data Type**</span></span>|<span data-ttu-id="aa44e-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="aa44e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa44e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="aa44e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="aa44e-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa44e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aa44e-113">메시지를 보낸 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="aa44e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="aa44e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="aa44e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aa44e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aa44e-116">메시지를 보낸 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="aa44e-117">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa44e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa44e-118">**UserTenant 넌 트**</span><span class="sxs-lookup"><span data-stu-id="aa44e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="aa44e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="aa44e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="aa44e-120">메시지를 보낸 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="aa44e-121">자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa44e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa44e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="aa44e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="aa44e-123">smallint</span><span class="sxs-lookup"><span data-stu-id="aa44e-123">smallint</span></span>  <br/> |<span data-ttu-id="aa44e-124">회의 세션 동안 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa44e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

