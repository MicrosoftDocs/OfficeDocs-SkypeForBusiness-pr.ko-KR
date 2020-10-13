---
title: Microsoft 팀을 위한 클라우드 비디오 Interop
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 클라우드 비디오 Interop를 중간 솔루션으로 사용 하 여 타사 회의실 장치가 Microsoft 팀 모임에 참가할 수 있도록 합니다.
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f812d27b07dadb2f60bf77302e18eb0879f977e
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433080"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="2df96-103">Microsoft 팀을 위한 클라우드 비디오 Interop</span><span class="sxs-lookup"><span data-stu-id="2df96-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="2df96-104">CVI (Cloud Video Interop)는 타사 모임 채팅방 (telepresence) 및 개인 비디오 장치 (VTCs)에서 Microsoft 팀 모임에 참가할 수 있도록 하는 Microsoft의 정식 타사 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="2df96-105">Microsoft 팀에서는 오디오, 비디오, 콘텐츠 공유가 포함 된 모임에서 풍부한 온라인 콘텐츠 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="2df96-106">이 작업은 데스크톱 및 웹 클라이언트를 통해 가능 하며, Microsoft 팀과 기본적으로 통합 되는 여러 파트너 장치를 통해 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="2df96-107">그러나 많은 고객이 비디오 teleconferencing 및 개인 영상 통신 장치에 이미 투자 하 고 있어 업그레이드 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="2df96-108">클라우드 비디오 Interop는 업그레이드 준비가 될 때까지 기존 솔루션을 계속 사용할 수 있도록 해 주는 간편한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="2df96-109">클라우드 비디오 Interop를 사용 하 여 Microsoft 팀은 회의실 또는 팀 클라이언트 내에서 모든 참가자에 대해 기본 모임 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="2df96-110">클라우드 비디오 Interop를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2df96-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="2df96-111">클라우드 비디오 Interop는 팀 끝점을 사용 하 여 전체 기본 Microsoft 팀 솔루션으로 전환 하는 동안 중간 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="2df96-112">제공 되는 서비스는 마이그레이션 경로의 일부 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="2df96-113">클라우드 비디오 Interop는 다음 조건을 충족 하는 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="2df96-114">Microsoft 팀과 직접 통합할 자격이 없는 회의실 장치 및 개인 영상 장치 배포 (50 + 장치)가 대량으로 배포 됨</span><span class="sxs-lookup"><span data-stu-id="2df96-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="2df96-115">클라우드 비디오 Interop 파트너 중 하나에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="2df96-116">기본 Microsoft 팀 솔루션으로 마이그레이션하는 동안 현재 회의실 장치 및 개인 비디오 장치에 투자 가치를 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="2df96-117">클라우드 비디오 Interop는 훌륭한 중급 솔루션을 제공 하는 반면, 고객은 장기적으로 팀 대화방 시스템과 같은 기본 팀 모임 솔루션을 살펴볼 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="office-365-us-government-and-third-party-services"></a><span data-ttu-id="2df96-118">Office 365 미국 정부 및 타사 서비스</span><span class="sxs-lookup"><span data-stu-id="2df96-118">Office 365 US Government and third-party services</span></span>

<span data-ttu-id="2df96-119">Office 365는 타사 응용 프로그램을 SharePoint Online 사이트, 비즈니스용 Skype, 팀, Office 응용 프로그램 (예: Word, Excel, PowerPoint, Outlook 등의 Microsoft 365 앱에 포함) 및 Outlook Web App에 통합할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-119">Office 365 provides the ability to integrate third-party applications into SharePoint Online sites, Skype for Business, Teams, Office applications included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App.</span></span> <span data-ttu-id="2df96-120">또한 Office 365는 타사 서비스 공급자와의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-120">In addition, Office 365 supports integration with third-party service providers.</span></span> <span data-ttu-id="2df96-121">이러한 타사 응용 프로그램 및 서비스에는 Office 365 인프라 외부에 있는 타사 시스템에 조직의 고객 데이터를 저장, 전송, 처리 하는 작업이 포함 될 수 있으며, 따라서 Office 365 준수 및 데이터 보호 약정에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-121">These third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Office 365 infrastructure and therefore are not covered by the Office 365 compliance and data protection commitments.</span></span> <span data-ttu-id="2df96-122">**조직에 대해 이러한 서비스의 적절 한 사용을 평가할 때는 제 3 자가 제공 하는 개인 정보 보호 및 규정 준수 문을 검토 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="2df96-122">**It is recommended that you review the privacy and compliance statements provided by the third parties when assessing the appropriate use of these services for your organization.**</span></span>



### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="2df96-123">Microsoft 팀에 대해 인증 된 파트너</span><span class="sxs-lookup"><span data-stu-id="2df96-123">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="2df96-124">다음 파트너는 Microsoft 팀을 위한 비디오 interop 솔루션을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-124">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="2df96-125">회사에서 엔터프라이즈 내에서 이러한 파트너를 조합 하 여 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-125">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="2df96-126">Partner</span><span class="sxs-lookup"><span data-stu-id="2df96-126">Partner</span></span>|<span data-ttu-id="2df96-127">파트너 솔루션</span><span class="sxs-lookup"><span data-stu-id="2df96-127">Partner solution</span></span>|
|----|---|
|![Polycom RealConnect를 나타내는 로고](media/polycom.png) | <span data-ttu-id="2df96-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect 서비스</a></span><span class="sxs-lookup"><span data-stu-id="2df96-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect Service</a></span></span> |
|![Pexip 무한대를 나타내는 로고](media/pexip.png)| <span data-ttu-id="2df96-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft 팀 용 pexip 무한대</a></span><span class="sxs-lookup"><span data-stu-id="2df96-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![BlueJeans 게이트웨이를 나타내는 로고](media/bluejeans.png)| <span data-ttu-id="2df96-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft 팀을 위한 BlueJeans 게이트웨이</a></span><span class="sxs-lookup"><span data-stu-id="2df96-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |
|![Cisco CVI을 나타내는 로고](media/cisco.png)|<span data-ttu-id="2df96-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft 팀 용 Cisco Webex 비디오 통합</a></span><span class="sxs-lookup"><span data-stu-id="2df96-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a></span></span>|

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="2df96-136">클라우드 비디오 Interop 개요</span><span class="sxs-lookup"><span data-stu-id="2df96-136">Cloud Video Interop overview</span></span>

<span data-ttu-id="2df96-137">클라우드 비디오 Interop는 기존 영상 회의와 개인 비디오 디바이스 솔루션 (온-프레미스)과 Microsoft 팀 간의 상호 운영성을 제공 하기 위해 파트너가 제공 하는 타사 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-137">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="2df96-138">파트너가 제공 하는 솔루션은 완전히 클라우드 기반 또는 부분적/완전히 온-프레미스로 배포할 수 있는 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-138">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="2df96-139">다음 다이어그램은 파트너 솔루션의 상위 수준 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-139">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![팀 클라우드 비디오 Interop 파트너 솔루션을 설명 하는 다이어그램](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="2df96-141">클라우드 비디오 Interop 배포</span><span class="sxs-lookup"><span data-stu-id="2df96-141">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="2df96-142">클라우드 비디오 Interop 솔루션을 배포 하는 경우 파트너 솔루션을 배포 하는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-142">When deploying a Cloud Video Interop solution, it's important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="2df96-143">클라우드 비디오 Interop를 배포 하기 위해 수행 해야 하는 일반적인 단계는 다음 다이어그램에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-143">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![조직에서 CVI을 배포 하는 방법을 설명 하는 다이어그램](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="2df96-145">계획</span><span class="sxs-lookup"><span data-stu-id="2df96-145">Plan</span></span>

<span data-ttu-id="2df96-146">계획 단계에서는 네이티브 팀 장치로 대체 하지 않을 장치를 식별 하 고 이러한 장치를 지원할 수 있는 클라우드 비디오 Interop 파트너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-146">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="2df96-147">또한 클라우드 비디오 Interop 사용 가능 장치를 사용할 모임을 예약 하는 각 사용자에 대해 라이선스가 필요 하다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-147">It's also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="2df96-148">정확한 라이선스 요구 사항은 클라우드 비디오 Interop 파트너에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-148">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="2df96-149">배포를 시작 하기 전에이에 대 한 자세한 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-149">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="2df96-150">구성할</span><span class="sxs-lookup"><span data-stu-id="2df96-150">Configure</span></span>

<span data-ttu-id="2df96-151">CVI 배포에 대해 선택한 파트너는 조직 내에서 성공적으로 배포 하는 데 필요한 모든 단계로 구성 된 전체 배포 문서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-151">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="2df96-152">여기에는 방화벽 포트 및 IP 범위, 장치에 대 한 구성 변경 내용, 변경 해야 하는 기타 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-152">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="2df96-153">공급</span><span class="sxs-lookup"><span data-stu-id="2df96-153">Provision</span></span>  

