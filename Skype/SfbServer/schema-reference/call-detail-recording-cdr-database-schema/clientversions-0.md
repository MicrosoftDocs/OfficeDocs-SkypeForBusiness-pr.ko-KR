---
title: ClientVersions 보기
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 보기에는 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 정보가 저장되어 있습니다. 보기의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813358"
---
# <a name="clientversions-view"></a><span data-ttu-id="0f74e-105">ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="0f74e-105">ClientVersions view</span></span>
 
<span data-ttu-id="0f74e-106">ClientVersions 보기에는 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 정보가 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0f74e-107">보기의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="0f74e-108">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f74e-109">특정 열에 여러 레코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="0f74e-110">**열**</span><span class="sxs-lookup"><span data-stu-id="0f74e-110">**Column**</span></span>|<span data-ttu-id="0f74e-111">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="0f74e-111">**Data Type**</span></span>|<span data-ttu-id="0f74e-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="0f74e-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f74e-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="0f74e-113">**VersionId**</span></span> <br/> |<span data-ttu-id="0f74e-114">int</span><span class="sxs-lookup"><span data-stu-id="0f74e-114">int</span></span>  <br/> |<span data-ttu-id="0f74e-115">이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="0f74e-116">**버전**</span><span class="sxs-lookup"><span data-stu-id="0f74e-116">**Version**</span></span> <br/> |<span data-ttu-id="0f74e-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0f74e-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f74e-118">사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="0f74e-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="0f74e-119">**ClientType**</span></span> <br/> |<span data-ttu-id="0f74e-120">int</span><span class="sxs-lookup"><span data-stu-id="0f74e-120">int</span></span>  <br/> |<span data-ttu-id="0f74e-121">클라이언트 유형입니다</span><span class="sxs-lookup"><span data-stu-id="0f74e-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="0f74e-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="0f74e-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="0f74e-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="0f74e-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="0f74e-p103">클라이언트가 속한 범주입니다. 예를 들어 Conferencing_Attendant_1.0 클라이언트는 ClientCategory CAA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="0f74e-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

