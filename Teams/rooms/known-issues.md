---
title: 알려진 문제
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 관리자는 업데이트, 사용자 인터페이스, 하드웨어, 제한 사항, 예상 동작 등 Microsoft 팀 대화방의 알려진 문제 목록에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1083ceb040f173aeef0a8a60d56a888a6b8fdb17
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874455"
---
# <a name="known-issues"></a><span data-ttu-id="b994c-103">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b994c-103">Known issues</span></span> 
 
<span data-ttu-id="b994c-104">이 문서에는 Microsoft 팀 대화방의 알려진 문제점에 대 한 기능 영역별로 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-104">This article lists the known issues for Microsoft Teams Rooms, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="b994c-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="b994c-105"><a name="update"> </a></span></span>  
## <a name="update"></a><span data-ttu-id="b994c-106">Update</span><span class="sxs-lookup"><span data-stu-id="b994c-106">Update</span></span> 

| <span data-ttu-id="b994c-107">문제 제목</span><span class="sxs-lookup"><span data-stu-id="b994c-107">Issue title</span></span> |  <span data-ttu-id="b994c-108">동작 \/ 증상</span><span class="sxs-lookup"><span data-stu-id="b994c-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="b994c-109">알려진 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b994c-109">Known workaround</span></span> | <span data-ttu-id="b994c-110">기술 자료 문서</span><span class="sxs-lookup"><span data-stu-id="b994c-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
| <span data-ttu-id="b994c-111">응용 프로그램이 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="b994c-111">Application not launching</span></span> |  <span data-ttu-id="b994c-112">응용 프로그램 버전 4.4.41.0로 업데이트 한 후 시스템에서 검은색 화면으로 부팅 하거나 몇 분 후에 로그온 화면으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-112">After updating to application version 4.4.41.0, the system boots to black screen, or go to the logon screen after few minutes.</span></span> | <span data-ttu-id="b994c-113">이 문제를 해결 하려면 Microsoft 팀 대화방의 단계를 수행 하 여 [버전 4.4.41.0로 업데이트 한 후 응용 프로그램을 시작 하지](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-113">Follow the steps in [Microsoft Teams Rooms application does not start after update to version 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) to fix this issue.</span></span>  | <span data-ttu-id="b994c-114">없음</span><span class="sxs-lookup"><span data-stu-id="b994c-114">None</span></span> |
|  <span data-ttu-id="b994c-115">앱이 만료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-115">App out of date</span></span>         |    <span data-ttu-id="b994c-116">Microsoft 팀 회의실 콘솔에 "시스템 구성 오래 됨" 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-116">The Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="b994c-117">Microsoft 팀 대화방 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="b994c-117">Use the Microsoft Teams Rooms recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="b994c-118">없음</span><span class="sxs-lookup"><span data-stu-id="b994c-118">None</span></span> |
|  <span data-ttu-id="b994c-119">장치가 지원 되지 않는 버전의 Windows 10으로 업데이트 됨</span><span class="sxs-lookup"><span data-stu-id="b994c-119">Device updated to unsupported version of Windows 10</span></span>   |    <span data-ttu-id="b994c-120">Windows 10 장치가 버전 1803에서 버전 1809 (지원 되지 않음)로 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-120">Windows 10 device updated from version 1803 to version 1809, which is not supported.</span></span> <span data-ttu-id="b994c-121">지원 되는 버전은 1903입니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-121">The supported version is 1903.</span></span> |   <span data-ttu-id="b994c-122">이 문제는 지정 된 일 수 동안 기능 업데이트를 지연할 수 있는 [DeferFeatureUpdatesPeriodinDays setting에 대 한 그룹 정책 또는 MDM 설정이](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) 최대 365 일로 설정 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-122">This can happen if the [Group Policy or MDM setting for DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) setting, which lets you defer feature updates for a specified number of days, is set to the maximum of 365 days.</span></span> <br><br> <span data-ttu-id="b994c-123">Windows 10 버전 1809는 Microsoft 팀 대화방에서 지원 되지 않으며 버전 1903이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-123">Windows 10 version 1809 isn't supported with Microsoft Teams Rooms, while version 1903 is supported.</span></span> <span data-ttu-id="b994c-124">그러나, 3 월 27 일 현재 2020 버전 1809은 365 일이 하를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-124">However, as of March 27, 2020, version 1809 is over 365 days old.</span></span> <span data-ttu-id="b994c-125">이 설정이 변경 되지 않으면 Windows에서 버전 1809를 설치 하려고 시도 하며,이 경우 Microsoft 팀 대화방에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-125">If this setting isn't changed, Windows attempts to install version 1809, which may cause issues with Microsoft Teams Rooms.</span></span><br><br><span data-ttu-id="b994c-126">이 문제를 방지 하려면 업데이트 지연에 대 한 그룹 정책 또는 MDM 설정을 **제거** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-126">To avoid this situation, **remove** any Group Policy or MDM setting for deferring updates.</span></span> <span data-ttu-id="b994c-127">이렇게 하면 Windows에서 지원 되는 최신 OS 버전으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-127">This allows Windows to update to the latest, supported OS version.</span></span> <br><br><span data-ttu-id="b994c-128">**중요** 그룹 정책 또는 MDM 설정을 **제거** (왼쪽에 구성 취소) 하 고 **0으로 설정 하지**않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-128">**IMPORTANT** The Group Policy or MDM setting must be **removed** (left unconfigured) and **not set to 0**.</span></span> <span data-ttu-id="b994c-129">정책이 0으로 설정 되 면 Windows에서 지원 되지 않을 수 있는 최신 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-129">If the policy is set to 0, Windows takes the latest available version which may not be supported.</span></span> |  <span data-ttu-id="b994c-130">없음</span><span class="sxs-lookup"><span data-stu-id="b994c-130">None</span></span> |



