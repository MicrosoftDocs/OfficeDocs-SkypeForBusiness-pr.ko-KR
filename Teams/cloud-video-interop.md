---
title: Microsoft Teams용 클라우드 비디오 Interop
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
description: 클라우드 비디오 Interop을 중간 솔루션으로 사용하여 타사 회의실 디바이스가 Microsoft Teams 모임에 참가할 수 있도록 허용합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122362"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="8c191-103">Microsoft Teams용 클라우드 비디오 Interop</span><span class="sxs-lookup"><span data-stu-id="8c191-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="8c191-104">CVI(Cloud Video Interop)는 타사 회의실(telepresence) 및 VTC(개인 비디오 디바이스)가 Microsoft Teams 모임에 참가할 수 있는 Microsoft 공인 타사 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="8c191-105">Microsoft Teams를 사용하면 오디오, 비디오 및 콘텐츠 공유를 포함 하는 모임에서 풍부한 온라인 콘텐츠 공동 작업을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="8c191-106">데스크톱 및 웹 클라이언트뿐만 아니라 Microsoft Teams와 기본적으로 통합되는 많은 파트너 디바이스를 통해 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="8c191-107">그러나 많은 고객이 이미 비디오 원격회의 및 개인 비디오 통신 디바이스에 투자하여 업그레이드하는 데 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="8c191-108">Cloud Video Interop은 쉽게 솔루션을 제공하므로 업그레이드할 준비가 될 때까지 기존 솔루션을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="8c191-109">Cloud Video Interop을 통해 Microsoft Teams는 모든 참가자를 위한 네이티브 모임 환경을 회의실 또는 Teams 클라이언트 내부에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="8c191-110">Cloud Video Interop이 제게는 있나요?</span><span class="sxs-lookup"><span data-stu-id="8c191-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="8c191-111">Cloud Video Interop은 Teams 엔드포인트를 사용하여 전체 네이티브 Microsoft Teams 솔루션으로 전환하는 동안 중간 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="8c191-112">제공된 서비스는 마이그레이션 경로의 일부로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="8c191-113">Cloud Video Interop은 다음 조건을 충족하는 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="8c191-114">Microsoft Teams와 직접 통합할 수 없는 회의실 디바이스 및 개인 비디오 디바이스 배포(50개 이상 디바이스)를 대규모로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="8c191-115">Cloud Video Interop 파트너 중 하나에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="8c191-116">네이티브 Microsoft Teams 솔루션으로 마이그레이션하는 동안 현재 회의실 디바이스 및 개인 비디오 디바이스에 대한 투자 가치를 유지하려는 경우</span><span class="sxs-lookup"><span data-stu-id="8c191-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="8c191-117">Cloud Video Interop은 훌륭한 중간 솔루션을 제공하면서 고객이 장기적으로 Teams Room Systems와 같은 네이티브 Teams 모임 솔루션을 살펴보는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="office-365-us-government-and-third-party-services"></a><span data-ttu-id="8c191-118">Office 365 미국 정부 및 타사 서비스</span><span class="sxs-lookup"><span data-stu-id="8c191-118">Office 365 US Government and third-party services</span></span>

<span data-ttu-id="8c191-119">Office 365는 타사 애플리케이션을 SharePoint Online 사이트, 비즈니스용 Skype, Teams, 엔터프라이즈용 Microsoft 365 Apps에 포함된 Office 애플리케이션(예: Word, Excel, PowerPoint 및 Outlook)에 통합하는 기능을 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="8c191-119">Office 365 provides the ability to integrate third-party applications into SharePoint Online sites, Skype for Business, Teams, Office applications included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App.</span></span> <span data-ttu-id="8c191-120">또한 Office 365는 타사 서비스 공급자와의 통합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-120">In addition, Office 365 supports integration with third-party service providers.</span></span> <span data-ttu-id="8c191-121">이러한 타사 애플리케이션 및 서비스는 Office 365 인프라 외부에 있으므로 Office 365 규정 준수 및 데이터 보호 약정에 적용되지 않는 타사 시스템에 조직의 고객 데이터를 저장, 전송 및 처리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-121">These third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Office 365 infrastructure and therefore are not covered by the Office 365 compliance and data protection commitments.</span></span> <span data-ttu-id="8c191-122">**조직에 이러한 서비스의 적절한 사용을 평가할 때 타사에서 제공하는 개인 정보 및 규정 준수 정책을 검토하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="8c191-122">**It is recommended that you review the privacy and compliance statements provided by the third parties when assessing the appropriate use of these services for your organization.**</span></span>



### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="8c191-123">Microsoft Teams에 대한 파트너 인증</span><span class="sxs-lookup"><span data-stu-id="8c191-123">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="8c191-124">다음 파트너에는 Microsoft Teams에 대한 비디오 인터프 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-124">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="8c191-125">회사에서는 엔터프라이즈 내에서 이러한 파트너의 조합으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-125">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="8c191-126">파트너</span><span class="sxs-lookup"><span data-stu-id="8c191-126">Partner</span></span>|<span data-ttu-id="8c191-127">파트너 솔루션</span><span class="sxs-lookup"><span data-stu-id="8c191-127">Partner solution</span></span>|
|----|---|
|![Poly RealConnect를 나타내는 로고](media/polycom.png) | <span data-ttu-id="8c191-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 서비스</a></span><span class="sxs-lookup"><span data-stu-id="8c191-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a></span></span> |
|![Pexip Infinity를 나타내는 로고](media/pexip.png)| <span data-ttu-id="8c191-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams용 Pexip Infinity</a></span><span class="sxs-lookup"><span data-stu-id="8c191-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![BlueJeans Gateway를 나타내는 로고](media/bluejeans.png)| <span data-ttu-id="8c191-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams용 BlueJeans Gateway</a></span><span class="sxs-lookup"><span data-stu-id="8c191-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |
|![Cisco CVI를 나타내는 로고](media/cisco.png)|<span data-ttu-id="8c191-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams용 Cisco Webex 비디오 통합</a></span><span class="sxs-lookup"><span data-stu-id="8c191-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a></span></span>|

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="8c191-136">클라우드 비디오 Interop 개요</span><span class="sxs-lookup"><span data-stu-id="8c191-136">Cloud Video Interop overview</span></span>

<span data-ttu-id="8c191-137">Cloud Video Interop은 파트너가 제공하는 타사 서비스로, 프레미스에서 기존 비디오 회의 및 개인 비디오 디바이스 솔루션과 Microsoft Teams 간에 상호운용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-137">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="8c191-138">파트너가 제공하는 솔루션은 완전 클라우드 기반 또는 부분적으로 온-프레미스를 배포할 수 있는 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-138">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="8c191-139">다음 다이어그램은 파트너 솔루션의 고급 아키텍처를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-139">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![Teams Cloud Video Interop 파트너 솔루션을 설명하는 다이어그램](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="8c191-141">클라우드 비디오 Interop 배포</span><span class="sxs-lookup"><span data-stu-id="8c191-141">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="8c191-142">Cloud Video Interop 솔루션을 배포할 때 파트너 솔루션을 배포하고 있는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-142">When deploying a Cloud Video Interop solution, it's important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="8c191-143">Cloud Video Interop을 배포하는 데 필요한 일반적인 단계는 다음 다이어그램에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-143">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![조직에서 CVI 배포를 설명하는 다이어그램](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="8c191-145">계획</span><span class="sxs-lookup"><span data-stu-id="8c191-145">Plan</span></span>

<span data-ttu-id="8c191-146">계획 단계에서는 네이티브 Teams 디바이스로 대체하지 않을 디바이스를 식별하고 이러한 디바이스를 지원할 수 있는 Cloud Video Interop 파트너를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-146">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="8c191-147">또한 Cloud Video Interop 지원 디바이스가 조인할 모임을 예약하는 각 사용자에 대한 라이선스가 필요하다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-147">It's also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="8c191-148">Cloud Video Interop 파트너에서 정확한 라이선스 요구 사항을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-148">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="8c191-149">배포를 시작하기 전에 이 방법을 명확히 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-149">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="8c191-150">구성</span><span class="sxs-lookup"><span data-stu-id="8c191-150">Configure</span></span>

<span data-ttu-id="8c191-151">CVI 배포를 위해 선택한 파트너는 조직 내에서 성공적으로 배포하는 데 필요한 모든 단계로 구성된 전체 배포 문서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-151">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="8c191-152">여기에는 방화벽 포트 및 IP 범위, 디바이스에 대한 구성 변경 내용 및 변경해야 하는 기타 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-152">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="8c191-153">프로비전</span><span class="sxs-lookup"><span data-stu-id="8c191-153">Provision</span></span>  

<span data-ttu-id="8c191-154">프로비전 단계에서 파트너 구성 가이드에 따라 적절한 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-154">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="8c191-155">또한 파트너에게 Teams 환경에 대한 액세스 권한을 제공하려면 Azure 동의 프로세스를 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-155">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="8c191-156">Azure [동의 프로세스에](/azure/active-directory/develop/v2-permissions-and-consent) 대한 자세한 내용은 Microsoft ID 플랫폼 엔드포인트의 사용 권한 및 동의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c191-156">See [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent) for more information about the Azure consent process.</span></span>

