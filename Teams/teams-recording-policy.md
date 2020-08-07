---
title: 팀에 대 한 소개 정책 기반 기록 & 모임 통화
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 팀 정책 기반 & 모임 통화에 대 한 자세한 정보
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63aee051467d07a5eef9063538d740b07e6eadf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584087"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="5743e-103">팀 소개 정책 기반 & 모임 기록</span><span class="sxs-lookup"><span data-stu-id="5743e-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="5743e-104">정책 기반 기록은 Microsoft 팀이 관리 정책을 사용 하 여 stipulate에 전화를 걸고 모임을 하는 조직에 게, 관련 회사 또는 규정 정책에서 요구 하는 후속 처리 및 보존을 위해 통화와 온라인 모임을 자동으로 기록 하 고 캡처할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="5743e-105">팀 통신을 구성, 관리, 기록, 저장 및 분석 하는 종단 간 솔루션을 제공 하는 데 필요한 플랫폼 기능, 사용자 환경, 관리 인터페이스를 비롯 한 타사 기록 솔루션의 통합을 지원 하도록 성능이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="5743e-106">여기에는 다음을 제공 하는 기록에 대 한 통신 플랫폼 Api 및 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="5743e-107">장치 간의 원활한 고품질 미디어 캡처 및 오디오, 비디오, 화면 공유, 채팅에 대해 지원 되는 모든 끝점</span><span class="sxs-lookup"><span data-stu-id="5743e-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="5743e-108">팀 사용자 간 상호 작용 캡처 지원 및 지원 되는 호출 끝점 (팀, 팀 모바일, 비즈니스용 Skype, PSTN)</span><span class="sxs-lookup"><span data-stu-id="5743e-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="5743e-109">기존 팀 관리 통화, 모임 도구 및 정책과의 통합을 포함 하 여 규정 준수 기록에 대 한 새로운 관리 정책</span><span class="sxs-lookup"><span data-stu-id="5743e-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="5743e-110">[고급 통신 라이선스가](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/advanced-communications) 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-110">Requires an [Advanced Communications license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/advanced-communications)</span></span>

<span data-ttu-id="5743e-111">준수 기록 [<span class="underline">및 Microsoft 팀 세션</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)의 Ignite 2019 에서도 문제 해결 기록 솔루션 통합 기능을 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="5743e-112">팀 조작 기록 개요</span><span class="sxs-lookup"><span data-stu-id="5743e-112">Teams interaction recording overview</span></span>

