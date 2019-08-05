---
title: CodecDescription 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 테이블은 고유 코덱 식별자를 해당 하는 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트에 대 한 디지털 신호를 인코딩한 다음 재생을 위해 해당 신호를 디코딩 하는 데 사용 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196578"
---
# <a name="codecdescription-table"></a><span data-ttu-id="ef11c-105">CodecDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="ef11c-105">CodecDescription table</span></span>
 
<span data-ttu-id="ef11c-106">CodecDescription 테이블은 고유 코덱 식별자를 해당 하는 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ef11c-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="ef11c-107">코덱은 전송 및 브로드캐스트에 대 한 디지털 신호를 인코딩한 다음 재생을 위해 해당 신호를 디코딩 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef11c-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="ef11c-108">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef11c-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="ef11c-109">**열**</span><span class="sxs-lookup"><span data-stu-id="ef11c-109">**Column**</span></span>|<span data-ttu-id="ef11c-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="ef11c-110">**Data Type**</span></span>|<span data-ttu-id="ef11c-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="ef11c-111">**Key/Index**</span></span>|<span data-ttu-id="ef11c-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="ef11c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ef11c-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="ef11c-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="ef11c-114">smallint</span><span class="sxs-lookup"><span data-stu-id="ef11c-114">smallint</span></span>  <br/> |<span data-ttu-id="ef11c-115">주요한</span><span class="sxs-lookup"><span data-stu-id="ef11c-115">Primary</span></span>  <br/> |<span data-ttu-id="ef11c-116">코덱에 할당 된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ef11c-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="ef11c-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="ef11c-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="ef11c-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef11c-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="ef11c-119">독특한</span><span class="sxs-lookup"><span data-stu-id="ef11c-119">Unique</span></span>  <br/> |<span data-ttu-id="ef11c-120">CodecDescriptionKey에 해당 하는 코덱에 대 한 고유한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ef11c-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

