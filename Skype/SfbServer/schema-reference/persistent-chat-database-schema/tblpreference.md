---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference에는 사용자의 클라이언트 기본 설정이 포함되어 있습니다. 일반적으로 Lync 2013 이전의 클라이언트에서 사용됩니다.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815908"
---
# <a name="tblpreference"></a><span data-ttu-id="1d58e-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="1d58e-104">tblPreference</span></span>

<span data-ttu-id="1d58e-105">tblPreference에는 사용자의 클라이언트 기본 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="1d58e-106">일반적으로 Lync 2013 이전의 클라이언트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="1d58e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="1d58e-107">**Columns**</span></span>


| <span data-ttu-id="1d58e-108">**열**</span><span class="sxs-lookup"><span data-stu-id="1d58e-108">**Column**</span></span>            | <span data-ttu-id="1d58e-109">**유형**</span><span class="sxs-lookup"><span data-stu-id="1d58e-109">**Type**</span></span>                        | <span data-ttu-id="1d58e-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="1d58e-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="1d58e-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="1d58e-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="1d58e-112">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="1d58e-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="1d58e-113">형식이 같은 레이블: \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="1d58e-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="1d58e-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="1d58e-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="1d58e-115">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1d58e-115">int, not null</span></span>  <br/>            | <span data-ttu-id="1d58e-116">버전 관리 목적의 일련 번호(레이블당)입니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="1d58e-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="1d58e-117">prefContent</span></span>  <br/>    | <span data-ttu-id="1d58e-118">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="1d58e-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="1d58e-119">인코딩된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="1d58e-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="1d58e-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="1d58e-121">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1d58e-121">int, not null</span></span>  <br/>            | <span data-ttu-id="1d58e-122">기본 설정을 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="1d58e-123">**키**</span><span class="sxs-lookup"><span data-stu-id="1d58e-123">**Key**</span></span>

|<span data-ttu-id="1d58e-124">**열**</span><span class="sxs-lookup"><span data-stu-id="1d58e-124">**Column**</span></span>|<span data-ttu-id="1d58e-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="1d58e-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="1d58e-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1d58e-126">Primary key.</span></span>  <br/> |


