---
title: 사용자 환경 품질 | Microsoft Teams | QoS | 통화 품질
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리자는 Microsoft Teams의 품질 및 사용을 모니터링하는 데 필요한 작업 및 활동에 대해 배울 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808998"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="83b7d-103">QoE(체감 품질) 검토 가이드</span><span class="sxs-lookup"><span data-stu-id="83b7d-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="83b7d-104">![업그레이드 여정의 운영 효율성 단계가 강조 표시된 다이어그램](media/upgrade-banner-op-excellence.png "운영 효율성 단계에 강조를 두는 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="83b7d-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="83b7d-105">이 문서는 비즈니스용 Skype에서 Teams로의 업그레이드를 완료하는 즉시 시작하는 업그레이드 여정의 운영 효율성 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="83b7d-106">통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="83b7d-106">Improve and monitor call quality</span></span>

<span data-ttu-id="83b7d-107">[Teams의](monitor-call-quality-qos.md) 통화 품질 개선 및 모니터링에는 아래와 같은 사용자 환경 개선에 가장 큰 영향을 주는 주요 영역에서 수정 지침을 평가하고 제공하는 활동 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="83b7d-108">![검토 중에 검사할 주요 영역의 그림입니다.](media/plan-my-service-management-image2.png "경험 품질 검토 중에 검사할 주요 영역은 오디오, 안정성 및 사용자 설문 조사 결과입니다.")</span><span class="sxs-lookup"><span data-stu-id="83b7d-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="83b7d-109">가이드에 설명된 영역을 지속적으로 평가하고 수정하여 사용자 경험에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="83b7d-110">배포에서 발생하는 대부분의 사용자 환경 문제는 다음 범주로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="83b7d-111">불완전한 방화벽 또는 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="83b7d-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="83b7d-112">불량 Wi-Fi 검사</span><span class="sxs-lookup"><span data-stu-id="83b7d-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="83b7d-113">대역폭 부족</span><span class="sxs-lookup"><span data-stu-id="83b7d-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="83b7d-114">VPN</span><span class="sxs-lookup"><span data-stu-id="83b7d-114">VPN</span></span>

- <span data-ttu-id="83b7d-115">사용할 수 없는 오디오 장치 또는 기본 제공 오디오 장치 사용</span><span class="sxs-lookup"><span data-stu-id="83b7d-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="83b7d-116">문제가 있는 서브넷 또는 네트워크 디바이스</span><span class="sxs-lookup"><span data-stu-id="83b7d-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="83b7d-117">[Teams의](monitor-call-quality-qos.md) 통화 품질 개선 및 모니터링에 제공된 지침은 채택과 영향을 최대화하기 위해 오디오에 초점을 맞추고 설명된 각 영역을 보고하고 조사하는 기본 도구로 CQD(통화 품질 대시보드) Online을 사용하는 데 중점을 습니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="83b7d-118">또한 오디오 환경을 개선하기 위해 네트워크를 최적화하면 비디오 및 데스크톱 공유가 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="83b7d-119">품질 챔피언을 초기에 추천하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83b7d-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="83b7d-120">지명된 후 Teams의 통화 품질 개선 및 모니터링 콘텐츠에 [익숙해지기 시작해야 합니다.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="83b7d-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