### <a name="schedule"></a><span data-ttu-id="8c191-157">일정</span><span class="sxs-lookup"><span data-stu-id="8c191-157">Schedule</span></span>

<span data-ttu-id="8c191-158">사용자가 Cloud Video Interop을 사용하도록 설정한 후 Outlook용 Teams 모임 추가 기능 또는 Teams 클라이언트를 사용하여 예약된 모든 모임에는 Cloud Video Interop 호환 디바이스가 이러한 모임에 참가할 수 있도록 Teams 모임에 자동으로 적절한 추가 정보가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-158">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="8c191-159">조인</span><span class="sxs-lookup"><span data-stu-id="8c191-159">Join</span></span>

<span data-ttu-id="8c191-160">파트너 솔루션에 따라 Cloud Video Interop 지원 모임에 참가하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-160">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="8c191-161">Cloud Video Interop 파트너가 정확한 모임 조인 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-161">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="8c191-162">아래에 몇 가지 예제가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-162">We've listed some examples below:</span></span>

- <span data-ttu-id="8c191-163">IVR(대화형 음성 응답)</span><span class="sxs-lookup"><span data-stu-id="8c191-163">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="8c191-164">파트너의 IVR에 전화 접속할 수 tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="8c191-164">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="8c191-165">파트너 IVR에 있는 경우 VTC conferenceId에 입력하라는 메시지가 표시됩니다. 그러면 Teams 모임에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-165">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="8c191-166">직접 다이얼</span><span class="sxs-lookup"><span data-stu-id="8c191-166">Direct dial</span></span> 
  - <span data-ttu-id="8c191-167">테넌트키의 전체 문자열을 사용하여 직접 다이얼 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고 Teams 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="8c191-167">You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="8c191-168">원터치 다이얼</span><span class="sxs-lookup"><span data-stu-id="8c191-168">One-touch dial</span></span> 
  - <span data-ttu-id="8c191-169">통합 Teams 룸이 있는 경우 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다(다이얼 문자열을 입력할 필요 없이).</span><span class="sxs-lookup"><span data-stu-id="8c191-169">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="8c191-170">클라우드 비디오 Interop 관리</span><span class="sxs-lookup"><span data-stu-id="8c191-170">Manage Cloud Video Interop</span></span>

<span data-ttu-id="8c191-171">Cloud Video Interop을 배포한 후 파트너가 제공하는 솔루션을 사용하여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-171">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="8c191-172">각 파트너는 라이선스 및 디바이스 관리를 모두 포함할 관리 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-172">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="8c191-173">보고는 파트너 관리 인터페이스에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-173">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="8c191-174">보고 기능에 대한 자세한 내용은 선택한 파트너에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="8c191-174">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="8c191-175">클라우드 비디오 Interop 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8c191-175">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="8c191-176">Cloud Video Interop은 파트너가 제공하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-176">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="8c191-177">문제가 발생하는 경우 첫 번째 단계는 Teams 클라이언트가 설치되어 있는 디바이스를 연결하고 문제를 일으키는 Cloud Video Interop 디바이스와 동일한 세그먼트에 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-177">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="8c191-178">Teams가 이 세그먼트에서 올바르게 작동하고 파트너가 제공한 모든 네트워킹 및 구성 지침을 따르는 경우 추가 문제 해결을 위해 파트너에게 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-178">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="8c191-179">Cloud Video Interop용 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c191-179">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="8c191-180">다음 PowerShell cmdlet은 Cloud Video Interop 배포를 자동화(부분적으로)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-180">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="8c191-181">**Get-CsTeamsVideoInteropServicepolicy:** Microsoft는 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 지원되는 각 파트너에 대해 미리 생성된 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-181">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="8c191-182">이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 생성된 정책을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-182">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="8c191-183">cmdlet을 사용하여 하나 이상의 사용자에게 이 정책을 할당할 Grant-CsTeamsVideoInteropServicePolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-183">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="8c191-184">**Grant-CsTeamsVideoInteropServicePolicy**: 이 cmdlet을 사용하면 조직에서 사용할 미리 생성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-184">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="8c191-185">**New-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 사용할 지원되는 CVI 파트너에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-185">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="8c191-186">**Set-CsVideoInteropServiceProvider:** 이 cmdlet을 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-186">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="8c191-187">**Get-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직 내에서 사용하도록 구성된 모든 공급자를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-187">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="8c191-188">**Remove-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 더 이상 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c191-188">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>