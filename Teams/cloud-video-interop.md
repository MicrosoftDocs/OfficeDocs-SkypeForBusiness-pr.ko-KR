---
title: Microsoft 팀을 위한 클라우드 비디오 Interop
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: 클라우드 비디오 Interop는 타사 회의실 장치를 사용 하 여 Microsoft 팀 모임에 참가 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c44f945304bd6e21e0c572ad17afe165fe6eedcd
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516686"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="e6fc1-103">Microsoft 팀을 위한 클라우드 비디오 Interop</span><span class="sxs-lookup"><span data-stu-id="e6fc1-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="e6fc1-104">CVI (Cloud Video Interop)는 타사 모임 채팅방 (telepresence) 및 개인 비디오 장치 (VTCs)에서 Microsoft 팀 모임에 참가할 수 있도록 하는 Microsoft의 정식 타사 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="e6fc1-105">Microsoft 팀에서는 오디오, 비디오, 콘텐츠 공유가 포함 된 모임에서 풍부한 온라인 콘텐츠 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="e6fc1-106">이 작업은 데스크톱 및 웹 클라이언트를 통해 가능 하며, Microsoft 팀과 기본적으로 통합 되는 여러 파트너 장치를 통해 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="e6fc1-107">그러나 많은 고객이 비디오 teleconferencing 및 개인 영상 통신 장치에 이미 투자 하 고 있어 업그레이드 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="e6fc1-108">클라우드 비디오 Interop는 업그레이드 준비가 될 때까지 기존 솔루션을 계속 사용할 수 있도록 해 주는 간편한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="e6fc1-109">클라우드 비디오 Interop를 사용 하 여 Microsoft 팀은 회의실 또는 팀 클라이언트 내에서 모든 참가자에 대해 기본 모임 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="e6fc1-110">클라우드 비디오 Interop를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e6fc1-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="e6fc1-111">클라우드 비디오 Interop는 팀 끝점을 사용 하 여 전체 기본 Microsoft 팀 솔루션으로 전환 하는 동안 중간 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="e6fc1-112">제공 되는 서비스는 마이그레이션 경로의 일부 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="e6fc1-113">클라우드 비디오 Interop는 다음 조건을 충족 하는 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="e6fc1-114">Microsoft 팀과 직접 통합할 자격이 없는 회의실 장치 및 개인 영상 장치 배포 (50 + 장치)가 대량으로 배포 됨</span><span class="sxs-lookup"><span data-stu-id="e6fc1-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="e6fc1-115">클라우드 비디오 Interop 파트너 중 하나에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="e6fc1-116">기본 Microsoft 팀 솔루션으로 마이그레이션하는 동안 현재 회의실 장치 및 개인 비디오 장치에 투자 가치를 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="e6fc1-117">클라우드 비디오 Interop는 훌륭한 중급 솔루션을 제공 하는 반면, 고객은 장기적으로 팀 대화방 시스템과 같은 기본 팀 모임 솔루션을 살펴볼 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="e6fc1-118">Microsoft 팀에 대해 인증 된 파트너</span><span class="sxs-lookup"><span data-stu-id="e6fc1-118">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="e6fc1-119">다음 파트너는 Microsoft 팀을 위한 비디오 interop 솔루션을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-119">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="e6fc1-120">회사에서 엔터프라이즈 내에서 이러한 파트너를 조합 하 여 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-120">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="e6fc1-121">Partner</span><span class="sxs-lookup"><span data-stu-id="e6fc1-121">Partner</span></span>|<span data-ttu-id="e6fc1-122">파트너 솔루션</span><span class="sxs-lookup"><span data-stu-id="e6fc1-122">Partner solution</span></span>|
|----|---|
|![Polycom RealConnect를 나타내는 로고](media/polycom.png) | <span data-ttu-id="e6fc1-124"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect 서비스</a></span><span class="sxs-lookup"><span data-stu-id="e6fc1-124"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect Service</a></span></span> |
|![Pexip 무한대를 나타내는 로고](media/pexip.png)| <span data-ttu-id="e6fc1-126"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft 팀 용 pexip 무한대</a></span><span class="sxs-lookup"><span data-stu-id="e6fc1-126"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![BlueJeans 게이트웨이를 나타내는 로고](media/bluejeans.png)| <span data-ttu-id="e6fc1-128"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft 팀을 위한 BlueJeans 게이트웨이</a></span><span class="sxs-lookup"><span data-stu-id="e6fc1-128"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="e6fc1-129">클라우드 비디오 Interop 개요</span><span class="sxs-lookup"><span data-stu-id="e6fc1-129">Cloud Video Interop overview</span></span>

