---
title: 교육용 Teams의 인사이트에 대한 IT 관리자 가이드
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams의 인사이트를 관리하는 데 도움이 되는 IT 관리자 가이드입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00bfc5606e23460255e3ee4748010843415eb1b
ms.sourcegitcommit: 92fdfad4564eb27190cd88f109bded2b95d473ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47408234"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a><span data-ttu-id="4fc15-103">교육용 Teams의 인사이트에 대한 IT 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="4fc15-103">IT Admin Guide to Insights in Teams for Education</span></span>

<span data-ttu-id="4fc15-104">교육용 Microsoft Teams의 인사이트를 통해 교육자와 리더는 디지털 참여, 할당 작업량, 등급, 커뮤니케이션 등에 대한 분석 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-104">With Insights in Microsoft Teams for Education, educators and leaders can access analytics data about digital engagement, assignment workload, grades, communication and more.</span></span>

<span data-ttu-id="4fc15-105">Office 365 Education SKUs A1, A3, A5에서 통찰력이 활발합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-105">Insights is active in Office 365 Education SKUs A1, A3, and A5.</span></span>

> [!NOTE]
> <span data-ttu-id="4fc15-106">교육자 여러분, 인사이트를 사용하는 방법을 [여기](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)에서 배워보세요.</span><span class="sxs-lookup"><span data-stu-id="4fc15-106">Educators, learn how to use Insights [here](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).</span></span>

## <a name="permissions"></a><span data-ttu-id="4fc15-107">사용 권한</span><span class="sxs-lookup"><span data-stu-id="4fc15-107">Permissions</span></span>

### <a name="user-types"></a><span data-ttu-id="4fc15-108">사용자 유형</span><span class="sxs-lookup"><span data-stu-id="4fc15-108">User types</span></span>
- <span data-ttu-id="4fc15-109">**학생**은 라이선스로 식별되며 Insights 탭에 액세스 _할 수 없습니다_(팀 소유자인 경우에도).</span><span class="sxs-lookup"><span data-stu-id="4fc15-109">**Students** are identified by their license and _do not have_ access to the Insights tab (even if they are an owner of the team).</span></span> 
- <span data-ttu-id="4fc15-110">**강사**는 교직원용 라이선스로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-110">**Educators** are identified by faculty licenses.</span></span> <span data-ttu-id="4fc15-111">강사는 데이타를 추가하여 인사이트 탭에 표시하려면 교직원용 라이선스가 있어야 하며 수업 팀 소유자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-111">Educators must have a faculty license and be a class team owner to add and see the data presented in the Insights tab.</span></span> 
- <span data-ttu-id="4fc15-112">**리더**는 교직원용 라이선스로 식별되지만, Insights 앱에서 보고서를 보려면 추가로 IT 글로벌 관리자로부터 명시적인 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-112">**Leaders** are also identified by faculty license, but in addition they need explicit permissions from the IT global admin to view the reports in the Insights app.</span></span>
- <span data-ttu-id="4fc15-113">게스트 계정은 Insights에 액세스_할 수 없습니다_.</span><span class="sxs-lookup"><span data-stu-id="4fc15-113">Guest accounts _do not have_ access to Insights.</span></span>

### <a name="permission-levels"></a><span data-ttu-id="4fc15-114">권한 수준</span><span class="sxs-lookup"><span data-stu-id="4fc15-114">Permission levels</span></span>
<span data-ttu-id="4fc15-115">강사와 리더는 다양한 사용 권한 수준 및 논리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-115">Educators and leaders have different permission levels and logic:</span></span>
- <span data-ttu-id="4fc15-116">**강사**는 Teams 앱 모음의 앱으로 이동하여 Insights를 검색하여 수업 팀 내의 공개 채널에 Insights 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-116">**Educators** can add the Insights app to a public channel within a class team by navigating to Apps in the Teams app bar and searching for Insights.</span></span> <span data-ttu-id="4fc15-117">탭에는 소유자가 아닌 수업 팀의 모든 사람(팀의 소유자가 아닌 강사 포함)의 활동이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-117">The tab reflects activity from everyone in the class team who isn’t an owner (including educators who aren’t owners of the team).</span></span> 
- <span data-ttu-id="4fc15-118">**리더**는 Teams 앱 모음에서 앱으로 이동하여 Insights를 검색하여 Insights 앱을 개인 앱으로 추가할 수 있습니다(Teams 왼쪽 메뉴에 표시됨).</span><span class="sxs-lookup"><span data-stu-id="4fc15-118">**Leaders** can add the Insights app as a personal app (appears on Teams left menu) by navigating to Apps in the Teams app bar and searching for Insights.</span></span> 

