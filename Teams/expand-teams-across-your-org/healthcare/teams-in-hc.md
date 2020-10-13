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
description: 주의 조정, 보안 메시지, 가상 방문, EHR 통합,에서 일선 worker 시스템 통합을 포함 하는 상태 관리 기능에 대해 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03de58e9fef94dcf63649920cde5a3663a25889e
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433061"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="980ba-103">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="980ba-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="980ba-104">Microsoft 팀은 병원 및 기타 의료 단체에 유용한 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="980ba-105">팀 기능은 다음을 지원 하기 위해 개발 중에 병원.</span><span class="sxs-lookup"><span data-stu-id="980ba-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="980ba-106">세심 한 조정 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="980ba-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="980ba-107">보안 메시지</span><span class="sxs-lookup"><span data-stu-id="980ba-107">Secure Messaging</span></span>
- <span data-ttu-id="980ba-108">가상 방문</span><span class="sxs-lookup"><span data-stu-id="980ba-108">Virtual Visit</span></span>
- <span data-ttu-id="980ba-109">EHR (전자 건강 보험 기록) 통합</span><span class="sxs-lookup"><span data-stu-id="980ba-109">Electronic Healthcare Record (EHR) integration</span></span>
- <span data-ttu-id="980ba-110">Firstline Worker 시스템 통합</span><span class="sxs-lookup"><span data-stu-id="980ba-110">Firstline Worker system integration</span></span>