<span data-ttu-id="b994c-131"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="b994c-131"><a name="OS-conflicts"> </a></span></span>  
## <a name="user-interface"></a><span data-ttu-id="b994c-132">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b994c-132">User interface</span></span> 

| <span data-ttu-id="b994c-133">문제 제목</span><span class="sxs-lookup"><span data-stu-id="b994c-133">Issue title</span></span> |  <span data-ttu-id="b994c-134">동작 \/ 증상</span><span class="sxs-lookup"><span data-stu-id="b994c-134">Behavior \/ Symptom</span></span> | <span data-ttu-id="b994c-135">알려진 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b994c-135">Known workaround</span></span> | <span data-ttu-id="b994c-136">기술 자료 문서</span><span class="sxs-lookup"><span data-stu-id="b994c-136">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="b994c-137">가상 키보드가 없음</span><span class="sxs-lookup"><span data-stu-id="b994c-137">Virtual keyboard missing</span></span>   | <span data-ttu-id="b994c-138">Microsoft 팀 대화방에 정보를 입력 해야 하는 경우 가상 키보드가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-138">The virtual keyboard doesn't appear when you need to enter information in Microsoft Teams Rooms.</span></span> <span data-ttu-id="b994c-139">이 문제는 Windows 10 버전 1903에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-139">This issue occurs in Windows 10, version 1903.</span></span> | <span data-ttu-id="b994c-140">Windows 10에 대 한 2020-04 누적 업데이트 설치, x64 기반 시스템에 대 한 windows 업데이트 (버전 1903)</span><span class="sxs-lookup"><span data-stu-id="b994c-140">Install 2020-04 Cumulative Update for Windows 10, version 1903 for x64-based Systems through Windows Updates.</span></span>  | <span data-ttu-id="b994c-141">없음</span><span class="sxs-lookup"><span data-stu-id="b994c-141">None</span></span> | 

<span data-ttu-id="b994c-142"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="b994c-142"><a name="Hardware"> </a></span></span>  
## <a name="hardware"></a><span data-ttu-id="b994c-143">하드웨어</span><span class="sxs-lookup"><span data-stu-id="b994c-143">Hardware</span></span>