## <a name="compliance"></a><span data-ttu-id="4fc15-119">규정 준수</span><span class="sxs-lookup"><span data-stu-id="4fc15-119">Compliance</span></span>

<span data-ttu-id="4fc15-120">인사이트는 업계 최고의 규정 준수 의무를 가지고 있으며 Office 365 규정 준수 프레임워크 내에서 Tier-C 서비스로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-120">Insights has industry-leading compliance commitments, and is classified as a Tier-C service within the Office 365 Compliance Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="4fc15-121">[Microsoft 보안 센터](https://www.microsoft.com/trust-center)에 방문하여 Microsoft에서 데이터를 보호하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4fc15-121">Visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center) to learn more about how Microsoft protects your data.</span></span>

## <a name="privacy"></a><span data-ttu-id="4fc15-122">개인 정보</span><span class="sxs-lookup"><span data-stu-id="4fc15-122">Privacy</span></span>

<span data-ttu-id="4fc15-123">인사이트를 통해 수집 및 표시되는 정보는 학생 및 자녀의 보안 및 기타 유사한 개인 정보 관련 규정에 대한 GDPR 및 FERPA(가족교육권 및 개인 정보에 관한 법률)를 포함하여 90개가 넘는 규정과 산업 표준을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-123">The information collected and shown through Insights does meets more than 90 regulatory and industry standards, including GDPR and the Family Education Rights and Privacy Act (FERPA) for the security of students and children and other, similar, privacy-oriented regulations.</span></span> <span data-ttu-id="4fc15-124">IT 관리자는 학생별로 수집된 정보가 수업 환경에서만 사용되도록 의도되었다는 것을 알아야 합니다. 교육자와 리더가 학생의 행동을 결정할 수 있도록 하기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-124">It's important for IT admins to know that the information collected on a per-student basis is intended to be used in a class context only, to allow educators and leaders to determine students' behavior.</span></span> <span data-ttu-id="4fc15-125">이 정보는 수업 모임 참석, 메시지 게시, 친구 게시물에 응답, 과제 작업, 파일 편집 등과 같은 의미 있는 학습 활동을 위해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-125">The information is collected for meaningful learning activities, such as class meetings attendance, posting messages, responding to classmates' posts, working on assignments, editing files, and more.</span></span> <span data-ttu-id="4fc15-126">예를 들어 비공개 채팅 또는 Teams 로그인에 대한 정보는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-126">We don't show information about private chat or a Teams login, as an example.</span></span>

<span data-ttu-id="4fc15-127">Microsoft의 목표는 강사가 참여를 이해하고 학생 교육 과정을 밝게 비추도록 돕는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-127">Our goal is to help educators to understand engagement and shine a spotlight on student learning.</span></span> <span data-ttu-id="4fc15-128">이러한 수업 활동은 학생 수준의 작업에 초점을 맞출 수 있지만 Microsoft Teams에서는 이러한 작업에 할당한 긍정적 또는 부정적 가치가 없으며 기준에 따라 학생 개인을 판단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-128">While these class activities can be focused down to actions at the student level, there is no positive or negative value assigned to these actions by Microsoft Teams, and there is no judgmental identification of individual students based on criteria.</span></span> <span data-ttu-id="4fc15-129">예를 들어, 인사이트의 정보는 교육자에게 학생이 특정 기간 동안 도구에서 활동을 하지 않았거나 지난 주에 정시에 모든 과제를 완료했다고 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-129">The information in  Insights informs an educator that, for example, a student has not been active in the tool during a certain period in time, or has completed all their assignments last week on-time.</span></span> <span data-ttu-id="4fc15-130">학생과 학생의 가족 또는 보호자와 상호 작용하여 탐색된 활동 또는 비활동의 근본적인 원인을 파악하는 것은 강사의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-130">It remains the responsibility of the educator to interact with the student and that student's family or guardians to determine the underlying reason for any activity or inactivity detected.</span></span>

## <a name="data-collection"></a><span data-ttu-id="4fc15-131">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="4fc15-131">Data collection</span></span>

- <span data-ttu-id="4fc15-132">테넌트에 대해 교육 분석을 설정하면 인사이트에 대한 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-132">We collect data for Insights when Education Analytics is turned on for the tenant.</span></span> <span data-ttu-id="4fc15-133">데이터는 교육 및 학습에 대한 실행 가능한 정보를 표시하기 위해 Teams 활동에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-133">The data is collected from Teams activity in order to surface actionable insights for teaching and learning.</span></span>
- <span data-ttu-id="4fc15-134">게스트 데이터는 수집되지 _않습니다_.</span><span class="sxs-lookup"><span data-stu-id="4fc15-134">Guests data _does not_ collected for Insights.</span></span>
- <span data-ttu-id="4fc15-135">기본적으로 Education Analytics는 **켜져** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-135">By default, Education Analytics is turned **On**.</span></span>

