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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815416"
---
# <a name="clientversions-view"></a><span data-ttu-id="175b9-105">ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="175b9-105">ClientVersions view</span></span>
 
<span data-ttu-id="175b9-106">ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="175b9-107">뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="175b9-108">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="175b9-109">특정 열에 여러 레코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="175b9-110">**열**</span><span class="sxs-lookup"><span data-stu-id="175b9-110">**Column**</span></span>|<span data-ttu-id="175b9-111">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="175b9-111">**Data Type**</span></span>|<span data-ttu-id="175b9-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="175b9-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="175b9-113">**#**</span><span class="sxs-lookup"><span data-stu-id="175b9-113">**VersionId**</span></span> <br/> |<span data-ttu-id="175b9-114">int</span><span class="sxs-lookup"><span data-stu-id="175b9-114">int</span></span>  <br/> |<span data-ttu-id="175b9-115">이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="175b9-116">**버전**</span><span class="sxs-lookup"><span data-stu-id="175b9-116">**Version**</span></span> <br/> |<span data-ttu-id="175b9-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="175b9-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="175b9-118">사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="175b9-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="175b9-119">**ClientType**</span></span> <br/> |<span data-ttu-id="175b9-120">int</span><span class="sxs-lookup"><span data-stu-id="175b9-120">int</span></span>  <br/> |<span data-ttu-id="175b9-121">클라이언트의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="175b9-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="175b9-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="175b9-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="175b9-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="175b9-124">클라이언트가 속한 범주</span><span class="sxs-lookup"><span data-stu-id="175b9-124">Category that the client belongs to.</span></span> <span data-ttu-id="175b9-125">예를 들어 클라이언트 Conferencing_Attendant_1 .0는 ClientCategory CA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="175b9-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