<span data-ttu-id="980ba-111">이 섹션의 내용은 모임, 통화, 메시징과 같은 팀의 기본 기능을 기반으로 하며 조직에 이미 팀을 배포한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="980ba-112">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](../../How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="980ba-113">의료 협조-Microsoft 팀 환자 앱</span><span class="sxs-lookup"><span data-stu-id="980ba-113">Care Coordination - Microsoft Teams Patients app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="980ba-114">**2020 년 10 월 30 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="980ba-114">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="980ba-115">환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-115">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="980ba-116">환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-116">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="980ba-117">현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-117">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="980ba-118">[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-118">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="980ba-119">목록에서 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져오면 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-119">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="980ba-120">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-120">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="980ba-121">Microsoft 팀에는 이제 건강 보험 조직과 관련 된 의료 협조 솔루션을 포함 하 고 있으며,이를 통해 가장 좋은 환자를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-121">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="980ba-122">의료 코디 네이션 솔루션의 crux (Microsoft 팀 환자 앱)는 빠른 의료 상호 운용성 리소스 ([Fto r](https://www.hl7.org/fhir/)) 인터페이스를 사용 하 여 microsoft 팀에 연결 되어 있으며, 임상 공동 작업 및 의사 소통을 가능 하 게 하는 유용한 의료 정보를 컨텍스트로 통합 하는 제 1 자 탭 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-122">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="980ba-123">의료 코디 네이션 솔루션은 HL7v2 및 FA r과 같은 기존 상태 데이터 표준을 사용 하 여 환자 앱을 EHR 시스템에 연결할 수 있는 선두 독립 소프트웨어 공급 업체 (Isv)와 인터페이스 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-123">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="980ba-124">Microsoft는 다음 업계 리더와 협력 하 여 팀과 전자 상태 레코드 통합을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-124">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="980ba-125">Datica ( [CMI](https://datica.com/compliant-managed-integration/) 제공)</span><span class="sxs-lookup"><span data-stu-id="980ba-125">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="980ba-126">Cloverleaf ( [INFOR FA r 브리지](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)를 통해)</span><span class="sxs-lookup"><span data-stu-id="980ba-126">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="980ba-127">Redox ( [r ^ FA r 서버](https://www.redoxengine.com/fhir/)통과)</span><span class="sxs-lookup"><span data-stu-id="980ba-127">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="980ba-128">Dapasoft ( [FA r의 Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="980ba-128">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="980ba-129">건강 관리 기관에 대 한 Microsoft 팀을 구현 하는 EHR 통합 및 interop 파트너는 환자 앱에 의료 공급자 조직의 EHR 시스템에 대 한 보안 및 인증 된 연결을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-129">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="980ba-130">이렇게 하면 관련 환자 레코드의 단방향 (읽기 전용) 흐름을 환자 앱으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-130">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="980ba-131">환자 앱은 f r 형식을 인식 하므로, 파트너는 HL7v2 등의 다양 한 다른 형식에서 집계 된 데이터를 FTO r DSTU2 또는 STU3으로 변환 하는 역할도 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-131">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<span data-ttu-id="980ba-132">환자 앱은 EHR (전자 상태 레코드) 시스템과 통합 되며 의사 공급자가 팀의 보안 플랫폼 내에서 실시간으로 환자를 처리할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-132">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams' secure platform.</span></span> <span data-ttu-id="980ba-133">환자 앱은 다음과 같은 문제를 해결 하기 위해 주의 조정 영역에서 첫 번째 주요 투자입니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-133">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="980ba-134">환자 경험을 통한 저렴 하 고 중요 한 의사 소통으로 인 한 효율성 향상</span><span class="sxs-lookup"><span data-stu-id="980ba-134">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="980ba-135">Siloed 관리 burdens를 생성 하는 정보</span><span class="sxs-lookup"><span data-stu-id="980ba-135">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="980ba-136">복잡 하 고 단편화 된 공동 작업 도구로 clinicians 간의 불만</span><span class="sxs-lookup"><span data-stu-id="980ba-136">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="980ba-137">너무 많은 비 리소스 임상 시간을 구울 수 있는 비효율적인 개인 관리 지원 조정</span><span class="sxs-lookup"><span data-stu-id="980ba-137">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="980ba-138">Microsoft 팀은 의사, clinicians, nurses, 기타 직원이 다음과 같이 효율적으로 공동 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-138">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="980ba-139">Office 문서에서 작동 하 고 공동 작업 하는 단일 가상화 된 팀의 일부</span><span class="sxs-lookup"><span data-stu-id="980ba-139">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="980ba-140">다른 환자에 대 한 지속적인 대화를 통해 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-140">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="980ba-141">탭에서 채널을 사용 하 여 작업을 구조화 하는 방법으로, 정보 원본을 고정 하는 탭의 추가 도움말을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-141">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="980ba-142">팀의 오디오, 비디오, 화면 공유, 기록, 내용 기능을 통해 채널 모임을 사용 하 여 일일 모임 관리</span><span class="sxs-lookup"><span data-stu-id="980ba-142">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="980ba-143">환자 앱을 사용 하 여 모니터링 해야 하는 위험성이 높은 환자 목록을 만들고 EHR 시스템에서 최신 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-143">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="980ba-144">환자 앱 자체는 Microsoft 팀에 다음 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-144">The Patients app itself adds the following features to Microsoft Teams:</span></span>
  - <span data-ttu-id="980ba-145">단일 채널 내에서 여러 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-145">Ability to create multiple patient lists within a single channel.</span></span>
  - <span data-ttu-id="980ba-146">구성 가능한 열을 통해 환자에 대해 표시 되는 정보를 보고 정렬 하는 기능.</span><span class="sxs-lookup"><span data-stu-id="980ba-146">Ability to view and sort information displayed about patients through configurable columns.</span></span>
  - <span data-ttu-id="980ba-147">팀 템플릿을 통해 앱을 자동으로 프로 비전 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-147">Ability to auto-provision the app through a team template.</span></span>
  - <span data-ttu-id="980ba-148">IOS 및 Android 용 팀 앱에서 모바일 최초의 의료 근로자와 Microsoft 팀 웹 및 데스크톱 클라이언트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-148">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
  - <span data-ttu-id="980ba-149">준수 문의 구문 분석을 통해 FDSTU2 및 STU3 버전에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="980ba-149">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
  - <span data-ttu-id="980ba-150">모든 보기 및 검색 작업에 대 한 감사 로그를 사용 하 여 HIPAA의 모든 사용자 인터페이스를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-150">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="980ba-151">환자 앱은 팀 확장성 플랫폼을 기반으로 하며, 탭 프레임 워크를 활용 하 여 채널 내에서 다양 한 환자 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-151">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="980ba-152">다른 팀 앱과 플랫폼 자체에 대해 자세히 알아보려면 [Microsoft 팀 용 앱](/microsoftteams/platform/concepts/apps/apps-overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-152">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="980ba-153">환자 앱은 비공개 preview이 고 FTO r 인터페이스는 beta입니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-153">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="980ba-154">릴리스 버전은 이전 버전과 호환 되지 않을 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-154">Released versions are not expected to be backward compatible.</span></span>

![데스크톱 및 모바일 장치에서 환자 앱 스크린샷](../../media/ehr-2.png)

<span data-ttu-id="980ba-156">구현 세부 정보는 [Microsoft 팀에 전자 의료 기록 통합](patients-app.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-156">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="teams-templates"></a><span data-ttu-id="980ba-157">팀 서식 파일</span><span class="sxs-lookup"><span data-stu-id="980ba-157">Teams templates</span></span>

<span data-ttu-id="980ba-158">팀을 만들기 위한 새 템플릿이 병원 설정에 적용 되도록 개발 되었고 더 많은 내용이 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-158">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="980ba-159">이를 통해 의료 근로자가 다양 한 부서나 wards의 환자을 조정 하는 데 사용 하는 팀을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-159">This makes it easier to create teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="980ba-160">[의료 조직의 팀 서식 파일 시작을](healthcare-templates.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-160">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="980ba-161">팀은 cardiology 등의 내부 부서를 위해 시작 하거나 주의를 wards 하 고 더 많은 서식 파일을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-161">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="lists-app"></a><span data-ttu-id="980ba-162">목록 앱</span><span class="sxs-lookup"><span data-stu-id="980ba-162">Lists app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="980ba-163">팀의 목록 앱은 팀에서 정보를 추적 하 고 작업을 구성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-163">The Lists app in Teams helps teams track information and organize work.</span></span> <span data-ttu-id="980ba-164">앱은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-164">The app is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="980ba-165">목록은 미리 정의 된 서식 파일에서 만들거나 Excel로 데이터를 가져와 처음부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-165">Lists can be created from scratch, from predefined templates, or by importing data to Excel.</span></span>

<span data-ttu-id="980ba-166">관리 팀에서 환자 서식 파일을 사용 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-166">Care teams can use the Patients template to get started.</span></span> <span data-ttu-id="980ba-167">환자의 요구 및 상태를 추적 하는 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-167">They can create lists to track the needs and status of patients.</span></span> <span data-ttu-id="980ba-168">팀에서 Excel 스프레드시트의 기존 환자 데이터를 가져와 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-168">Existing patient data on Excel spreadsheets can be brought in to create a list in Teams.</span></span> <span data-ttu-id="980ba-169">이러한 목록은 라운드 및 환자 모니터링과 같은 시나리오에 사용 하 여 주의를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-169">These lists can be used for scenarios such as rounds and patient monitoring to coordinate care.</span></span>

<span data-ttu-id="980ba-170">예를 들어, 청구 nurse는 모든 의료 팀 구성원을 포함 하는 환자 목록을 팀에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-170">For example, a charge nurse creates a patient list in a team that includes all care team members.</span></span> <span data-ttu-id="980ba-171">라운드 하는 동안 의료 팀은 모바일 장치에서 팀에 액세스 하 고 목록에서 환자 정보를 업데이트 하 여 팀의 모든 구성원이 동기화 상태를 유지할 수 있습니다. 관리 팀에서 주요 상태 성과 지표에 대해 논의 하 고 평가 하는 데 사용 되는 반올림 세션에서는 대규모 디스플레이 화면에서 팀을 사용 하 여이 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-171">During rounds, the care team access Teams on their mobile devices and update patient information in the list, which everyone on the team can view to stay in sync. At rounding sessions where the care team gathers to discuss and evaluate key health performance metrics to ensure a patient is on the right glide path to discharge, they can share this information using Teams on a large display screen.</span></span> <span data-ttu-id="980ba-172">사이트를가지고 있지 않은 팀 구성원은 원격으로 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-172">Care team members who aren't on site can join remotely.</span></span>

<span data-ttu-id="980ba-173">다음은 환자 반올림을 위해 설정 된 예제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-173">Here's an example list which was set up for patient rounding.</span></span>

:::image type="content" source="../../media/lists-patients-example.png" alt-text="환자 반올림에 대 한 예제 목록 스크린샷":::

<span data-ttu-id="980ba-175">자세히 알아보려면 [팀에서 조직의 목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-175">To learn more, see [Manage the Lists app for your organization in Teams](../../manage-lists-app.md).</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="980ba-176">보안 메시지</span><span class="sxs-lookup"><span data-stu-id="980ba-176">Secure Messaging</span></span>

<span data-ttu-id="980ba-177">안전한 메시징은 새로운 여러 기능을 포함 하 여 주의 팀 내에서 공동 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-177">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="980ba-178">메시지 보낸 사람이 메시지에 대 한 특별 한 우선 순위를 설정할 수 있으므로 메시지를 읽을 때까지 받는 사람이 반복적으로 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-178">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="980ba-179">메시지 보낸 사람은 읽음 확인을 요청할 수 있으므로 메시지를 받는 사람이 보낸 메시지를 읽었을 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-179">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>

<span data-ttu-id="980ba-180">이러한 기능을 함께 사용 하면 긴급 메시지를 더욱 쉽게 확인 하 고 메시지를 받아서 읽음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-180">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="980ba-181">이러한 기능을 사용 하는 새로운 의료 팀은 환자 기준으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-181">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="980ba-182">이러한 기능은 정책 기반 이며, 개인 또는 전체 팀에 게 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-182">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="980ba-183">자세한 내용은 [의료 기관에 대 한 보안 메시징 정책 시작](messaging-policies-hc.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-183">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="980ba-184">보안 메시징과 관련 하 여 의료 기관에서 다른 테 넌 트를 페더레이션 하 여 더 다양 한 테 넌 트 간 통신을 허용 하는 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-184">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="980ba-185">( [Microsoft 팀에서 외부 액세스 (페더레이션) 관리](../../manage-external-access.md)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="980ba-185">(See [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="980ba-186">Firstline Worker 통합</span><span class="sxs-lookup"><span data-stu-id="980ba-186">Firstline Worker integration</span></span>

<span data-ttu-id="980ba-187">Microsoft 팀은 Firstline Worker와 통합 되어 교대 근무 인력 기능을 조정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980ba-187">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span> <span data-ttu-id="980ba-188">[Microsoft 팀에서 조직의 교대 근무 앱 관리](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980ba-188">See [Manage the Shifts app for your organization in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