<span data-ttu-id="e6fc1-130">클라우드 비디오 Interop는 기존 영상 회의와 개인 비디오 디바이스 솔루션 (온-프레미스)과 Microsoft 팀 간의 상호 운영성을 제공 하기 위해 파트너가 제공 하는 타사 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-130">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="e6fc1-131">파트너가 제공 하는 솔루션은 완전히 클라우드 기반 또는 부분적/완전히 온-프레미스로 배포할 수 있는 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-131">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="e6fc1-132">다음 다이어그램은 파트너 솔루션의 상위 수준 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-132">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![팀 클라우드 비디오 Interop 파트너 솔루션을 설명 하는 다이어그램](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="e6fc1-134">클라우드 비디오 Interop 배포</span><span class="sxs-lookup"><span data-stu-id="e6fc1-134">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="e6fc1-135">클라우드 비디오 Interop 솔루션을 배포 하는 경우 파트너 솔루션을 배포 하는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-135">When deploying a Cloud Video Interop solution, it’s important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="e6fc1-136">클라우드 비디오 Interop를 배포 하기 위해 수행 해야 하는 일반적인 단계는 다음 다이어그램에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-136">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![조직에서 CVI을 배포 하는 방법을 설명 하는 다이어그램](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="e6fc1-138">계획</span><span class="sxs-lookup"><span data-stu-id="e6fc1-138">Plan</span></span>

<span data-ttu-id="e6fc1-139">계획 단계에서는 네이티브 팀 장치로 대체 하지 않을 장치를 식별 하 고 이러한 장치를 지원할 수 있는 클라우드 비디오 Interop 파트너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-139">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="e6fc1-140">또한 클라우드 비디오 Interop 사용 가능 장치를 사용할 모임을 예약 하는 각 사용자에 대해 라이선스가 필요 하다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-140">It’s also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="e6fc1-141">정확한 라이선스 요구 사항은 클라우드 비디오 Interop 파트너에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-141">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="e6fc1-142">배포를 시작 하기 전에이에 대 한 자세한 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-142">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="e6fc1-143">구성할</span><span class="sxs-lookup"><span data-stu-id="e6fc1-143">Configure</span></span>

<span data-ttu-id="e6fc1-144">CVI 배포에 대해 선택한 파트너는 조직 내에서 성공적으로 배포 하는 데 필요한 모든 단계로 구성 된 전체 배포 문서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-144">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="e6fc1-145">여기에는 방화벽 포트 및 IP 범위, 장치에 대 한 구성 변경 내용, 변경 해야 하는 기타 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-145">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="e6fc1-146">공급</span><span class="sxs-lookup"><span data-stu-id="e6fc1-146">Provision</span></span>  

<span data-ttu-id="e6fc1-147">구축 단계에서 파트너 구성 가이드에 따라 라이선스를 적절 한 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-147">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="e6fc1-148">또한 협력 업체에 게 팀 환경에 대 한 액세스를 제공 하기 위해 Azure 승인 프로세스를 거쳐야 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-148">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="e6fc1-149">Azure 승인 프로세스에 대 한 자세한 내용은 다음을 참조 하세요.https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent</span><span class="sxs-lookup"><span data-stu-id="e6fc1-149">More information on the Azure Consent process can be found here: https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent</span></span> 

### <a name="schedule"></a><span data-ttu-id="e6fc1-150">따라</span><span class="sxs-lookup"><span data-stu-id="e6fc1-150">Schedule</span></span>

<span data-ttu-id="e6fc1-151">사용자가 클라우드 비디오 Interop를 사용할 수 있게 되 면 Outlook 용 팀 추가 기능을 사용 하 여 예약 된 모든 모임에서 팀 모임에 자동으로 추가 되는 적절 한 추가 정보를 포함 하 여 클라우드 비디오가 Interop 호환 장치는 이러한 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-151">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="e6fc1-152">합류</span><span class="sxs-lookup"><span data-stu-id="e6fc1-152">Join</span></span>

