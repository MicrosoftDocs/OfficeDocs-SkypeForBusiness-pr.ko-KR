---
title: 비즈니스용 Skype 서버의 Dialogs 테이블
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 테이블은 피어 투 피어 세션의 DialogID에 대한 정보를 저장하는 지원 테이블입니다.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816048"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="01043-103">비즈니스용 Skype 서버의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="01043-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="01043-104">Dialogs 테이블은 피어 투 피어 세션의 DialogID에 대한 정보를 저장하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="01043-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="01043-105">**열**</span><span class="sxs-lookup"><span data-stu-id="01043-105">**Column**</span></span>|<span data-ttu-id="01043-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="01043-106">**Data Type**</span></span>|<span data-ttu-id="01043-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="01043-107">**Key/Index**</span></span>|<span data-ttu-id="01043-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="01043-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01043-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="01043-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="01043-110">datetime</span><span class="sxs-lookup"><span data-stu-id="01043-110">datetime</span></span>  <br/> |<span data-ttu-id="01043-111">Primary</span><span class="sxs-lookup"><span data-stu-id="01043-111">Primary</span></span>  <br/> |<span data-ttu-id="01043-112">세션 요청 시간 세션을 고유하게 식별하기 위해 SessionIDSeq와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01043-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="01043-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="01043-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="01043-114">int</span><span class="sxs-lookup"><span data-stu-id="01043-114">int</span></span>  <br/> |<span data-ttu-id="01043-115">Primary</span><span class="sxs-lookup"><span data-stu-id="01043-115">Primary</span></span>  <br/> |<span data-ttu-id="01043-116">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="01043-116">ID number to identify the session.</span></span> <span data-ttu-id="01043-117">SessionIDTime과 함께 세션을 고유하게 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01043-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="01043-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="01043-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="01043-119">int</span><span class="sxs-lookup"><span data-stu-id="01043-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="01043-120">ExternalID의 체크um입니다.</span><span class="sxs-lookup"><span data-stu-id="01043-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="01043-121">이 필드는 데이터베이스 검색 속도를 높이는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01043-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="01043-122">**externalId**</span><span class="sxs-lookup"><span data-stu-id="01043-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="01043-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="01043-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="01043-124">이진 파일로 저장된 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01043-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="01043-125">이진 파일 형식은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="01043-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="01043-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="01043-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="01043-127">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01043-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

