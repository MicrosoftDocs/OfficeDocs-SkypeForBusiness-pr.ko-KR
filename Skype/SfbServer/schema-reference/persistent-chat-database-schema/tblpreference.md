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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다. 이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814556"
---
# <a name="tblpreference"></a><span data-ttu-id="fca99-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="fca99-104">tblPreference</span></span>

<span data-ttu-id="fca99-105">tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca99-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="fca99-106">이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca99-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="fca99-107">**열**</span><span class="sxs-lookup"><span data-stu-id="fca99-107">**Columns**</span></span>


| <span data-ttu-id="fca99-108">**열**</span><span class="sxs-lookup"><span data-stu-id="fca99-108">**Column**</span></span>            | <span data-ttu-id="fca99-109">**유형**</span><span class="sxs-lookup"><span data-stu-id="fca99-109">**Type**</span></span>                        | <span data-ttu-id="fca99-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="fca99-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="fca99-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="fca99-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="fca99-112">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="fca99-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="fca99-113">레이블이 다음과 같은 형식으로 지정 된 \<레이블: 사용자 sip uri\></span><span class="sxs-lookup"><span data-stu-id="fca99-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="fca99-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="fca99-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="fca99-115">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="fca99-115">int, not null</span></span>  <br/>            | <span data-ttu-id="fca99-116">버전 관리 목적에 대 한 순차 번호 (레이블 당).</span><span class="sxs-lookup"><span data-stu-id="fca99-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="fca99-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="fca99-117">prefContent</span></span>  <br/>    | <span data-ttu-id="fca99-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fca99-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="fca99-119">인코딩된 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="fca99-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="fca99-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="fca99-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="fca99-121">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="fca99-121">int, not null</span></span>  <br/>            | <span data-ttu-id="fca99-122">기본 설정을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fca99-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="fca99-123">**키**</span><span class="sxs-lookup"><span data-stu-id="fca99-123">**Key**</span></span>

|<span data-ttu-id="fca99-124">**열**</span><span class="sxs-lookup"><span data-stu-id="fca99-124">**Column**</span></span>|<span data-ttu-id="fca99-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="fca99-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fca99-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="fca99-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="fca99-127">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fca99-127">Primary key.</span></span>  <br/> |


