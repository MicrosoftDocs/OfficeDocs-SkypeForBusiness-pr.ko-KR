---
title: '비즈니스용 Skype 서버 2019에 대한 가상화 지원 '
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
description: '요약: 비즈니스용 Skype 서버 2019의 가상화 지원에 대해 자세히 알아보습니다.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509035"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="67ec2-103">비즈니스용 Skype 서버 2019에 대한 가상화 지원</span><span class="sxs-lookup"><span data-stu-id="67ec2-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="67ec2-104">비즈니스용 Skype 서버 2019는 가상화에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="67ec2-105">가상화가 지원되는 동안 기억해야 할 몇 가지 주요 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="67ec2-106">가상 CPU와 실제 CPU의 1:1 비율을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="67ec2-107">게스트 서버가 작동되는 동안에는 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="67ec2-108">라이브 시스템 마이그레이션 및 가상 컴퓨터의 이식성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="67ec2-109">모든 호스트에서 하이퍼스레딩을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="67ec2-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="67ec2-110">호스트 서버에서 동적 메모리를 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="67ec2-111">동적 디스크 대신 고정 또는 통과 디스크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="67ec2-112">가상 게스트에 필요한 것 이상으로 하이퍼바이저에 대한 오버헤드를 6-10% 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="67ec2-113">지원되는 하이퍼바이터</span><span class="sxs-lookup"><span data-stu-id="67ec2-113">Supported hypervisors</span></span>

<span data-ttu-id="67ec2-114">SfB Server 2019는 Windows Server 2016 및 Windows Server 2019에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="67ec2-115">타사 하이퍼바이서의 경우 관련 OS에 대한 SVVP(서버 가상화 유효성 검사 프로그램) 테스트를 통과한 하이퍼바이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="67ec2-116">SVVP 목록에서 [Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec2-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="67ec2-117">SVVP 목록에서 [Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec2-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="67ec2-118">스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="67ec2-118">Stress and performance tool</span></span>

<span data-ttu-id="67ec2-119">비즈니스용 Skype 서버 2019 스트레스 및 성능 도구에는 비즈니스용 Skype 서버 2019의 용량 계획을 간소화하는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="67ec2-120">비즈니스용 Skype 서버 2019 스트레스 및 성능 도구를 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="67ec2-121">비즈니스용 Skype 서버 2019의 하드웨어 계획 간소화</span><span class="sxs-lookup"><span data-stu-id="67ec2-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="67ec2-122">성능 조정을 위한 더 많은 지식 및 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec2-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="67ec2-123">의도한 비즈니스용 Skype 서버 2019 배포의 성능 측정</span><span class="sxs-lookup"><span data-stu-id="67ec2-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="67ec2-124">여기에서 도구를 다운로드할 수 [있습니다.](https://www.microsoft.com/download/details.aspx?id=101447)</span><span class="sxs-lookup"><span data-stu-id="67ec2-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