<span data-ttu-id="5743e-113">조작 기록 사용 사례는 이미지에 표시 된 것 처럼 편리한, 함수형, 조직적, 합법적 가로채기의 네 가지 기본 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="5743e-114">![상호 작용 기록 및 그 이유를 보여 주는 스크린샷](media/recording-taxonomy.png "이미지에는 기록 범주가 표시 됩니다.")</span><span class="sxs-lookup"><span data-stu-id="5743e-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="5743e-115">각 범주는 녹음/녹화를 시작 하는 방법, 기록 되는 내용, 녹음/녹화의 위치, 알림 메시지, 액세스를 제어 하는 사용자, 보존이 처리 되는 방식에 대 한 요구 사항이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="5743e-116">방법일</span><span class="sxs-lookup"><span data-stu-id="5743e-116">Convenience</span></span>        | <span data-ttu-id="5743e-117">작동</span><span class="sxs-lookup"><span data-stu-id="5743e-117">Functional</span></span>         | <span data-ttu-id="5743e-118">조직-일반</span><span class="sxs-lookup"><span data-stu-id="5743e-118">Org - General</span></span>      | <span data-ttu-id="5743e-119">조직 규정</span><span class="sxs-lookup"><span data-stu-id="5743e-119">Org - Regulated</span></span> | <span data-ttu-id="5743e-120">합법적 가로채기</span><span class="sxs-lookup"><span data-stu-id="5743e-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="5743e-121">사람</span><span class="sxs-lookup"><span data-stu-id="5743e-121">Initiator</span></span>              | <span data-ttu-id="5743e-122">사용자</span><span class="sxs-lookup"><span data-stu-id="5743e-122">User</span></span>               | <span data-ttu-id="5743e-123">앱/솔루션</span><span class="sxs-lookup"><span data-stu-id="5743e-123">App/Solution</span></span>       | <span data-ttu-id="5743e-124">관리자 (시스템)</span><span class="sxs-lookup"><span data-stu-id="5743e-124">Admin (system)</span></span>     | <span data-ttu-id="5743e-125">관리자 (시스템)</span><span class="sxs-lookup"><span data-stu-id="5743e-125">Admin (system)</span></span>  | <span data-ttu-id="5743e-126">LEA</span><span class="sxs-lookup"><span data-stu-id="5743e-126">LEA</span></span>                |
| <span data-ttu-id="5743e-127">대상</span><span class="sxs-lookup"><span data-stu-id="5743e-127">Target</span></span>                 | <span data-ttu-id="5743e-128">통화 당/회의</span><span class="sxs-lookup"><span data-stu-id="5743e-128">Per-call / meeting</span></span> | <span data-ttu-id="5743e-129">통화 당/회의</span><span class="sxs-lookup"><span data-stu-id="5743e-129">Per-call / meeting</span></span> | <span data-ttu-id="5743e-130">통화 당/회의</span><span class="sxs-lookup"><span data-stu-id="5743e-130">Per-call / meeting</span></span> | <span data-ttu-id="5743e-131">사용자별</span><span class="sxs-lookup"><span data-stu-id="5743e-131">Per-user</span></span>        | <span data-ttu-id="5743e-132">끝점 단위/</span><span class="sxs-lookup"><span data-stu-id="5743e-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="5743e-133">저장소 소유자</span><span class="sxs-lookup"><span data-stu-id="5743e-133">Storage owner</span></span>          | <span data-ttu-id="5743e-134">사용자</span><span class="sxs-lookup"><span data-stu-id="5743e-134">User</span></span>               | <span data-ttu-id="5743e-135">내</span><span class="sxs-lookup"><span data-stu-id="5743e-135">App</span></span>                | <span data-ttu-id="5743e-136">관리자</span><span class="sxs-lookup"><span data-stu-id="5743e-136">Admin</span></span>              | <span data-ttu-id="5743e-137">규정 준수</span><span class="sxs-lookup"><span data-stu-id="5743e-137">Compliance</span></span>      | <span data-ttu-id="5743e-138">LEA</span><span class="sxs-lookup"><span data-stu-id="5743e-138">LEA</span></span>                |
| <span data-ttu-id="5743e-139">알림이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="5743e-139">Notification required?</span></span> | <span data-ttu-id="5743e-140">예</span><span class="sxs-lookup"><span data-stu-id="5743e-140">Yes</span></span>                | <span data-ttu-id="5743e-141">예</span><span class="sxs-lookup"><span data-stu-id="5743e-141">Yes</span></span>                | <span data-ttu-id="5743e-142">예</span><span class="sxs-lookup"><span data-stu-id="5743e-142">Yes</span></span>                | <span data-ttu-id="5743e-143">예</span><span class="sxs-lookup"><span data-stu-id="5743e-143">Yes</span></span>             | <span data-ttu-id="5743e-144">아니요</span><span class="sxs-lookup"><span data-stu-id="5743e-144">No</span></span>                 |
| <span data-ttu-id="5743e-145">액세스 소유자</span><span class="sxs-lookup"><span data-stu-id="5743e-145">Access Owner</span></span>           | <span data-ttu-id="5743e-146">사용자</span><span class="sxs-lookup"><span data-stu-id="5743e-146">User</span></span>               | <span data-ttu-id="5743e-147">내</span><span class="sxs-lookup"><span data-stu-id="5743e-147">App</span></span>                | <span data-ttu-id="5743e-148">관리자</span><span class="sxs-lookup"><span data-stu-id="5743e-148">Admin</span></span>              | <span data-ttu-id="5743e-149">규정 준수</span><span class="sxs-lookup"><span data-stu-id="5743e-149">Compliance</span></span>      | <span data-ttu-id="5743e-150">LEA</span><span class="sxs-lookup"><span data-stu-id="5743e-150">LEA</span></span>                |
| <span data-ttu-id="5743e-151">보존 정책</span><span class="sxs-lookup"><span data-stu-id="5743e-151">Retention Policy?</span></span>      | <span data-ttu-id="5743e-152">선택</span><span class="sxs-lookup"><span data-stu-id="5743e-152">Optional</span></span>           | <span data-ttu-id="5743e-153">예</span><span class="sxs-lookup"><span data-stu-id="5743e-153">Yes</span></span>                | <span data-ttu-id="5743e-154">예</span><span class="sxs-lookup"><span data-stu-id="5743e-154">Yes</span></span>                | <span data-ttu-id="5743e-155">예</span><span class="sxs-lookup"><span data-stu-id="5743e-155">Yes</span></span>             | <span data-ttu-id="5743e-156">예</span><span class="sxs-lookup"><span data-stu-id="5743e-156">Yes</span></span>                |

