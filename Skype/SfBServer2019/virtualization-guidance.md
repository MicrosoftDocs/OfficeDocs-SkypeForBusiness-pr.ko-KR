---
title: '비즈니스용 Skype 서버 2019에 대 한 가상화 지원 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype 서버 2019에 대 한 가상화 지원에 대해 알아봅니다.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509035"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="71520-103">비즈니스용 Skype 서버 2019에 대 한 가상화 지원</span><span class="sxs-lookup"><span data-stu-id="71520-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="71520-104">비즈니스용 Skype 서버 2019은 가상화에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71520-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="71520-105">가상화가 지원 되는 동안 몇 가지 주요 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="71520-106">실제 CPU에 대 한 1:1 비율의 가상 CPU를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="71520-107">작동 중에는 게스트 서버를 이동 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="71520-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="71520-108">라이브 시스템 및 가상 컴퓨터의 이식성 마이그레이션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71520-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="71520-109">모든 호스트에서 하이퍼 스레드를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="71520-110">호스트 서버에 동적 메모리를 구성 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="71520-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="71520-111">동적 디스크가 아닌 고정 또는 통과 디스크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="71520-112">가상 게스트에 필요한 것 보다 더 이상 하이퍼바이저에 대 한 6-10% 오버 헤드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="71520-113">지원 되는 하이퍼바이저</span><span class="sxs-lookup"><span data-stu-id="71520-113">Supported hypervisors</span></span>

<span data-ttu-id="71520-114">SfB 서버 2019는 Windows Server 2016 및 Windows Server 2019에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71520-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="71520-115">타사 하이퍼바이저의 경우 관련 OS에 대 한 SVVP (서버 가상화 유효성 검사 프로그램) 테스트를 통과 한 하이퍼바이저가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="71520-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="71520-116">SVVP 목록에서 [Windows Server 2016 버전](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71520-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="71520-117">SVVP 목록에서 [Windows Server 2019 버전](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71520-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="71520-118">스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="71520-118">Stress and performance tool</span></span>

<span data-ttu-id="71520-119">비즈니스용 skype 서버 2019 스트레스 및 성능 도구에는 비즈니스용 Skype 서버 2019에 대 한 용량 계획을 간소화 하는 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71520-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="71520-120">비즈니스용 Skype 서버 2019 스트레스 및 성능 도구는 다음 작업을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71520-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="71520-121">비즈니스용 Skype 서버 2019에 대 한 하드웨어 계획 간소화</span><span class="sxs-lookup"><span data-stu-id="71520-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="71520-122">성능 조정에 대 한 향상 된 지식과 모범 사례 제공</span><span class="sxs-lookup"><span data-stu-id="71520-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="71520-123">예정 된 Skype for Business Server 2019 배포의 성능 측정</span><span class="sxs-lookup"><span data-stu-id="71520-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="71520-124">이 도구는 [여기](https://www.microsoft.com/download/details.aspx?id=101447)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71520-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
