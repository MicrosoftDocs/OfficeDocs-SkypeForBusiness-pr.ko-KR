---
title: Microsoft 팀 대화방 관리 개요
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft 팀 대화방 관리 개요.
ms.openlocfilehash: a55741fced90a62316ab8d046a91ee0364b314fd
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573564"
---
# <a name="management-overview"></a><span data-ttu-id="007cc-103">관리 개요</span><span class="sxs-lookup"><span data-stu-id="007cc-103">Management overview</span></span>

<span data-ttu-id="007cc-104">Microsoft 팀 대화방 시스템을 사용자가 사용할 수 있도록 하 고 훌륭한 사용자 환경을 제공 하기 위해 지속적인 유지 관리와 작업을 개발 하 고 실행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="007cc-105">모니터</span><span class="sxs-lookup"><span data-stu-id="007cc-105">Monitoring</span></span> 

<span data-ttu-id="007cc-106">Microsoft 팀 대화방 시스템의 모니터링은 다음과 같은 두 가지 주요 활동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="007cc-107">장치, 응용 프로그램 및 주변 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="007cc-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="007cc-108">품질 및 안정성 모니터링 (CQD)</span><span class="sxs-lookup"><span data-stu-id="007cc-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="007cc-109">Microsoft 팀 대화방 장치, 응용 프로그램 및 주변 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="007cc-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="007cc-110">사용자가 Microsoft 팀 대화방 단위를 사용할 수 있도록 하려면 단위가 켜져 있고, Microsoft 팀 대화방 응용 프로그램이 올바르게 구성 된 네트워크에 연결 되어 있으며, 제대로 작동 하는 주변 장치에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="007cc-111">Microsoft 팀 공간 응용 프로그램 및 연결 된 주변 장치 상태에 대 한 정보는 Microsoft 팀 대화방 응용 프로그램이 Windows 이벤트 로그에 기록 하 고 [로그 항목을 이해](azure-monitor-manage.md#understand-the-log-entries)하는 데 문서화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="007cc-112">**설정**</span><span class="sxs-lookup"><span data-stu-id="007cc-112">**Setting**</span></span>|<span data-ttu-id="007cc-113">**가능**</span><span class="sxs-lookup"><span data-stu-id="007cc-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="007cc-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="007cc-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="007cc-115">Microsoft 팀 회의실을 부팅할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="007cc-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="007cc-116">전원 관리-\> AC, 10 분 후 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="007cc-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="007cc-117">전원 관리-\> AC, 시스템을 절전 모드로 전환 안 함</span><span class="sxs-lookup"><span data-stu-id="007cc-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="007cc-118">Microsoft 팀 대화방에서 연결 된 디스플레이를 끄고 자동으로 절전 모드 해제 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="007cc-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="007cc-119">네트 계정/maxpwage: 무제한</span><span class="sxs-lookup"><span data-stu-id="007cc-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="007cc-120">또는 동등한 방법으로 로컬 계정에서 암호 만료를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="007cc-121">이 작업을 수행 하지 않으면 결국 Skype 계정에 만료 된 비밀 번호에 대 한 로그온 complaining 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="007cc-122">이로 인해 컴퓨터의 모든 로컬 계정에 영향을 줄 수 있으므로이를 설정 하지 않으면 상자의 관리 계정도 결국 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="007cc-123">Skype 계정이 항상 로그인 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="007cc-124">그룹 정책을 사용 하 여 파일을 전송 하는 방법에 대해서는 [파일 항목 구성을](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="007cc-125">PowerShell을 사용 하 여 원격 관리</span><span class="sxs-lookup"><span data-stu-id="007cc-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="007cc-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="007cc-126"></span></span>