<span data-ttu-id="5743e-157">팀은 모임 및 라이브 이벤트에 대 한 [<span class="underline">편리한</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) 기능과 기능 기록을 위한 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="5743e-158">조직 기록은 팀을 채택 하 여 stipulate에 게 전화를 걸고 모임을 하는 조직을 사용 하도록 설정 하는 것을 의미 합니다. 통화와 온라인 모임을 자동으로 기록 하 고 관련 회사 또는 규정 정책에 따라 후속 처리 및 보존을 위해 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="5743e-159">이 정책에 속하는 사용자는 팀과의 디지털 조작이 기록 되 고 있음을 알 수 있지만,이는 조작이 완료 된 후에는 녹음/녹화에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="5743e-160">기록은 eDiscovery, 법률 고 지, 기타 기업 보존 용도에 부합 하 고 법적 담당자가 사용할 수 있는 조직 아카이브의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="5743e-161">사용자 요구 예제</span><span class="sxs-lookup"><span data-stu-id="5743e-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5743e-162"><strong>가</strong></span><span class="sxs-lookup"><span data-stu-id="5743e-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="5743e-163"><strong>성과</strong></span><span class="sxs-lookup"><span data-stu-id="5743e-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5743e-164">기록 된 사용자</span><span class="sxs-lookup"><span data-stu-id="5743e-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="5743e-165">기록이 진행 중일 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="5743e-166">정책 및 기록 오류로 인해 호출 동작이 변경 되는 경우 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5743e-167">통신 관리자</span><span class="sxs-lookup"><span data-stu-id="5743e-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="5743e-168">팀 사용자/끝점에 기록 정책을 적용/시행 하는 이유와 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="5743e-169">조직의 팀 기록 정책을 구성 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="5743e-170">팀 전화 및 모임에서 기록 관련 문제를 모니터링 하 고 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="5743e-171">사용, 품질 및 안정성에 대 한 운영 분석을 통해 내부 규정 준수 책임자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5743e-172">규정 준수 책임자</span><span class="sxs-lookup"><span data-stu-id="5743e-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="5743e-173">적절 한 지역 경계에서 준수 의무를 충족 하는 데 필요한 방식으로 모든 팀의 의사 소통을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="5743e-174">통신 관련 메타 데이터 또는 상호 작용 콘텐츠를 기준으로 상호 작용을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="5743e-175">일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="5743e-176"><strong>메타 데이터</strong> - 참가자, 시간, 방향, 전화 번호, 원래 번호, 사용자 지정 비즈니스 데이터</span><span class="sxs-lookup"><span data-stu-id="5743e-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="5743e-177"><strong>콘텐츠 – 내용</strong> , 정서, 윗주, 관련 조작</span><span class="sxs-lookup"><span data-stu-id="5743e-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="5743e-178">수집 되는 의사 소통을 모니터링 하는 기능을 포함 하 여 수집 된 통신을 분석 하 고 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="5743e-179">수집 된 통신의 보안을 보장 하 고 모든 단계에서 변조를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="5743e-180">솔루션 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="5743e-180">Solution architecture overview</span></span>

