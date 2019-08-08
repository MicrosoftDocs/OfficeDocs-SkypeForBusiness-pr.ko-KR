---
title: 사용자 환경 개선 | Microsoft 팀 | QoS | 통화 음질
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Microsoft 팀의 품질 및 사용 현황을 모니터링 하는 데 필요한 작업 및 활동
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecc3781f3190b7c7e5f52aec7ecf9dbae0894886
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236431"
---
<span data-ttu-id="cb777-103">![업그레이드 여행에 대 한 작업 진행을 보여 주는 다이어그램] 운영에 대 한 다양 한 (media/upgrade-banner-op-excellence.png "단계의 강조를 통해 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="cb777-103">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="cb777-104">이 문서는 비즈니스용 Skype에서 팀으로 업그레이드를 완료 하는 즉시 시작 되는 업그레이드 여행에 대 한 작업을 위한 뛰어난 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="cb777-105">경력 품질 검토 가이드</span><span class="sxs-lookup"><span data-stu-id="cb777-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="cb777-106">[경력 품질 검토 가이드](https://aka.ms/qerguide) 에는 아래 그림과 같이 사용자 환경 개선에 가장 큰 영향을 주는 주요 영역에서 개선 지침을 평가 하 고 제공 하는 일련의 활동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="cb777-107">![검토 중에 검사할 주요 영역에 대 한 그림입니다.] (media/plan-my-service-management-image2.png "경력을 검토 하는 동안에는 오디오, 안정성, 사용자 설문 조사 결과 중에서 검사할 주요 영역입니다.")</span><span class="sxs-lookup"><span data-stu-id="cb777-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="cb777-108">가이드에 설명 된 영역을 지속적으로 평가 하 고 수정 사용자 환경에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="cb777-109">배포에서 발생 하는 대부분의 사용자 경험 문제는 다음 범주로 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="cb777-110">방화벽 또는 프록시 구성이 완료 되지 않음</span><span class="sxs-lookup"><span data-stu-id="cb777-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="cb777-111">불량 Wi-fi 서비스</span><span class="sxs-lookup"><span data-stu-id="cb777-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="cb777-112">대역폭 부족</span><span class="sxs-lookup"><span data-stu-id="cb777-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="cb777-113">VPN</span><span class="sxs-lookup"><span data-stu-id="cb777-113">VPN</span></span>

- <span data-ttu-id="cb777-114">최적화 되지 않음 또는 내장 오디오 장치 사용</span><span class="sxs-lookup"><span data-stu-id="cb777-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="cb777-115">문제가 있는 서브넷 또는 네트워크 장치</span><span class="sxs-lookup"><span data-stu-id="cb777-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="cb777-116">경력 품질 검토 가이드에서 제공 하는 지침에 따라, 제공 되는 각 영역에 대해 보고 하 고 조사 하 고, 오디오에 초점을 따라 채택 및 영향을 최대화 하는 기본 도구로 서 온라인으로 CQD (통화 품질 대시보드)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="cb777-117">오디오 환경을 개선 하기 위해 네트워크에 대 한 최적화는 비디오 및 데스크톱 공유의 향상 된 기능으로 직접 번역 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="cb777-118">품질 챔피언을 일찍 지명할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="cb777-119">지정 된 후에는 [경험 치 검토 가이드](https://aka.ms/qerguide)의 콘텐츠를 숙지 하기 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb777-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
