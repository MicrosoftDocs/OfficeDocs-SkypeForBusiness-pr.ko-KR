---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다. 이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196621"
---
# <a name="tblpreference"></a><span data-ttu-id="ce86e-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="ce86e-104">tblPreference</span></span>

<span data-ttu-id="ce86e-105">tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce86e-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="ce86e-106">이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce86e-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="ce86e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="ce86e-107">**Columns**</span></span>


| <span data-ttu-id="ce86e-108">**열**</span><span class="sxs-lookup"><span data-stu-id="ce86e-108">**Column**</span></span>            | <span data-ttu-id="ce86e-109">**유형**</span><span class="sxs-lookup"><span data-stu-id="ce86e-109">**Type**</span></span>                        | <span data-ttu-id="ce86e-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="ce86e-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="ce86e-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="ce86e-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="ce86e-112">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="ce86e-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="ce86e-113">레이블이 다음과 같은 형식으로 지정 된 \<레이블: 사용자 sip uri\></span><span class="sxs-lookup"><span data-stu-id="ce86e-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="ce86e-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="ce86e-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="ce86e-115">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="ce86e-115">int, not null</span></span>  <br/>            | <span data-ttu-id="ce86e-116">버전 관리 목적에 대 한 순차 번호 (레이블 당).</span><span class="sxs-lookup"><span data-stu-id="ce86e-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="ce86e-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="ce86e-117">prefContent</span></span>  <br/>    | <span data-ttu-id="ce86e-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ce86e-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="ce86e-119">인코딩된 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ce86e-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="ce86e-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="ce86e-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="ce86e-121">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="ce86e-121">int, not null</span></span>  <br/>            | <span data-ttu-id="ce86e-122">기본 설정을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ce86e-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="ce86e-123">**키**</span><span class="sxs-lookup"><span data-stu-id="ce86e-123">**Key**</span></span>

|<span data-ttu-id="ce86e-124">**열**</span><span class="sxs-lookup"><span data-stu-id="ce86e-124">**Column**</span></span>|<span data-ttu-id="ce86e-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="ce86e-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce86e-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="ce86e-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="ce86e-127">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ce86e-127">Primary key.</span></span>  <br/> |