<span data-ttu-id="5743e-181">준수 기록 솔루션은 다음 다이어그램에 표시 된 것 처럼 팀과 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="5743e-182">![팀 사용자 지정 앱 설정을 보여 주는 스크린샷](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "이미지는 팀 모임 또는 통화를 보내고 받을 때의 흐름을 보여 줍니다.")</span><span class="sxs-lookup"><span data-stu-id="5743e-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="5743e-183">녹음</span><span class="sxs-lookup"><span data-stu-id="5743e-183">Recorder</span></span>

<span data-ttu-id="5743e-184">준수 기록 솔루션의 핵심 구성 요소는 레코더입니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="5743e-185">레코더는 microsoft [<span class="underline">의 통신 플랫폼을 활용</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) 하 고 microsoft Graph를 사용 하 여 응용 프로그램으로 등록 하는 확장 가능한 Azure 기반 서비스 (bot)로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="5743e-186">레코더는 팀 호출 및 모임 [<span class="underline">통신 플랫폼 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 와 직접 상호 작용을 제공 하 고 미디어 수집을 위한 끝점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="5743e-187">봇을 구성 하 고, 앱 인스턴스를 만들고, 준수 정책을 할당 하는 방법을 보여 주는 [<span class="underline">샘플 준수 기록 응용 프로그램을 사용할 수 있습니다</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) .</span><span class="sxs-lookup"><span data-stu-id="5743e-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="5743e-188">또한 샘플에는 [<span class="underline">들어오는 호출</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   라우팅 처리, [<span class="underline">기록 상태 변경</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), 그리고 [<span class="underline">기록 중인 사용자 제거</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)와 같은 특정 조작을 기록 하는 API 사용에 대 한 예제가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="5743e-189">특정 Api에 대 한 그래프 문서는 [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) 및 [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)에 대해 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="5743e-190">레코더 서비스의 정확한 구현은 파트너 마다 다르며, 팀의 대기 시간을 기록으로 줄이기 위해 배포의 고가용성 및 지리적 배포를 달성 하기 위해 여러 레코더를 지원 하도록 디자인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="5743e-191">또한, 복원성과 중복성을 고려 하 여 레코더 자체를 디자인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="5743e-192">파트너는 인증을 위해 솔루션을 제출 하기 전에 microsoft Graph와 Sdk의 최소 필요한 릴리스 버전을 확인 하 여 준수 기록 통합의 모든 요구 사항이 지원 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="5743e-193">다음과 같은 두 가지 특정 요구 사항은 시나리오의 준수 기록에 대 한 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="5743e-194">레코더 봇을 Azure에 배포 해야 함</span><span class="sxs-lookup"><span data-stu-id="5743e-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="5743e-195">레코더 봇이 Azure의 Windows VM에서 실행 되어야 함</span><span class="sxs-lookup"><span data-stu-id="5743e-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="5743e-196">Azure 및 Windows VM 요구 사항은 팀 인공 지능 구성 요소에만 적용 되며, 파트너는 해당 사용자가 선택 하는 플랫폼의 나머지를 구현할 수 있으므로, 준수 기록에 대 한 관련 성능 및 기능적 요구 조건을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="5743e-197">준수 기록 정책 과제 및 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="5743e-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="5743e-198">IT 관리자는 규정 준수 기록 정책을 만들고 할당 하 여 기록 되는 사용자와 각 사용자에 게 사용할 레코더를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="5743e-199">녹음기는 통신 조작이 발생 하는 경우 이러한 정책의 구성을 기반으로 대화에 참여 하도록 자동으로 초대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="5743e-200">준수 기록 정책은 [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) 을 사용 하 여 관리 되며 각 조직의 테 넌 트, 사용자 단위 및 보안 그룹 수준에서 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="5743e-201">Microsoft 문서에서 [<span class="underline">모임 정책</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">호출 정책</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) 및 [<span class="underline">그룹 정책</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="5743e-202">테 넌 트에 응용 프로그램 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-202">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="5743e-203">준수 기록 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-203">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="5743e-204"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="5743e-204"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="5743e-205">사용자에 게 준수 기록 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-205">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="5743e-206"><span class="underline">부여-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="5743e-206"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="5743e-207">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="5743e-207">User experiences</span></span>

<span data-ttu-id="5743e-208">알림 지원은 팀 클라이언트 환경을 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-208">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="5743e-209">환경은 visual 또는 audio 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-209">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="5743e-210">**팀 클라이언트-시각적 알림**</span><span class="sxs-lookup"><span data-stu-id="5743e-210">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="5743e-211">데스크톱/웹</span><span class="sxs-lookup"><span data-stu-id="5743e-211">Desktop/web</span></span>
- <span data-ttu-id="5743e-212">모바일 (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="5743e-212">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="5743e-213">팀 전화</span><span class="sxs-lookup"><span data-stu-id="5743e-213">Teams phones</span></span>
- <span data-ttu-id="5743e-214">팀 대화방</span><span class="sxs-lookup"><span data-stu-id="5743e-214">Teams rooms</span></span>

<span data-ttu-id="5743e-215">**기타 끝점-오디오 알림**</span><span class="sxs-lookup"><span data-stu-id="5743e-215">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="5743e-216">SIP 전화</span><span class="sxs-lookup"><span data-stu-id="5743e-216">SIP phones</span></span>
- <span data-ttu-id="5743e-217">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="5743e-217">Skype for Business</span></span>
- <span data-ttu-id="5743e-218">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="5743e-218">Audio conferencing</span></span>
- <span data-ttu-id="5743e-219">PSTN 발신자</span><span class="sxs-lookup"><span data-stu-id="5743e-219">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="5743e-220">팀 인증 프로그램에 대 한 규정 준수 기록</span><span class="sxs-lookup"><span data-stu-id="5743e-220">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="5743e-221">파트너가 팀을 통해 CCaaS 개발 및 통합할 수 있도록 공개적으로 사용할 수 있는 Api를 게시 하는 것 외에, Microsoft 팀에서 각 파트너의 솔루션이 테스트를 수행 하 고 Microsoft 솔루션에서 기대 하는 품질, 호환성 및 안정성을 제공 하도록 확인 하는 것을 고객에 게 제공 하는 인증 프로그램에 대 한 준수 기록을 개발 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-221">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="5743e-222">다음 파트너는 Microsoft 팀의 솔루션을 인증 하는 과정을 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-222">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="5743e-223">Partner</span><span class="sxs-lookup"><span data-stu-id="5743e-223">Partner</span></span>|<span data-ttu-id="5743e-224">솔루션 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="5743e-224">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="5743e-225">ASC 기술</span><span class="sxs-lookup"><span data-stu-id="5743e-225">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="5743e-226">오디오 코드</span><span class="sxs-lookup"><span data-stu-id="5743e-226">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="5743e-227">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="5743e-227">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="5743e-228">좋지</span><span class="sxs-lookup"><span data-stu-id="5743e-228">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="5743e-229">Numonix</span><span class="sxs-lookup"><span data-stu-id="5743e-229">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="5743e-230">빨간색 상자</span><span class="sxs-lookup"><span data-stu-id="5743e-230">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="5743e-231">Verint</span><span class="sxs-lookup"><span data-stu-id="5743e-231">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="5743e-232">이 목록은 더 많은 파트너가 참가 하 고 인증 기준을 충족 하면 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-232">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5743e-233">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5743e-233">Next steps</span></span>

<span data-ttu-id="5743e-234">인증 프로그램에 참여 하는 공급 업체를 찾고 있다면 메일을 <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5743e-234">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
