---
title: UserAgent 보기
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 보기에는 데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800018"
---
# <a name="useragent-view"></a><span data-ttu-id="20549-104">UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="20549-104">UserAgent view</span></span>
 
<span data-ttu-id="20549-105">UserAgent 보기에는 데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="20549-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="20549-106">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="20549-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="20549-107">**열**</span><span class="sxs-lookup"><span data-stu-id="20549-107">**Column**</span></span>|<span data-ttu-id="20549-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="20549-108">**Data Type**</span></span>|<span data-ttu-id="20549-109">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="20549-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20549-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="20549-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="20549-111">int</span><span class="sxs-lookup"><span data-stu-id="20549-111">int</span></span>  <br/> |<span data-ttu-id="20549-112">이 사용자 에이전트를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="20549-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="20549-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="20549-113">UserAgent</span></span>  <br/> |<span data-ttu-id="20549-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="20549-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="20549-115">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="20549-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="20549-116">UAType</span><span class="sxs-lookup"><span data-stu-id="20549-116">UAType</span></span>  <br/> |<span data-ttu-id="20549-117">smallint</span><span class="sxs-lookup"><span data-stu-id="20549-117">smallint</span></span>  <br/> |<span data-ttu-id="20549-118">사용자 에이전트의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="20549-118">Type of user agent.</span></span> <span data-ttu-id="20549-119">자세한 내용은 [UserAgent 테이블을](useragent.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="20549-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="20549-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="20549-120">UACategory</span></span>  <br/> |<span data-ttu-id="20549-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="20549-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="20549-p104">사용자가 속한 범주입니다. 예를 들어 사용자 에이전트 Conferencing_Attendant_1.0은 UACategory CAA에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20549-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