<span data-ttu-id="2df96-154">구축 단계에서 파트너 구성 가이드에 따라 라이선스를 적절 한 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-154">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="2df96-155">또한 협력 업체에 게 팀 환경에 대 한 액세스를 제공 하기 위해 Azure 승인 프로세스를 거쳐야 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-155">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="2df96-156">Azure 승인 프로세스에 대 한 자세한 내용은 [Microsoft id 플랫폼 끝점의 사용 권한 및 동의](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2df96-156">See [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) for more information about the Azure consent process.</span></span>

### <a name="schedule"></a><span data-ttu-id="2df96-157">따라</span><span class="sxs-lookup"><span data-stu-id="2df96-157">Schedule</span></span>

<span data-ttu-id="2df96-158">사용자가 클라우드 비디오 Interop를 사용할 수 있게 되 면 Outlook 용 팀 추가 기능을 사용 하 여 예약 된 모든 모임에 팀 모임에 자동으로 추가 되는 적절 한 추가 정보가 포함 되므로 클라우드 비디오 Interop 호환 장치에서 이러한 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-158">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="2df96-159">합류</span><span class="sxs-lookup"><span data-stu-id="2df96-159">Join</span></span>

<span data-ttu-id="2df96-160">파트너 솔루션에 따라 여러 가지 방법으로 클라우드 비디오 Interop 사용 가능 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-160">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="2df96-161">정확한 모임 참가 시나리오는 클라우드 비디오 Interop 파트너에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-161">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="2df96-162">여기에는 몇 가지 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-162">We've listed some examples below:</span></span>

- <span data-ttu-id="2df96-163">IVR (대화형 음성 응답)</span><span class="sxs-lookup"><span data-stu-id="2df96-163">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="2df96-164">Tenantkey@domain를 사용 하 여 파트너의 IVR에 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-164">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="2df96-165">파트너 IVR에 있는 경우 VTC conferenceId을 입력 하 라는 메시지가 표시 되 고 팀 회의에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-165">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="2df96-166">다이렉트 전화 접속</span><span class="sxs-lookup"><span data-stu-id="2df96-166">Direct dial</span></span> 
  - <span data-ttu-id="2df96-167">Tenantkey의 전체 문자열을 사용 하 여 직접 전화 접속 기능을 사용 하 여 파트너의 IVR과 상호 작용 하지 않고 팀 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="2df96-167">You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="2df96-168">한 번 터치 다이얼</span><span class="sxs-lookup"><span data-stu-id="2df96-168">One-touch dial</span></span> 
  - <span data-ttu-id="2df96-169">통합 된 팀 객실이 있는 경우에는 해당 파트너가 제공 하는 원터치 전화 접속 기능을 사용할 수 있습니다 (다이얼 문자열을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="2df96-169">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="2df96-170">클라우드 비디오 Interop 관리</span><span class="sxs-lookup"><span data-stu-id="2df96-170">Manage Cloud Video Interop</span></span>

<span data-ttu-id="2df96-171">클라우드 비디오 Interop을 배포한 후에는 파트너가 제공 하는 솔루션을 사용 하 여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-171">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="2df96-172">각 파트너는 라이선스 및 장치 관리를 모두 포함 하는 관리 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-172">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="2df96-173">보고는 파트너 관리 인터페이스에서 직접 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-173">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="2df96-174">보고 기능에 대 한 자세한 내용은 선택한 파트너에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="2df96-174">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="2df96-175">클라우드 비디오 Interop 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2df96-175">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="2df96-176">클라우드 비디오 Interop는 파트너가 제공 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-176">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="2df96-177">문제가 발생 하는 경우 첫 번째 단계는 팀 클라이언트가 설치 된 장치를 연결 하 고 문제를 일으키는 클라우드 비디오 Interop 장치와 동일한 세그먼트에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-177">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="2df96-178">이 세그먼트에서 팀이 올바르게 작동 하 고 파트너가 제공한 모든 네트워킹 및 구성 지침을 팔 로우 한 경우에는 협력 업체에 문의 하 여 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-178">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="2df96-179">클라우드 비디오 Interop 용 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2df96-179">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="2df96-180">다음 PowerShell cmdlet을 사용 하 여 클라우드 비디오 Interop 배포를 부분적으로 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-180">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="2df96-181">**CsTeamsVideoInteropServicepolicy**: Microsoft는 지원 되는 각 파트너에 대해 미리 구성 된 정책을 제공 하 여 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-181">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="2df96-182">이 cmdlet을 사용 하 여 조직에서 사용할 수 있는 미리 구성 된 정책을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-182">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="2df96-183">Grant-CsTeamsVideoInteropServicePolicy cmdlet을 활용 하 여 하나 이상의 사용자에 게이 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-183">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="2df96-184">**부여-CsTeamsVideoInteropServicePolicy**:이 cmdlet을 사용 하면 조직에서 사용할 미리 생성 된 정책을 할당 하거나 특정 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-184">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="2df96-185">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직에서 사용 하려는 지원 되는 cvi 파트너에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-185">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="2df96-186">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직에서 사용 하는 지원 되는 cvi 파트너에 대 한 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-186">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="2df96-187">**CsVideoInteropServiceProvider**:이 cmdlet을 사용 하 여 조직 내에서 사용 하도록 구성 된 모든 공급자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-187">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="2df96-188">**제거-CsVideoInteropServiceProvider**: 조직에서 더 이상 사용 하지 않는 공급자에 대 한 모든 공급자 정보를 제거 하려면이 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df96-188">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>
