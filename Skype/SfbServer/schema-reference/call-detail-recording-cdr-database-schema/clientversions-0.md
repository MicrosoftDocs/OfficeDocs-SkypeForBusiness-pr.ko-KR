---
title: ClientVersions 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196791"
---
# <a name="clientversions-view"></a><span data-ttu-id="6ae8c-105">ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="6ae8c-105">ClientVersions view</span></span>
 
<span data-ttu-id="6ae8c-106">ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="6ae8c-107">뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="6ae8c-108">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ae8c-109">특정 열에 여러 레코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="6ae8c-110">**열**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-110">**Column**</span></span>|<span data-ttu-id="6ae8c-111">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-111">**Data Type**</span></span>|<span data-ttu-id="6ae8c-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ae8c-113">**#**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-113">**VersionId**</span></span> <br/> |<span data-ttu-id="6ae8c-114">int</span><span class="sxs-lookup"><span data-stu-id="6ae8c-114">int</span></span>  <br/> |<span data-ttu-id="6ae8c-115">이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="6ae8c-116">**버전**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-116">**Version**</span></span> <br/> |<span data-ttu-id="6ae8c-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6ae8c-118">사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="6ae8c-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-119">**ClientType**</span></span> <br/> |<span data-ttu-id="6ae8c-120">int</span><span class="sxs-lookup"><span data-stu-id="6ae8c-120">int</span></span>  <br/> |<span data-ttu-id="6ae8c-121">클라이언트의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="6ae8c-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="6ae8c-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="6ae8c-124">클라이언트가 속한 범주</span><span class="sxs-lookup"><span data-stu-id="6ae8c-124">Category that the client belongs to.</span></span> <span data-ttu-id="6ae8c-125">예를 들어 클라이언트 Conferencing_Attendant_ 1.0은 ClientCategory CA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

