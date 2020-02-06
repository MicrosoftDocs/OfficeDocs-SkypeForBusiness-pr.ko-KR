---
title: 비즈니스용 Skype 서버 2015의 Mcus 테이블
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 서비스에 대 한 정보를 저장 합니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행 됨)와 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815066"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="00131-105">비즈니스용 Skype 서버 2015의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="00131-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00131-106">Mcus 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="00131-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="00131-107">각 레코드는 하나의 회의 서비스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00131-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="00131-108">여기에는 IM 회의 서비스 및 전화 통신 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행 됨)와 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00131-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="00131-109">**열**</span><span class="sxs-lookup"><span data-stu-id="00131-109">**Column**</span></span>|<span data-ttu-id="00131-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="00131-110">**Data Type**</span></span>|<span data-ttu-id="00131-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="00131-111">**Key/Index**</span></span>|<span data-ttu-id="00131-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="00131-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00131-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="00131-113">**McuId**</span></span> <br/> |<span data-ttu-id="00131-114">int</span><span class="sxs-lookup"><span data-stu-id="00131-114">int</span></span>  <br/> |<span data-ttu-id="00131-115">주요한</span><span class="sxs-lookup"><span data-stu-id="00131-115">Primary</span></span>  <br/> |<span data-ttu-id="00131-116">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="00131-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="00131-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="00131-117">**McuUri**</span></span> <br/> |<span data-ttu-id="00131-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00131-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="00131-119">**M가공선 Ypeid**</span><span class="sxs-lookup"><span data-stu-id="00131-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="00131-120">inyint</span><span class="sxs-lookup"><span data-stu-id="00131-120">inyint</span></span>  <br/> | <span data-ttu-id="00131-121">외부</span><span class="sxs-lookup"><span data-stu-id="00131-121">Foreign</span></span> <br/> |<span data-ttu-id="00131-122">컨퍼런스: 채팅 (Im의 경우) 또는 컨퍼런스: 오디오-비디오 등의 회의 서버 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="00131-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="00131-123">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00131-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

