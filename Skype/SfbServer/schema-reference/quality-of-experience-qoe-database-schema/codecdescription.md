---
title: CodecDescription 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다. 이 표는 Microsoft Lync Server 2013에서 도입
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831348"
---
# <a name="codecdescription-table"></a><span data-ttu-id="bab07-105">CodecDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="bab07-105">CodecDescription table</span></span>
 
<span data-ttu-id="bab07-106">CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="bab07-107">코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="bab07-108">이 표는 Microsoft Lync Server 2013에서 도입</span><span class="sxs-lookup"><span data-stu-id="bab07-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="bab07-109">**열**</span><span class="sxs-lookup"><span data-stu-id="bab07-109">**Column**</span></span>|<span data-ttu-id="bab07-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="bab07-110">**Data Type**</span></span>|<span data-ttu-id="bab07-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="bab07-111">**Key/Index**</span></span>|<span data-ttu-id="bab07-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="bab07-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bab07-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="bab07-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="bab07-114">smallint</span><span class="sxs-lookup"><span data-stu-id="bab07-114">smallint</span></span>  <br/> |<span data-ttu-id="bab07-115">Primary</span><span class="sxs-lookup"><span data-stu-id="bab07-115">Primary</span></span>  <br/> |<span data-ttu-id="bab07-116">코덱에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="bab07-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="bab07-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="bab07-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="bab07-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="bab07-119">고유</span><span class="sxs-lookup"><span data-stu-id="bab07-119">Unique</span></span>  <br/> |<span data-ttu-id="bab07-120">CodecDescriptionKey에 해당하는 코덱의 고유한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