<span data-ttu-id="4fc15-136">현재 이 데이터는 다음과 같은 수업 팀의 학생과 강사 활동 영역에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-136">Currently, this data is pulled from the following areas of student and educator activity in class teams:</span></span>

|<span data-ttu-id="4fc15-137">팀 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4fc15-137">Teams component</span></span>  |<span data-ttu-id="4fc15-138">수집된 데이터</span><span class="sxs-lookup"><span data-stu-id="4fc15-138">Data collected</span></span>  |
|-----------------|------------------------|------------------------|
|<span data-ttu-id="4fc15-139">과제</span><span class="sxs-lookup"><span data-stu-id="4fc15-139">Assignments</span></span> |<span data-ttu-id="4fc15-140">과제 열기, 제출, 점수 지정</span><span class="sxs-lookup"><span data-stu-id="4fc15-140">Opening, turning in, and grade on assignments.</span></span> |
|<span data-ttu-id="4fc15-141">채널 참여</span><span class="sxs-lookup"><span data-stu-id="4fc15-141">Channel engagement</span></span> |<span data-ttu-id="4fc15-142">채널 방문, 게시물 작성, 게시물 응답 및 좋아요(채팅 콘텐츠 제외)</span><span class="sxs-lookup"><span data-stu-id="4fc15-142">Visiting a channel, creating a post, replying to and liking a post (not including chat content).</span></span> |
|<span data-ttu-id="4fc15-143">파일</span><span class="sxs-lookup"><span data-stu-id="4fc15-143">Files</span></span> |<span data-ttu-id="4fc15-144">파일 업로드, 다운로드, 액세스, 수정, 댓글 달기, 공유(파일 콘텐츠 제외)</span><span class="sxs-lookup"><span data-stu-id="4fc15-144">Uploading, downloading, accessing, modifying, commenting on, and sharing a file (not including file content).</span></span> |
|<span data-ttu-id="4fc15-145">모임</span><span class="sxs-lookup"><span data-stu-id="4fc15-145">Meetings</span></span> |<span data-ttu-id="4fc15-146">참석(모임 콘텐츠 제외)</span><span class="sxs-lookup"><span data-stu-id="4fc15-146">Attendance (not including meeting content).</span></span> |

## <a name="data-location"></a><span data-ttu-id="4fc15-147">데이터 위치</span><span class="sxs-lookup"><span data-stu-id="4fc15-147">Data location</span></span>

<span data-ttu-id="4fc15-148">유럽 기반 테넌트에 대한 통찰력 데이터는 유럽의 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-148">Insights data for European-based tenants is stored on servers in Europe.</span></span> <span data-ttu-id="4fc15-149">미국 기반 테넌트용 데이터는 미국의 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-149">Data for US-based tenants is stored on servers in the United States.</span></span> <span data-ttu-id="4fc15-150">인사이트를 사용하고 있으며 Office 365 테넌트가 유럽 또는 미국 외부 지역에 있는 경우, 데이터는 해당 지역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-150">If you use Insights and your Office 365 tenant is in a region outside of Europe or the United States, your data will be stored in the appropriate geographic region.</span></span>

## <a name="performance-and-reliability"></a><span data-ttu-id="4fc15-151">성능과 신뢰성</span><span class="sxs-lookup"><span data-stu-id="4fc15-151">Performance and reliability</span></span>

<span data-ttu-id="4fc15-152">인사이트는 Teams 활동에서 수집된 대량의 데이터를 최적의 성능과 안정성으로 처리하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-152">Insights is designed to handle a high volume of data collected from Teams activity with optimal performance and reliability.</span></span>

<span data-ttu-id="4fc15-153">데이터 수집 프로세스는 팀에 인사이트 탭 설치와 관계없이 별도의 서버에서 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-153">The data collection process takes place on separate servers regardless of the installation of the Insights tab in Teams.</span></span> <span data-ttu-id="4fc15-154">인사이트 탭 또는 개인 앱은 나머지 Teams 기능을 사용하는 교육자와 학생의 응용 프로그램 성능 또는 네트워크 대역폭에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-154">The Insights tab or personal app does not affect application performance or network bandwidth for educators and students using the rest of Teams functionality.</span></span>

> [!TIP]
> <span data-ttu-id="4fc15-155">[여기](edu-remote-low-bandwidth.md)에서 대역폭이 낮으면 교육용 Teams를 사용하는 방법에 대해 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="4fc15-155">Read [here](edu-remote-low-bandwidth.md) about using Teams for Education when bandwidth is low.</span></span>

