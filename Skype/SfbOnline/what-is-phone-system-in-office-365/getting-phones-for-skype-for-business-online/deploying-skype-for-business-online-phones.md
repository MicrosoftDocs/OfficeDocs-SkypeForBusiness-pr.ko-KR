---
title: 비즈니스용 Skype Online 휴대폰 배포
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 비즈니스용 Skype 온라인 전화에 대한 설정을 구성하는 배포 단계에 대해 알아보십시오.
ms.openlocfilehash: 41c6ef53469ab2de3699fd17a2d181477e143fae
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220448"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="94a61-103">비즈니스용 Skype Online 휴대폰 배포</span><span class="sxs-lookup"><span data-stu-id="94a61-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="94a61-104">이 배포 가이드는 비즈니스용 Skype Online IP 휴대폰을 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="94a61-105">모든 유형의 비즈니스에서 전화 번호를 사용하면 사용자가 음성 통화를 걸고 받을 수 있으며 비즈니스를 해야 하는 중요한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="94a61-106">전화 번호가 있는 사용자는 IP 전화, PC 및 모바일 장치를 비롯한 모든 비즈니스용 Skype 장치에서 음성 통화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="94a61-107">비즈니스용 Skype Online용 전화기에서 비즈니스용 Skype IP 전화에 대해 자세히 [배울 수 있습니다.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="94a61-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="94a61-108">IP 휴대폰에 대한 배포 단계</span><span class="sxs-lookup"><span data-stu-id="94a61-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="94a61-109">1단계 - 제조업체의 관리자 가이드 및 전화 설명서 다운로드</span><span class="sxs-lookup"><span data-stu-id="94a61-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="94a61-110">시작하기 전에 휴대폰 제조업체의 관리 가이드 및 전화 사용자 설명서를 다운로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="94a61-111">Polycom 휴대폰의 경우 [Poly 설명서 라이브러리를 참조하세요.](https://documents.polycom.com/category/voice)</span><span class="sxs-lookup"><span data-stu-id="94a61-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="94a61-112">Yealink 휴대폰의 경우 [Yealink 비즈니스용 Skype HD SIP Phones 솔루션을 참조하세요.](http://www.yealink.com/products_top_2.html)</span><span class="sxs-lookup"><span data-stu-id="94a61-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="94a61-113">AudioCodes 휴대폰의 경우 오디오 코드 프로비전 관리 [가이드를 참조하세요.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)</span><span class="sxs-lookup"><span data-stu-id="94a61-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="94a61-114">2단계 - 비즈니스용 Skype 지원 IP 전화 및 펌웨어를 구입하거나 마이그레이션하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="94a61-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="94a61-115">비즈니스용 Skype Online 지원 전화 및 펌웨어도 비즈니스용 Skype Server와 호환되지만 항상 그렇지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="94a61-116">지원되는 휴대폰과 펌웨어를 구입하거나 프로비전하는지 확인은 [비즈니스용 Skype Online용 전화기 다운로드를 참조하세요.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="94a61-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="94a61-117">3단계 - 올바른 펌웨어가 설치되어 있는지 확인하고 필요한 경우 펌웨어를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="94a61-118">휴대폰에서 펌웨어 버전을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="94a61-119">For:</span><span class="sxs-lookup"><span data-stu-id="94a61-119">For:</span></span>
  
- <span data-ttu-id="94a61-120">**Polycom VVX 휴대폰에서** 설정 상태 플랫폼 애플리케이션  >    >    >  **주로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="94a61-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="94a61-121">**Yealink 전화기에서** 주 전화 **화면의** 상태로 이동</span><span class="sxs-lookup"><span data-stu-id="94a61-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="94a61-122">**AudioCodes 휴대폰의** 시작 화면에서 **메뉴** 디바이스 상태  >    >  **펌웨어** 버전으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94a61-123">전화 세부 정보에 대한 원격 액세스는 제조업체 관리 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="94a61-124">사용자 가이드 및 전화 설명서는 위의 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="94a61-125">**LPE(Lync Phone Edition)** 휴대폰을 시작 화면에서 **메뉴**  >  **시스템** 정보로 이동</span><span class="sxs-lookup"><span data-stu-id="94a61-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="94a61-126">4단계 - 디바이스 업데이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="94a61-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="94a61-127">5.5.1.X 이전의 Polycom 펌웨어에는 비즈니스용 Skype 구현 "Phone-Lock"으로 대체되는 제조업체별 장치 잠금 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="94a61-128">"Device-Lock"으로 보안이 유지된 5.4.X.X에서 "Phone-Lock"으로 보안이 유지된 휴대폰을 5.5.1.X로 업그레이드하면 "Device-Lock"에서 PIN 코드를 상속하지 않습니다. 이 경우 휴대폰이 보안되지 않은 것으로 남을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="94a61-129">"Device-Lock"을 활성화한 사용자는 사용자에게 업그레이드 시간(lync.deviceUpdate.popUpSK.enabled=1)을 제어하도록 다음 Polycom 디바이스 프로필 매개 변수를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="94a61-130">펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="94a61-131">모든 비즈니스용 Skype 인증 휴대폰 펌웨어는 비즈니스용 Skype 업데이트 서버에 업로드됩니다. 장치 업데이트는 기본적으로 모든 휴대폰에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="94a61-132">휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰은 자동으로 인증된 최신 빌드를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="94a61-133">[Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet을 사용하고 _EnableDeviceUpdate_ 매개 변수를 으로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![휴대폰 배포를 보여주는 스크린샷](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="94a61-135">새 펌웨어를 사용할 수 있으며 다운로드 및 설치가 준비되면 휴대폰에서 사용자에게 알릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="94a61-136">Polycom 전화기에서 사용자에게 알리고 업데이트 또는  연기 옵션을 **제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="94a61-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![업데이트 및 연기 옵션을 보여주는 스크린샷](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="94a61-138">Polycom 휴대폰의 경우 **SwUpdate를** 선택하여 휴대폰의 펌웨어를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![SwUpdate 옵션을 보여주는 스크린샷](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="94a61-140">파트너 프로비전 시스템을 사용하여 펌웨어 업데이트를 관리하기로 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="94a61-141">고급 전화 사용자 지정을 포함한 파트너 프로비전 시스템 관리는 제조업체 관리 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="94a61-142">업데이트 루프를 방지하려면 단일 디바이스 업데이트 기관(대역 내 디바이스 업데이트 또는 타사 프로비전 서버)이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="94a61-143">5단계 - 구성 및 인프라 전화 설정</span><span class="sxs-lookup"><span data-stu-id="94a61-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="94a61-144">비즈니스용 Skype 대역 내 관리 cmdlet을 사용하여 가장 일반적으로 사용되는 전화 옵션 및 정책을 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="94a61-145">이러한 매개 변수 및 설정에 대한 자세한 내용은 [Set-CsIPPhonePolicy를](https://technet.microsoft.com/library/mt629497.aspx) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-145">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="94a61-146">네트워크 인프라 계획은 [Skype Operations Framework를 참조하세요.](https://www.skypeoperationsframework.com/)</span><span class="sxs-lookup"><span data-stu-id="94a61-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="94a61-147">6단계 - 사용자가 로그인할 수 있도록 준비</span><span class="sxs-lookup"><span data-stu-id="94a61-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="94a61-148">사용자가 비즈니스용 Skype Online 전화에 성공적으로 로그인하고 전화를 걸 수 있도록 설정하려면 사용자에게 올바른 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="94a61-149">최소한 전화 시스템 라이선스 및 통화 플랜을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="94a61-150">자세한 내용은 비즈니스용 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 및 Microsoft Teams 추가 기능 라이선스를 보고 비즈니스용 Skype 및 [Microsoft Teams 라이선스를 할당할 수 있습니다.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="94a61-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="94a61-151">전화 시스템 및 통화 요금제에서 통화 요금제에 대한 자세한 정보를 찾을 [수 있습니다.](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="94a61-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="94a61-152">**온라인 사용자가** 사용할 수 있는 로그인 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="94a61-153">**Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom 전화 로그온을 보여주는 스크린샷](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="94a61-155">**Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 전화 로그온을 보여주는 스크린샷입니다.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="94a61-157">제조업체에서 지원하는 로그인 옵션에 대한 자세한 내용은 비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="94a61-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="94a61-158">**사용자 ID** 휴대폰의 키패드 또는 화면 키보드(사용 가능한 경우)를 사용하여 사용자는 조직의 사용자 이름 및 암호를 사용하여 휴대폰에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="94a61-159">예를 들어 사용자 이름에 대해 amosm@contoso.com <em>UPN</em>  형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![로그인 화면을 보여주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="94a61-161">PIN 인증은 LPE 및 파트너 IP 전화용 비즈니스용 Skype Online에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="94a61-162">**PC 사용** BToE(Better Together over Ethernet) 소프트웨어가 사용자의 PC에 설치되어 사용하도록 설정되면 사용자는 Windows 비즈니스용 Skype 앱의 인증 창을 사용하여 휴대폰에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="94a61-163">[7단계(선택 사항) -](deploying-skype-for-business-online-phones.md#BK_BTOE) 디바이스 페어링이 있는 경우 BToE(이더넷)를 통해 더 잘 짝을 이루는 경우 다른 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="94a61-164">사용자는 조직의 사용자 이름 및 암호를 사용하여 휴대폰에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="94a61-165">예를 들어 사용자 이름에 대해 amosm@contoso.com  <em>UPN</em>  형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![로그인 화면을 보여주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="94a61-167">**웹 로그인 사용:** 이 방법은 온라인 사용자가 표준 웹 브라우저를 사용하여 인증할 수 있는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="94a61-168">사용자가 브라우저를 사용하여 로그인할 때 따라야 할 지침 집합이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="94a61-169">**Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom 지침을 보여주는 스크린샷](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="94a61-171">**Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 지침을 보여주는 스크린샷](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="94a61-173">생성된 코드는 15분 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="94a61-174">만료되면 사용자는 휴대폰에 따라 **다시** 시도 또는  확인을 클릭하여 새 코드를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="94a61-175">**Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![만료된 Polycom 코드를 보여주는 스크린샷](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="94a61-177">**Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![만료된 Yealink 코드를 보여주는 스크린샷](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="94a61-179">브라우저를 사용하여 전화에 표시된 주소로 이동하고 비즈니스용 Skype 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![전자 메일 확인을 보여주는 스크린샷](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="94a61-181">휴대폰에 표시된 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-181">Enter the code shown on the phone.</span></span>
    
     ![로그인 화면에 코드 입력을 보여주는 스크린샷](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="94a61-183">사이트에 "[휴대폰 제조업체 이름] **비즈니스용 Skype 인증 전화"가 표시되고** 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="94a61-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![이름 확인을 보여주는 스크린샷](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="94a61-185">사용자의 자격 증명을 클릭하거나 다른 계정 **사용:**</span><span class="sxs-lookup"><span data-stu-id="94a61-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![자격 증명 옵션을 보여주는 스크린샷](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="94a61-187">다음 페이지가 표시되면 브라우저를 닫는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![확인 메시지를 보여주는 스크린샷](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="94a61-189">비즈니스용 Skype Online용 LPE 휴대폰은 USB 테더링을 통해서만 로그인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="94a61-190">**지원되는 배포** 아래 표에서는 Exchange 통합, MFA(Multi-Factor Authentication)를 사용하는 최신 인증, 비즈니스용 Skype Online 및 On-프레미스를 포함하여 현재 지원되는 배포 모델에 대해 지원되는 인증 유형을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="94a61-191">**비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="94a61-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="94a61-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="94a61-192">**Exchange**</span></span> <br/> |<span data-ttu-id="94a61-193">**전화 Sign-In 방법**</span><span class="sxs-lookup"><span data-stu-id="94a61-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="94a61-194">**비즈니스용 Skype 액세스**</span><span class="sxs-lookup"><span data-stu-id="94a61-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="94a61-195">**최신 Auth 및 MFA를 사용하지 않도록 설정한 Exchange Access**</span><span class="sxs-lookup"><span data-stu-id="94a61-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="94a61-196">**최신 Auth 및 MFA를 사용하도록 설정된 Exchange Access**</span><span class="sxs-lookup"><span data-stu-id="94a61-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="94a61-197">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-197">Online</span></span>  <br/> |<span data-ttu-id="94a61-198">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-198">Online</span></span>  <br/> |<span data-ttu-id="94a61-199">웹 로그인</span><span class="sxs-lookup"><span data-stu-id="94a61-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="94a61-200">예</span><span class="sxs-lookup"><span data-stu-id="94a61-200">Yes</span></span>  <br/> |<span data-ttu-id="94a61-201">예</span><span class="sxs-lookup"><span data-stu-id="94a61-201">Yes</span></span>  <br/> |<span data-ttu-id="94a61-202">예</span><span class="sxs-lookup"><span data-stu-id="94a61-202">Yes</span></span>  <br/> |
|<span data-ttu-id="94a61-203">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-203">Online</span></span>  <br/> |<span data-ttu-id="94a61-204">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-204">Online</span></span>  <br/> |<span data-ttu-id="94a61-205">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="94a61-205">Username/Password</span></span>  <br/> |<span data-ttu-id="94a61-206">예</span><span class="sxs-lookup"><span data-stu-id="94a61-206">Yes</span></span>  <br/> |<span data-ttu-id="94a61-207">예</span><span class="sxs-lookup"><span data-stu-id="94a61-207">Yes</span></span>  <br/> |<span data-ttu-id="94a61-208">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-208">No</span></span>  <br/> |
|<span data-ttu-id="94a61-209">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-209">Online</span></span>  <br/> |<span data-ttu-id="94a61-210">On-premises</span><span class="sxs-lookup"><span data-stu-id="94a61-210">On-premises</span></span>  <br/> |<span data-ttu-id="94a61-211">웹 로그인</span><span class="sxs-lookup"><span data-stu-id="94a61-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="94a61-212">예</span><span class="sxs-lookup"><span data-stu-id="94a61-212">Yes</span></span>  <br/> |<span data-ttu-id="94a61-213">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-213">No</span></span>  <br/> |<span data-ttu-id="94a61-214">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-214">No</span></span>  <br/> |
|<span data-ttu-id="94a61-215">온라인</span><span class="sxs-lookup"><span data-stu-id="94a61-215">Online</span></span>  <br/> |<span data-ttu-id="94a61-216">On-Premises</span><span class="sxs-lookup"><span data-stu-id="94a61-216">On-Premises</span></span>  <br/> |<span data-ttu-id="94a61-217">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="94a61-217">Username/Password</span></span>  <br/> |<span data-ttu-id="94a61-218">예</span><span class="sxs-lookup"><span data-stu-id="94a61-218">Yes</span></span>  <br/> |<span data-ttu-id="94a61-219">예</span><span class="sxs-lookup"><span data-stu-id="94a61-219">Yes</span></span>  <br/> |<span data-ttu-id="94a61-220">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-220">No</span></span>  <br/> |
|<span data-ttu-id="94a61-221">On-premises</span><span class="sxs-lookup"><span data-stu-id="94a61-221">On-premises</span></span>  <br/> |<span data-ttu-id="94a61-222">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="94a61-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="94a61-223">PIN 인증</span><span class="sxs-lookup"><span data-stu-id="94a61-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="94a61-224">예</span><span class="sxs-lookup"><span data-stu-id="94a61-224">Yes</span></span>  <br/> |<span data-ttu-id="94a61-225">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-225">No</span></span>  <br/> |<span data-ttu-id="94a61-226">아니요</span><span class="sxs-lookup"><span data-stu-id="94a61-226">No</span></span>  <br/> |
|<span data-ttu-id="94a61-227">On-premises</span><span class="sxs-lookup"><span data-stu-id="94a61-227">On-premises</span></span>  <br/> |<span data-ttu-id="94a61-228">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="94a61-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="94a61-229">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="94a61-229">Username/Password</span></span>  <br/> |<span data-ttu-id="94a61-230">예</span><span class="sxs-lookup"><span data-stu-id="94a61-230">Yes</span></span>  <br/> |<span data-ttu-id="94a61-231">예</span><span class="sxs-lookup"><span data-stu-id="94a61-231">Yes</span></span>  <br/> |<span data-ttu-id="94a61-232">해당 없음</span><span class="sxs-lookup"><span data-stu-id="94a61-232">N/A</span></span>  <br/> |
|<span data-ttu-id="94a61-233">On-premises</span><span class="sxs-lookup"><span data-stu-id="94a61-233">On-premises</span></span>  <br/> |<span data-ttu-id="94a61-234">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="94a61-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="94a61-235">PC(BTOE)를 통해 로그인</span><span class="sxs-lookup"><span data-stu-id="94a61-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="94a61-236">예</span><span class="sxs-lookup"><span data-stu-id="94a61-236">Yes</span></span>  <br/> |<span data-ttu-id="94a61-237">예</span><span class="sxs-lookup"><span data-stu-id="94a61-237">Yes</span></span>  <br/> |<span data-ttu-id="94a61-238">해당 없음</span><span class="sxs-lookup"><span data-stu-id="94a61-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="94a61-239">**전화 기능** 기능 집합은 IP 전화 파트너에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="94a61-240">전체 기능 집합 및 각 전화 제조업체의 기능에 대한 자세한 내용은 비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="94a61-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="94a61-241">**전화 잠금은** 휴대폰을 보호하는 데 사용되는 비즈니스용 Skype 인증 전화기에서 최근에 도입된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="94a61-242">사용하도록 설정하면 인증에 성공하면 사용자에게 PIN을 만들지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="94a61-243">사용자가 정의한 유휴 시간 제한이 만료되거나, 사용자가 휴대폰을 수동으로 잠그거나, 휴대폰 페어링을 사용하여 휴대폰 잠금을 PC 잠금과 동기화하면 휴대폰이 잠기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="94a61-244">전화 잠금 PIN을 여러 번 잘못 입력한 경우 전화기에서 사용자를 로그인하거나 관리자의 코드로 전화 잠금을 해제하도록 요구하지만 전화 파트너에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="94a61-245">사용자의 PIN은 6~15자리 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="94a61-246">조직에 대한 Phone-Lock(기본적으로 사용하도록 설정)를 사용하지 않도록 설정하고, 유휴 시간 제한을 변경하고, 사용자가 잠긴 동안 전화 통화를 걸 수 있는지 또는 인밴드 설정을 사용하지 않을지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="94a61-247">이러한 설정에 대한 자세한 내용은 [Set-CsUCPhoneConfiguration을](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a61-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="94a61-248">7단계(선택 사항) - 디바이스 페어링이 있는 경우 이더넷(BToE)을 통해 더 잘 모일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="94a61-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="94a61-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="94a61-250">BToE는 사용자의 휴대폰을 비즈니스용 Skype 앱과 페어링하는 파트너 IP 전화기용 전화기입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="94a61-251">BToE를 사용하면 사용자가</span><span class="sxs-lookup"><span data-stu-id="94a61-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="94a61-252">비즈니스용 Skype 데스크톱 앱(PC 사용)을 사용하여 IP 휴대폰에 로그인</span><span class="sxs-lookup"><span data-stu-id="94a61-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="94a61-253">PC Phone-Lock 동기화</span><span class="sxs-lookup"><span data-stu-id="94a61-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="94a61-254">클릭하여 통화</span><span class="sxs-lookup"><span data-stu-id="94a61-254">Click to call</span></span>
    
<span data-ttu-id="94a61-255">BToE는 자동(기본값) 및 수동의  두 가지 모드로 작동하도록 구성할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="94a61-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="94a61-256">또한 대역 내 비즈니스용 Skype 설정을 사용하는 사용자에 대해 활성화(기본값)/비활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="94a61-257">수동 모드에서 *작동할*  때 사용자는 Windows 앱과 휴대폰을 페어링하기 위해 추가 단계를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="94a61-258">**사용자에게 BToE를 배포하는 경우**</span><span class="sxs-lookup"><span data-stu-id="94a61-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="94a61-259">PC 포트를 사용하여 PC를 휴대폰에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![PC에 대한 연결을 보여주는 스크린샷](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="94a61-261">아래 링크에서 제조업체 웹 사이트에서 최신 BToE 소프트웨어를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="94a61-262">더 나은 사용자 환경을 위해 Microsoft Endpoint Configuration Manager와 같은 관리 배포 솔루션을 사용하여 BToE 소프트웨어를 배포하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="94a61-263">구성 관리자 사용에 대한 도움말은 Configuration Manager의 패키지 [및 프로그램을 참조합니다.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="94a61-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="94a61-264">Polycom BToE 소프트웨어 다운로드 사이트</span><span class="sxs-lookup"><span data-stu-id="94a61-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="94a61-265">Yealink BToe 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="94a61-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="94a61-266">AudioCodes BToE 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="94a61-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="94a61-267">BToE에 대한 서버 설정은 기본적으로 사용 및 자동 **모드로** 설정됩니다. </span><span class="sxs-lookup"><span data-stu-id="94a61-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="94a61-268">이러한 설정을 변경하려면 [Set-CsIPPhonePolicy를 참조하세요.](https://technet.microsoft.com/library/mt629497.aspx)</span><span class="sxs-lookup"><span data-stu-id="94a61-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="94a61-269">BToE는 현재 Mac 및 VDI 플랫폼에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="94a61-270">관련 항목</span><span class="sxs-lookup"><span data-stu-id="94a61-270">Related topics</span></span>
[<span data-ttu-id="94a61-271">비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="94a61-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="94a61-272">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="94a61-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="94a61-273">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="94a61-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