<span data-ttu-id="007cc-127">Microsoft Operations Manager Suite를 사용 하 여 Microsoft 팀 회의실 시스템을 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="007cc-128">모니터링 및 기본 경고를 설정 하는 방법에 대 한 지침은 [Azure Monitor를 사용 하 여 Microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="007cc-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="007cc-129">이 지침을 사용 하 여 간편 하 게 사용할 수 있는 대시보드를 만들어 배포 전반에 걸친 Microsoft 팀 회의실 단위에 대 한 문제를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="007cc-130">결정 사항</span><span class="sxs-lookup"><span data-stu-id="007cc-130">Decision points</span></span>|<ul><li><span data-ttu-id="007cc-131">운영 관리 도구 모음을 사용 하 여 Microsoft 팀 회의실 배포를 모니터링 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="007cc-132">전자 메일 알림에 사용할 대상 메일 그룹을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="007cc-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="007cc-133">Next steps</span></span>|<ul><li><span data-ttu-id="007cc-134">품질 및 안정성 모니터링 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="007cc-135">품질 및 안정성 모니터링 (CQD)</span><span class="sxs-lookup"><span data-stu-id="007cc-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="007cc-136">통화 및 모임 품질과 안정성 추세를 모니터링 하 여 중요 한 영역을 식별 하 고 해결을 진행 하는 데 도움이 되도록 배포의 일부로 지속적인 운영 품질 및 안정성 모니터링 절차를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="007cc-137">빌드 정보를 CQD에 업로드 하면 각 건물 수준에서 통화 품질 및 안정성 추세를 조사 하 여 쉽게 건물을 비교 하 고 특정 문제에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="007cc-138">품질 및 안정성 추세를 식별 하 고 해당 문제를 해결할 작업 계획을 만들려면 [경험 치 검토 가이드](https://aka.ms/qerguide) 를 검토 하 고 팔 로우 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="007cc-139">Microsoft 팀 대화방 OS 및 Microsoft 팀 대화방 응용 프로그램 업데이트</span><span class="sxs-lookup"><span data-stu-id="007cc-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="007cc-140">제품 업데이트 및 개선 기능 혜택을 얻으려면 Microsoft 팀 공간 OS 및 Microsoft 팀 공간 응용 프로그램을 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="007cc-141">자세한 지침은 [Microsoft 팀 대화방 관리](room-systems-v2-operations.md#software-updates)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="007cc-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="007cc-142">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="007cc-142">Windows Updates</span></span>

<span data-ttu-id="007cc-143">Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱으로 동일한 Windows 업데이트 및 OS 빌드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="007cc-144">자세한 내용은 [Windows 업데이트 관리](updates.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="007cc-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="007cc-145">해결사</span><span class="sxs-lookup"><span data-stu-id="007cc-145">Troubleshooting</span></span>

<span data-ttu-id="007cc-146">운영 팀과 헬프 데스크에 Microsoft 팀 대화방 문제에 대 한 알림이 표시 되도록 위의 섹션에서 설명한 대로 Operations Management Suite 경고를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="007cc-147">PowerShell 원격 관리에 사용할 수 있는 옵션은 PowerShell을 [사용 하 여 원격 관리](room-systems-v2-operations.md#remote-management-using-powershell)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="007cc-148">주변 장치에 대 한 연결이 끊어지면 로컬 "smart 핸 즈"를 사용 하거나 장치를 다시 연결 하는 기능을 지원 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007cc-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="007cc-149">문제 해결 및 관리 모드에 대 한 자세한 내용은 [Microsoft 팀 대화방 관리](room-systems-v2-operations.md#admin-mode-and-device-management)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="007cc-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="007cc-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="007cc-150">See also</span></span>

[<span data-ttu-id="007cc-151">Microsoft 팀 대화방 도움말</span><span class="sxs-lookup"><span data-stu-id="007cc-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="007cc-152">Microsoft 팀 회의실 계획</span><span class="sxs-lookup"><span data-stu-id="007cc-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="007cc-153">Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="007cc-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="007cc-154">Microsoft 팀 대화방 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="007cc-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="007cc-155">XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리</span><span class="sxs-lookup"><span data-stu-id="007cc-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