## <a name="how-to-delete-your-data"></a><span data-ttu-id="4fc15-156">데이터 삭제 방법</span><span class="sxs-lookup"><span data-stu-id="4fc15-156">How to delete your data</span></span>

<span data-ttu-id="4fc15-157">교육 서비스는 수업 팀 컨텍스트에서 수행된 학생과 강사 활동을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-157">Education services stores student and educator actions performed in the context of a class team.</span></span> <span data-ttu-id="4fc15-158">이 데이터는 통합된 데이터 집합으로 간주하므로 조직에서 학생 또는 강사 사용자 계정을 삭제한 후에도 서비스에서 자동으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-158">This data is considered a co-mingled data set and therefore isn't automatically deleted from the service once student or educator user accounts are deleted from your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="4fc15-159">데이터를 삭제하면 시간이 지남에 따라 수업 팀 참여를 분석하는 Insights의 기능에 부정적인 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-159">Deleting data has a negative impact on Insights' ability to analyze class team engagement over time.</span></span>

- <span data-ttu-id="4fc15-160">[여기](https://edusupport.microsoft.com/support)에서 지원 티켓을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-160">Open a support ticket [here](https://edusupport.microsoft.com/support).</span></span> <span data-ttu-id="4fc15-161">지원 티켓은 GDPR 삭제 DSR 작업 요청을 명확하게 명시해야 하며 삭제할 개체 ID를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-161">The support ticket must state clearly the request for a GDPR Delete DSR operation and contain the user object ID to be deleted.</span></span> <span data-ttu-id="4fc15-162">삭제의 데이터 집합 또는 시간 창을 제한할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-162">There is no ability to limit the data set or time window of the deletion.</span></span>
- <span data-ttu-id="4fc15-163">일단 제출되면 지원 티켓은 규정 준수 최소 보존 정책을 충족하기 위해 일주일 동안 큐에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-163">Once filed, the support ticket waits in the queue for one week in order to meet compliance minimal retention policy.</span></span> <span data-ttu-id="4fc15-164">이 기간에는 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-164">You have the opportunity to cancel the operation during this time.</span></span>
- <span data-ttu-id="4fc15-165">일주일 후에는 Education Analytics 팀에서 사용자 ID와 관련된 모든 데이터를 서비스에서 삭제하는 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-165">After one week, the Education Analytics team takes action to ensure all data related to the user ID is deleted from the service.</span></span> <span data-ttu-id="4fc15-166">Microsoft 지원에서는 ICM 티켓을 모니터링하여 삭제 프로세스가 완료되면 28일 이내에 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-166">Microsoft support monitors the ICM ticket and will notify you once the deletion process is complete, in no more than 28 days.</span></span>

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a><span data-ttu-id="4fc15-167">SDS(학교 데이터 동기화)를 사용하여 Insights를 켜고 끕니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-167">Turn Insights off and on using School Data Sync (SDS)</span></span>

<span data-ttu-id="4fc15-168">SDS(학교 데이터 동기화)는 SIS(학생 정보 시스템) 데이터를 가져오고 Office 365와 동기화하는 프로세스를 자동화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-168">School Data Sync (SDS) helps to automate the process of importing and synchronizing Student Information System (SIS) data with Office 365.</span></span>

<span data-ttu-id="4fc15-169">인사이트를 사용하기 위해서는 SDS를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-169">The use of Insights does not require the use of SDS.</span></span> <span data-ttu-id="4fc15-170">그러나 **설정** > **Education Analytics 관리**의 SDS 관리 센터에서 토글을 꺼서 언제든지 Education Analytics를 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-170">However, you may choose to opt out from Education Analytics at any time by turning off the toggle in the SDS Admin Center under **Settings** > **Manage Education Analytics**.</span></span>

:::image type="content" source="media/class-insights-on-off.png" alt-text="인사이트를 사용하거나 사용하지 않도록 설정하는 켜기-끄기 스위치입니다.":::

<span data-ttu-id="4fc15-172">기본적으로 교육 분석, 즉 정보 활용이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-172">By default, Education Analytics, and therefore Insights, is turned on.</span></span> <span data-ttu-id="4fc15-173">분석에서 손을 떼면 인사이트 탭에 대해 수집된 모든 데이터가 삭제됩니다. 분석을 다시 설정하면 데이터를 다시 활성화할 때부터 수집하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc15-173">When you opt out of Analytics, we delete all data collected for the Insights tab. Turn Analytics back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="4fc15-174">자세한 정보: [인사이트에 대한 강사의 가이드](https://support.microsoft.com/ko-KR/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)</span><span class="sxs-lookup"><span data-stu-id="4fc15-174">Learn more: [Educator's guide to Insights](https://support.microsoft.com/ko-KR/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)</span></span>