| <span data-ttu-id="b994c-144">문제 제목</span><span class="sxs-lookup"><span data-stu-id="b994c-144">Issue title</span></span> |  <span data-ttu-id="b994c-145">동작 \/ 증상</span><span class="sxs-lookup"><span data-stu-id="b994c-145">Behavior \/ Symptom</span></span> | <span data-ttu-id="b994c-146">알려진 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b994c-146">Known workaround</span></span> | <span data-ttu-id="b994c-147">기술 자료 문서</span><span class="sxs-lookup"><span data-stu-id="b994c-147">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="b994c-148">감지 되지 않은 모니터</span><span class="sxs-lookup"><span data-stu-id="b994c-148">Monitors not detected</span></span> | <span data-ttu-id="b994c-149">Surface Pro (모델 2017) 장치에서 Microsoft 팀 대화방을 실행 하면 모니터가 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-149">When you run Microsoft Teams Rooms on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="b994c-150">Surface Pro 전원 단추를 20 초 이상 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-150">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="b994c-151">이렇게 하면 장치가 다시 시작 되 고 그래픽 캐시가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-151">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="b994c-152">KB4055681</span><span class="sxs-lookup"><span data-stu-id="b994c-152">KB4055681</span></span>](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<span data-ttu-id="b994c-153"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="b994c-153"><a name="Limits"> </a></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="b994c-154">제한 사항 및 예상 동작</span><span class="sxs-lookup"><span data-stu-id="b994c-154">Limitations and expected behaviors</span></span>

***

<span data-ttu-id="b994c-155">Microsoft 팀 대화방은 HDMI 수집 기능 (비디오, 오디오)에 문제가 발생 하는 데 관측 된 HDCP 입력을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-155">Microsoft Teams Rooms does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="b994c-156">Microsoft 팀 대화방에 연결 된 스위치에 HDCP 옵션이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-156">Take care to ensure that switches connected to Microsoft Teams Rooms have HDCP options turned off.</span></span> 

***

<span data-ttu-id="b994c-157">원본에서 대기 모드를 해제할 때 자동으로 활성 비디오 원본 (예: MTR 콘솔)으로 전환 하려면 특정 조건이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-157">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="b994c-158">이 기능은 선택 사항 이지만 Microsoft 팀 공간 소프트웨어에서 지원 되며, 기본 하드웨어에서 기능을 지 원하는 경우 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-158">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="b994c-159">채팅방 표시로 사용 되는 소비자 TV는 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-159">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="b994c-160">선택 된 dock 또는 console (CEC를 지원 하지 않을 수 있음) (제조업체 지원 문서 참조)에 따라 원하는 동작을 사용 하도록 설정 하려면 [HD CTL 100의 extron](https://www.extron.com/article/hdctl100ad) 작업 영역 컨트롤러가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-160">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a workspace controller such as an [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) may be needed to enable the desired behavior.</span></span> 

***

<span data-ttu-id="b994c-161">항상 유선 1 Gbps 네트워크 연결을 사용 하 여 필요한 대역폭을 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-161">Always use a wired 1-Gbps network connection to assure you have the needed bandwidth.</span></span> 

***

<span data-ttu-id="b994c-162">Microsoft 팀 대화방 장치가 도메인에서 신뢰를 상실 한 경우에는 디바이스에 인증 하 고 설정을 열 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-162">If your Microsoft Teams Rooms device loses trust with the domain, you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="b994c-163">예를 들어 도메인에 가입한 후 도메인에서 Microsoft 팀 대화방을 제거 하면 신뢰가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-163">For example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined, trust is lost.</span></span> <span data-ttu-id="b994c-164">해결 방법은 로컬 관리자 계정으로 로그인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-164">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="b994c-165">Microsoft 팀 대화방은 다중 창 응용 프로그램 이므로 장치의 HDMI 포트에 연결 하 여 앱이 올바르게 작동 하도록 하는 방 디스플레이가 앞에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-165">Microsoft Teams Rooms is a multi-window application and requires a front of room display to be connected to the HDMI port of the device, for the app to function correctly.</span></span> <span data-ttu-id="b994c-166">테스트 하는 경우에는 HDMI 디스플레이가 연결 되어 있는지 확인 하 고, 아직 표시를 구매 하지 않은 경우에는 dummy HDMI 플러그를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b994c-166">Make sure that you either have an HDMI display connected or use a dummy HDMI plug if you are testing and do not have a display purchased yet.</span></span>
***
<span data-ttu-id="b994c-167"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="b994c-167"><a name="See"> </a></span></span>  
## <a name="see-also"></a><span data-ttu-id="b994c-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b994c-168">See also</span></span>

[<span data-ttu-id="b994c-169">Microsoft 팀 대화방 도움말</span><span class="sxs-lookup"><span data-stu-id="b994c-169">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="b994c-170">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="b994c-170">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