<span data-ttu-id="e6fc1-153">파트너 솔루션에 따라 여러 가지 방법으로 클라우드 비디오 Interop 사용 가능 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-153">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="e6fc1-154">정확한 모임 참가 시나리오는 클라우드 비디오 Interop 파트너에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-154">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="e6fc1-155">여기에는 몇 가지 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-155">We’ve listed some examples below:</span></span>

- <span data-ttu-id="e6fc1-156">IVR (대화형 음성 응답)</span><span class="sxs-lookup"><span data-stu-id="e6fc1-156">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="e6fc1-157">Tenantkey @ domain을 사용 하 여 파트너의 IVR에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-157">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="e6fc1-158">파트너 IVR에 있는 경우 VTC conferenceId을 입력 하 라는 메시지가 표시 되 고 팀 회의에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-158">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="e6fc1-159">다이렉트 전화 접속</span><span class="sxs-lookup"><span data-stu-id="e6fc1-159">Direct dial</span></span> 
  - <span data-ttu-id="e6fc1-160">Tenantkey의 전체 문자열을 사용 하 여 직접 전화 접속 기능을 사용 하 여 파트너의 IVR과 상호 작용 하지 않고 팀 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId @ domain.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-160">You can directly dial in to the Teams meeting without interacting with the partner’s IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="e6fc1-161">한 번 터치 다이얼</span><span class="sxs-lookup"><span data-stu-id="e6fc1-161">One-touch dial</span></span> 
  - <span data-ttu-id="e6fc1-162">통합 된 팀 객실이 있는 경우에는 해당 파트너가 제공 하는 원터치 전화 접속 기능을 사용할 수 있습니다 (다이얼 문자열을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e6fc1-162">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="e6fc1-163">클라우드 비디오 Interop 관리</span><span class="sxs-lookup"><span data-stu-id="e6fc1-163">Manage Cloud Video Interop</span></span>

<span data-ttu-id="e6fc1-164">클라우드 비디오 Interop을 배포한 후에는 파트너가 제공 하는 솔루션을 사용 하 여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-164">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="e6fc1-165">각 파트너는 라이선스 및 장치 관리를 모두 포함 하는 관리 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-165">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="e6fc1-166">보고는 파트너 관리 인터페이스에서 직접 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-166">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="e6fc1-167">보고 기능에 대 한 자세한 내용은 선택한 파트너에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-167">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="e6fc1-168">클라우드 비디오 Interop 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e6fc1-168">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="e6fc1-169">클라우드 비디오 Interop는 파트너가 제공 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-169">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="e6fc1-170">문제가 발생 하는 경우 첫 번째 단계는 팀 클라이언트가 설치 된 장치를 연결 하 고 문제를 일으키는 클라우드 비디오 Interop 장치와 동일한 세그먼트에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-170">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="e6fc1-171">이 세그먼트에서 팀이 올바르게 작동 하 고 파트너가 제공한 모든 네트워킹 및 구성 지침을 팔 로우 한 경우에는 협력 업체에 문의 하 여 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-171">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="e6fc1-172">클라우드 비디오 Interop 용 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6fc1-172">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="e6fc1-173">다음 PowerShell cmdlet을 사용 하 여 클라우드 비디오 Interop 배포를 부분적으로 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-173">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="e6fc1-174">**CsTeamsVideoInteropServicepolicy**: Microsoft는 지원 되는 각 파트너에 대해 미리 구성 된 정책을 제공 하 여 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-174">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="e6fc1-175">이 cmdlet을 사용 하 여 조직에서 사용할 수 있는 미리 구성 된 정책을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-175">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="e6fc1-176">CsTeamsVideoInteropServicePolicy cmdlet을 활용 하 여 하나 이상의 사용자에 게이 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-176">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="e6fc1-177">**부여-CsTeamsVideoInteropServicePolicy**:이 cmdlet을 사용 하면 조직에서 사용할 미리 생성 된 정책을 할당 하거나 특정 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-177">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="e6fc1-178">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직에서 사용 하려는 지원 되는 cvi 파트너에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-178">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="e6fc1-179">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직에서 사용 하는 지원 되는 cvi 파트너에 대 한 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-179">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="e6fc1-180">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직 내에서 사용 하도록 구성 된 모든 공급자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-180">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="e6fc1-181">**제거-CsVideoInteropServiceProvider**: 조직에서 더 이상 사용 하지 않는 공급자에 대 한 모든 공급자 정보를 제거 하려면이 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-181">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>
