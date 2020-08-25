---
title: Microsoft Teams 보안 가이드
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 업무 공간의 공유 컴퓨터에서 Microsoft Teams 를 안전하게 사용하기 위한 지침
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: a723a7300febde4eaa5045b9b1318a3e0cafe779
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860836"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="66eb8-103">공유 컴퓨터에서 Microsoft Teams 를 안전하게 사용</span><span class="sxs-lookup"><span data-stu-id="66eb8-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="66eb8-104">가능한 경우 *권장* 기업은 클라이언트 디바이스에 제로 트러스트 접근 방식을 사용하여 디바이스 관리 기능, 디바이스 상태 점검 및 정책 시행, 디바이스 수준 암호화 및 기타 보안 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="명시적 검증, 최소 권한, 위반 가정(핵심 제로 트러스트 원칙)을 파란색 원으로 표시하는 제로 트러스트 그림":::

<span data-ttu-id="66eb8-106">관리자는 검증, 최소 권한을 주장하고 사용자와 데이터 모두에 대한 위험을 최소화하는 조치로 이어지는 표준인 타협을 *가정*함으로써 매우 안전한 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="66eb8-107">제로 트러스트 원리에 대한 자세한 내용은 [ 이 비디오](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)를 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-107">For a deeper examination of Zero Trust principles, see [these videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="66eb8-108">공용 컴퓨터에서 Microsoft Teams를 안전하게 사용하기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="66eb8-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="66eb8-109">모든 시나리오에서 이것이 가능하거나 실용적이지 않을 수 있다는 점을 인식한 보안 관리자는 공유 컴퓨터 또는 관리되지 않는 장치의 Teams를 최대한 사용하기 위한 지침을 따르는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="66eb8-110">가능한 한 신속하게 지침을 준수하도록 계획을 수립해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="66eb8-111">운영 체제 플랫폼 보안 기능 활용</span><span class="sxs-lookup"><span data-stu-id="66eb8-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="66eb8-112">운영 체제가 운영 체제 제공자의 자동 업데이트를 설치하도록 구성되어 있는지 확인합니다(Microsoft 시스템의 경우 [**Windows 업데이트**](https://support.microsoft.com/help/12373/windows-update-faq)를 통해 이 작업을 수행할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="66eb8-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    2. <span data-ttu-id="66eb8-113">[**bitlocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 같은 디바이스 암호화 기능이 설정되어 있고 디바이스에 액세스하는 데 사용되는 키가 보호되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-113">Ensure that any device encryption capabilities such as [**bitlocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) are enabled, and the key used to access the device is secured.</span></span>
    1. <span data-ttu-id="66eb8-114">디바이스에서 [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)에서 제공하는 것과 같은 바이러스 백신 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-114">Use anti-virus capabilities such as those offered by [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="66eb8-115">시스템의 각 사용자마다 [별도 사용자 계정](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-115">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="66eb8-116">비관리 기능(예: 웹 검색, 팀 실행 등)에 대해 관리자 권한을 부여하거나 사용하지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="66eb8-116">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

2. <span data-ttu-id="66eb8-117">브라우저 보안 기능 활용</span><span class="sxs-lookup"><span data-stu-id="66eb8-117">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="66eb8-118">개인 검색 세션을 사용하여 디스크에 유지되는 데이터 및 기록을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-118">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="66eb8-119">예를 들어 [Microsoft Edge의 inPrivate 브라우징](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Google Chrome의 시크릿 브라우징](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) 또는 비공개 브라우징을위한 특정 브라우저 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-119">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="66eb8-120">비공개 검색을 *기본값*으로 사용하도록 시스템 동작을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-120">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

3. <span data-ttu-id="66eb8-121">다운로드 가능한 Teams 클라이언트가 아닌 [Teams 웹 앱](https://teams.microsoft.com)(*웹* 클라이언트라고도 함)을 찾아서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-121">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

4. <span data-ttu-id="66eb8-122">공유 시스템 사용을 마쳤으면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-122">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="66eb8-123">[Teams에서 로그아웃](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)</span><span class="sxs-lookup"><span data-stu-id="66eb8-123">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="66eb8-124">모든 브라우저 탭과 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-124">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="66eb8-125">장치에서 로그아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-125">Sign out of the device.</span></span>

<span data-ttu-id="66eb8-126">위의 항목은 모든 사례를 포괄하는 모범 사례 또는 보안 제어의 포괄적인 목록이 아니며 사용자 환경에서 수행할 수 있는 추가 작업이 있을 수 있습니다(예: 보안 관리자는 [Office 365 ATP 플랜 1 또는 2가 있는 경우](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) Teams에 대해 안전한 링크 및 안전한 첨부 파일을 사용하도록 선택할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="66eb8-126">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="66eb8-127">그러나 이러한 단계는 공유 장치에서 Teams 를 사용하기 위한 지침을 구축하기 위한 출발점입니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-127">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="66eb8-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="66eb8-128">More Information</span></span>

[<span data-ttu-id="66eb8-129">구성 관리자의 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="66eb8-129">Bitlocker in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="66eb8-130">Intune의 Windows 10용 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="66eb8-130">Bitlocker for Windows 10 in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="66eb8-131">Intune의 끝점 보안</span><span class="sxs-lookup"><span data-stu-id="66eb8-131">Endpoint security in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

<span data-ttu-id="66eb8-132">Windows 보안에서 Microsoft Defender 바이러스 백신을 [사용](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)하고 [검사를 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)합니다.</span><span class="sxs-lookup"><span data-stu-id="66eb8-132">[Enable](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="66eb8-133">Microsoft Defender 보안 센터 문서</span><span class="sxs-lookup"><span data-stu-id="66eb8-133">Microsoft Defender security center article</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="66eb8-134">Teams 웹 클라이언트/teams 웹 앱</span><span class="sxs-lookup"><span data-stu-id="66eb8-134">Teams web client/teams web app</span></span>](../get-clients.md#web-client)

[<span data-ttu-id="66eb8-135">보안 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66eb8-135">Security and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-security-guide)
