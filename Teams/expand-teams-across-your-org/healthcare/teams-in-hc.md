---
title: 의료 조직을 위한 Teams 시작
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 주의 조정, 보안 메시징, telehealth, EHR 통합,에서 일선 worker 시스템 통합을 포함 하는 상태 관리 기능에 대해 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d2a77e5e7e696e20efb13a5c805968fc3af3204
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138108"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="22112-103">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="22112-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="22112-104">Microsoft 팀은 병원 및 기타 의료 단체에 유용한 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="22112-105">팀 기능은 다음을 지원 하기 위해 개발 중에 병원.</span><span class="sxs-lookup"><span data-stu-id="22112-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="22112-106">세심 한 조정 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="22112-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="22112-107">보안 메시지</span><span class="sxs-lookup"><span data-stu-id="22112-107">Secure Messaging</span></span>
- <span data-ttu-id="22112-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="22112-108">Telehealth</span></span>
- <span data-ttu-id="22112-109">EHR (전자 건강 보험 기록) 통합</span><span class="sxs-lookup"><span data-stu-id="22112-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="22112-110">Firstline Worker 시스템 통합</span><span class="sxs-lookup"><span data-stu-id="22112-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="22112-111">이 섹션의 내용은 모임, 통화, 메시징과 같은 팀의 기본 기능을 기반으로 하며 조직에 이미 팀을 배포한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="22112-112">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](../../How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="22112-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="22112-113">의료 협조-Microsoft 팀 환자 앱</span><span class="sxs-lookup"><span data-stu-id="22112-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="22112-114">Microsoft 팀에는 이제 건강 보험 조직과 관련 된 의료 협조 솔루션을 포함 하 고 있으며,이를 통해 가장 좋은 환자를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="22112-115">의료 코디 네이션 솔루션의 crux (Microsoft 팀 환자 앱)는 빠른 의료 상호 운용성 리소스 ([Fto r](https://www.hl7.org/fhir/)) 인터페이스를 사용 하 여 microsoft 팀에 연결 되어 있으며, 임상 공동 작업 및 의사 소통을 가능 하 게 하는 유용한 의료 정보를 컨텍스트로 통합 하는 제 1 자 탭 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="22112-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="22112-116">의료 코디 네이션 솔루션은 HL7v2 및 FA r과 같은 기존 상태 데이터 표준을 사용 하 여 환자 앱을 EHR 시스템에 연결할 수 있는 선두 독립 소프트웨어 공급 업체 (Isv)와 인터페이스 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="22112-117">Microsoft는 다음 업계 리더와 협력 하 여 팀과 전자 상태 레코드 통합을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="22112-118">Datica ( [CMI](https://datica.com/compliant-managed-integration/) 제공)</span><span class="sxs-lookup"><span data-stu-id="22112-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="22112-119">Cloverleaf ( [INFOR FA r 브리지](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)를 통해)</span><span class="sxs-lookup"><span data-stu-id="22112-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="22112-120">Redox ( [r ^ FA r 서버](https://www.redoxengine.com/fhir/)통과)</span><span class="sxs-lookup"><span data-stu-id="22112-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="22112-121">Dapasoft ( [FA r의 Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="22112-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="22112-122">건강 관리 기관에 대 한 Microsoft 팀을 구현 하는 EHR 통합 및 interop 파트너는 환자 앱에 의료 공급자 조직의 EHR 시스템에 대 한 보안 및 인증 된 연결을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="22112-123">이렇게 하면 관련 환자 레코드의 단방향 (읽기 전용) 흐름을 환자 앱으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="22112-124">환자 앱은 f r 형식을 인식 하므로, 파트너는 HL7v2 등의 다양 한 다른 형식에서 집계 된 데이터를 FTO r DSTU2 또는 STU3으로 변환 하는 역할도 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![신중 하 게 조정 및 공동 작업을 보여 주는 그림](../../media/ehr-1.png)

<br>

<span data-ttu-id="22112-126">환자 앱은 EHR (전자 상태 레코드) 시스템과 통합 되며 의사 공급자가 팀의 보안 플랫폼 내에서 실시간으로 환자를 처리할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams' secure platform.</span></span> <span data-ttu-id="22112-127">환자 앱은 다음과 같은 문제를 해결 하기 위해 주의 조정 영역에서 첫 번째 주요 투자입니다.</span><span class="sxs-lookup"><span data-stu-id="22112-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="22112-128">환자 경험을 통한 저렴 하 고 중요 한 의사 소통으로 인 한 효율성 향상</span><span class="sxs-lookup"><span data-stu-id="22112-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="22112-129">Siloed 관리 burdens를 생성 하는 정보</span><span class="sxs-lookup"><span data-stu-id="22112-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="22112-130">복잡 하 고 단편화 된 공동 작업 도구로 clinicians 간의 불만</span><span class="sxs-lookup"><span data-stu-id="22112-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="22112-131">너무 많은 비 리소스 임상 시간을 구울 수 있는 비효율적인 개인 관리 지원 조정</span><span class="sxs-lookup"><span data-stu-id="22112-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="22112-132">Microsoft 팀은 의사, clinicians, nurses, 기타 직원이 다음과 같이 효율적으로 공동 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="22112-133">Office 문서에서 작동 하 고 공동 작업 하는 단일 가상화 된 팀의 일부</span><span class="sxs-lookup"><span data-stu-id="22112-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="22112-134">다른 환자에 대 한 지속적인 대화를 통해 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="22112-135">탭에서 채널을 사용 하 여 작업을 구조화 하는 방법으로, 정보 원본을 고정 하는 탭의 추가 도움말을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="22112-136">팀의 오디오, 비디오, 화면 공유, 기록, 내용 기능을 통해 채널 모임을 사용 하 여 일일 모임 관리</span><span class="sxs-lookup"><span data-stu-id="22112-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="22112-137">환자 앱을 사용 하 여 모니터링 해야 하는 위험성이 높은 환자 목록을 만들고 EHR 시스템에서 최신 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22112-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="22112-138">환자 앱 자체는 Microsoft 팀에 다음 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="22112-139">단일 채널 내에서 여러 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="22112-140">구성 가능한 열을 통해 환자에 대해 표시 되는 정보를 보고 정렬 하는 기능.</span><span class="sxs-lookup"><span data-stu-id="22112-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="22112-141">팀 템플릿을 통해 앱을 자동으로 프로 비전 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="22112-142">IOS 및 Android 용 팀 앱에서 모바일 최초의 의료 근로자와 Microsoft 팀 웹 및 데스크톱 클라이언트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="22112-143">준수 문의 구문 분석을 통해 FDSTU2 및 STU3 버전에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="22112-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="22112-144">모든 보기 및 검색 작업에 대 한 감사 로그를 사용 하 여 HIPAA의 모든 사용자 인터페이스를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="22112-145">환자 앱은 팀 확장성 플랫폼을 기반으로 하며, 탭 프레임 워크를 활용 하 여 채널 내에서 다양 한 환자 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="22112-146">다른 팀 앱과 플랫폼 자체에 대해 자세히 알아보려면 [Microsoft 팀 용 앱](/microsoftteams/platform/concepts/apps/apps-overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="22112-147">환자 앱은 비공개 preview이 고 FTO r 인터페이스는 beta입니다.</span><span class="sxs-lookup"><span data-stu-id="22112-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="22112-148">릴리스 버전은 이전 버전과 호환 되지 않을 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22112-148">Released versions are not expected to be backward compatible.</span></span>

![데스크톱 및 모바일 장치에서 환자 앱 스크린샷](../../media/ehr-2.png)

<span data-ttu-id="22112-150">구현 세부 정보는 [Microsoft 팀에 전자 의료 기록 통합](patients-app.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="teams-templates"></a><span data-ttu-id="22112-151">팀 서식 파일</span><span class="sxs-lookup"><span data-stu-id="22112-151">Teams templates</span></span>

<span data-ttu-id="22112-152">팀을 만들기 위한 새 템플릿이 병원 설정에 적용 되도록 개발 되었고 더 많은 내용이 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="22112-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="22112-153">이를 통해 의료 근로자가 다양 한 부서나 wards의 환자을 조정 하는 데 사용 하는 팀을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-153">This makes it easier to create teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="22112-154">[의료 조직의 팀 서식 파일 시작을](healthcare-templates.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="22112-155">팀은 cardiology 등의 내부 부서를 위해 시작 하거나 주의를 wards 하 고 더 많은 서식 파일을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="lists-app"></a><span data-ttu-id="22112-156">목록 앱</span><span class="sxs-lookup"><span data-stu-id="22112-156">Lists app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="22112-157">팀의 목록 앱은 팀에서 정보를 추적 하 고 작업을 구성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22112-157">The Lists app in Teams helps teams track information and organize work.</span></span> <span data-ttu-id="22112-158">앱은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-158">The app is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="22112-159">목록은 미리 정의 된 서식 파일에서 만들거나 Excel로 데이터를 가져와 처음부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-159">Lists can be created from scratch, from predefined templates, or by importing data to Excel.</span></span>

<span data-ttu-id="22112-160">관리 팀에서 환자 서식 파일을 사용 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-160">Care teams can use the Patients template to get started.</span></span> <span data-ttu-id="22112-161">환자의 요구 및 상태를 추적 하는 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-161">They can create lists to track the needs and status of patients.</span></span> <span data-ttu-id="22112-162">팀에서 Excel 스프레드시트의 기존 환자 데이터를 가져와 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-162">Existing patient data on Excel spreadsheets can be brought in to create a list in Teams.</span></span> <span data-ttu-id="22112-163">이러한 목록은 라운드 및 환자 모니터링과 같은 시나리오에 사용 하 여 주의를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-163">These lists can be used for scenarios such as rounds and patient monitoring to coordinate care.</span></span>

<span data-ttu-id="22112-164">예를 들어, 청구 nurse는 모든 의료 팀 구성원을 포함 하는 환자 목록을 팀에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22112-164">For example, a charge nurse creates a patient list in a team that includes all care team members.</span></span> <span data-ttu-id="22112-165">라운드 하는 동안 의료 팀은 모바일 장치에서 팀에 액세스 하 고 목록에서 환자 정보를 업데이트 하 여 팀의 모든 구성원이 동기화 상태를 유지할 수 있습니다. 관리 팀에서 주요 상태 성과 지표에 대해 논의 하 고 평가 하는 데 사용 되는 반올림 세션에서는 대규모 디스플레이 화면에서 팀을 사용 하 여이 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-165">During rounds, the care team access Teams on their mobile devices and update patient information in the list, which everyone on the team can view to stay in sync. At rounding sessions where the care team gathers to discuss and evaluate key health performance metrics to ensure a patient is on the right glide path to discharge, they can share this information using Teams on a large display screen.</span></span> <span data-ttu-id="22112-166">사이트를가지고 있지 않은 팀 구성원은 원격으로 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-166">Care team members who aren't on site can join remotely.</span></span>

<span data-ttu-id="22112-167">다음은 환자 반올림을 위해 설정 된 예제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="22112-167">Here's an example list which was set up for patient rounding.</span></span>

:::image type="content" source="../../media/lists-patients-example.png" alt-text="환자 반올림에 대 한 예제 목록 스크린샷":::

<span data-ttu-id="22112-169">자세히 알아보려면 [팀에서 조직의 목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-169">To learn more, see [Manage the Lists app for your organization in Teams](../../manage-lists-app.md).</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="22112-170">보안 메시지</span><span class="sxs-lookup"><span data-stu-id="22112-170">Secure Messaging</span></span>

<span data-ttu-id="22112-171">안전한 메시징은 새로운 여러 기능을 포함 하 여 주의 팀 내에서 공동 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="22112-171">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="22112-172">메시지 보낸 사람이 메시지에 대 한 특별 한 우선 순위를 설정할 수 있으므로 메시지를 읽을 때까지 받는 사람이 반복적으로 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-172">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="22112-173">메시지 보낸 사람은 읽음 확인을 요청할 수 있으므로 메시지를 받는 사람이 보낸 메시지를 읽었을 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-173">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="22112-174">이러한 기능을 함께 사용 하면 긴급 메시지를 더욱 쉽게 확인 하 고 메시지를 받아서 읽음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-174">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="22112-175">이러한 기능을 사용 하는 새로운 의료 팀은 환자 기준으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-175">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="22112-176">이러한 기능은 정책 기반 이며, 개인 또는 전체 팀에 게 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-176">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="22112-177">자세한 내용은 [의료 기관에 대 한 보안 메시징 정책 시작](messaging-policies-hc.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-177">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="22112-178">보안 메시징과 관련 하 여 의료 기관에서 다른 테 넌 트를 페더레이션 하 여 더 다양 한 테 넌 트 간 통신을 허용 하는 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-178">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="22112-179">( [Microsoft 팀에서 외부 액세스 (페더레이션) 관리](../../manage-external-access.md)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="22112-179">(See [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="22112-180">Firstline Worker 통합</span><span class="sxs-lookup"><span data-stu-id="22112-180">Firstline Worker integration</span></span>

<span data-ttu-id="22112-181">Microsoft 팀은 Firstline Worker와 통합 되어 교대 근무 인력 기능을 조정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22112-181">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span> <span data-ttu-id="22112-182">[Microsoft 팀에서 조직의 교대 근무 앱 관리](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22112-182">See [Manage the Shifts app for your organization in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
