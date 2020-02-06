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
description: 올바른 펌웨어를 얻고, 필요한 경우 업데이트 하 고, 라이선스를 할당 하 고, 비즈니스용 Skype online 휴대폰용 설정을 구성 하는 배포 단계를 알아보세요.
ms.openlocfilehash: efcea04a454d846c0140e9d1dba561da228df1de
ms.sourcegitcommit: a61d33fe15982bd8a34f1759b6b89be5aa699fe3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2020
ms.locfileid: "41784755"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="4e57b-103">비즈니스용 Skype Online 휴대폰 배포</span><span class="sxs-lookup"><span data-stu-id="4e57b-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="4e57b-104">이 배포 가이드는 비즈니스용 Skype Online IP 전화를 배포 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="4e57b-105">전화 번호를 사용 하는 모든 유형의 기업은 사용자가 음성 전화를 걸고 받을 수 있으며, 비즈니스를 위해 중요 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="4e57b-106">전화 번호가 있는 사용자는 IP 전화, Pc, 모바일 장치를 비롯 한 모든 비즈니스용 Skype 장치에서 음성 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="4e57b-107">비즈니스용 [Skype Online에 대 한 전화를](getting-phones-for-skype-for-business-online.md)읽어 Skype FOR business IP 전화에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="4e57b-108">IP 휴대폰용 배포 단계</span><span class="sxs-lookup"><span data-stu-id="4e57b-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="4e57b-109">1 단계-제조업체의 관리자 가이드 및 전화 설명서 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e57b-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="4e57b-110">시작 하기 전에 전화 제조업체의 관리 가이드 및 전화 사용자 설명서를 다운로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="4e57b-111">Polycom 휴대폰용 [Poly 설명서 라이브러리](https://documents.polycom.com/category/voice)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="4e57b-112">옛 Alink 휴대폰의 경우에는 [옛 Alink 비즈니스용 SKYPE HD SIP 전화 솔루션](http://www.yealink.com/products_top_2.html)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="4e57b-113">오디오 통화 전화의 경우 [오디오 코드 프로비저닝 관리 가이드](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="4e57b-114">2 단계-비즈니스용 Skype 지원 IP 전화 및 펌웨어를 구매 또는 마이그레이션 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="4e57b-115">비즈니스용 Skype Online 지원 되는 휴대폰 및 펌웨어가 비즈니스용 Skype 서버와도 호환 되지만, 반대의 경우는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="4e57b-116">지원 되는 휴대폰 및 펌웨어를 구입 하거나 프로 비전 하는 경우 비즈니스용 [Skype Online 전화](getting-phones-for-skype-for-business-online.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="4e57b-117">3 단계-올바른 펌웨어가 설치 되어 있는지 확인 하 고, 필요한 경우 펌웨어를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="4e57b-118">휴대폰의 펌웨어 버전을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="4e57b-119">용</span><span class="sxs-lookup"><span data-stu-id="4e57b-119">For:</span></span>
  
- <span data-ttu-id="4e57b-120">**Polycom vvx 휴대폰**의 경우 **설정** > **상태** > **플랫폼** > **응용 프로그램** > **메인**으로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="4e57b-121">**옛 alink 휴대폰**의 경우 메인 전화 화면에서 **상태로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="4e57b-122">**오디오 코드 전화**, 시작 화면에서 **메뉴** > **디바이스 상태** > **펌웨어 버전** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e57b-123">전화 정보에 대 한 원격 액세스는 제조업체 관리 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="4e57b-124">위의 링크에서 사용자 안내서 및 전화 매뉴얼을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="4e57b-125">**Lpe (Lync Phone Edition) 휴대폰용**시작 화면에서 **메뉴** > **시스템 정보** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="4e57b-126">4 단계-장치 업데이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4e57b-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="4e57b-127">5.5.1 이전의 Polycom 펌웨어에는 비즈니스용 Skype 구현 "전화 잠금"으로 대체 되는 제조업체 관련 장치 잠금 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="4e57b-128">5.5.1에서 "Device Lock"으로 보안이 설정 된 전화를 업그레이드 하면 "전화-잠금"을 사용 하 여 "장치 잠금"에서 PIN 코드를 상속 받지 않으므로 안전 하지 않은 전화기를 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="4e57b-129">"장치 잠금"을 활성화 한 사용자는 다음 Polycom 디바이스 프로필 매개 변수를 사용 하 여 사용자에 게 업그레이드 시간 (popUpSK, enabled = 1)을 제어 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="4e57b-130">펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="4e57b-131">모든 비즈니스용 Skype 인증 휴대폰의 펌웨어가 비즈니스용 Skype 업데이트 서버에 업로드 되며 기본적으로 모든 전화기에서 장치 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="4e57b-132">휴대폰 및 폴링 간격의 비활성 시간에 따라 전화는 자동으로 최신 인증 된 빌드를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="4e57b-133">[Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet을 사용 하 고 _enabledeviceupdate_ 매개 변수를로 `false`설정 하 여 장치 업데이트 설정을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![전화 배포를 보여주는 스크린샷](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="4e57b-135">새 펌웨어를 사용할 수 있고 다운로드 및 설치할 준비가 되 면 휴대폰에서 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="4e57b-136">Polycom 휴대폰은 사용자에 게 알리고 **업데이트** 또는 **연기할**수 있는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![업데이트 및 연기 옵션을 보여 주는 스크린샷](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="4e57b-138">Polycom 휴대폰의 경우 **Swupdate**를 선택 하 여 휴대폰에서 펌웨어를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![SwUpdate 옵션을 보여 주는 스크린샷](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="4e57b-140">파트너 프로비저닝 시스템을 사용 하 여 펌웨어 업데이트를 관리 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="4e57b-141">고급 전화 사용자 지정을 비롯 한 파트너 프로비저닝 시스템 관리에 대 한 자세한 내용은 제조업체 관리 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4e57b-142">업데이트 루프를 방지 하려면 단일 장치 업데이트 기관 (대역내 장치 업데이트 또는 타사 프로비저닝 서버)을 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="4e57b-143">5 단계-구성 및 인프라 전화 설정</span><span class="sxs-lookup"><span data-stu-id="4e57b-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="4e57b-144">비즈니스용 Skype 대역 내 관리 Windows PowerShell cmdlet을 사용 하 여 가장 일반적으로 사용 되는 전화 옵션 및 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4e57b-145">이러한 매개 변수 및 설정에 대 한 자세한 내용은 [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-145">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="4e57b-146">네트워크 인프라 계획에 대해서는 [Skype 운영 프레임 워크](https://www.skypeoperationsframework.com/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="4e57b-147">6 단계-사용자가 로그인 하기 위해 준비</span><span class="sxs-lookup"><span data-stu-id="4e57b-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="4e57b-148">사용자가 비즈니스용 Skype Online 휴대폰에 성공적으로 로그인 하 여 전화를 걸 수 있도록 하려면 사용자에 게 올바른 라이선스가 할당 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="4e57b-149">최소한 전화 시스템 라이선스와 통화 요금제를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="4e57b-150">추가 정보는 비즈니스용 [skype 및 Microsoft 팀 추가 기능 라이선스](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 를 확인 하 고 [비즈니스용 Skype 및 microsoft 팀 라이선스를 할당할](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="4e57b-151">[전화 시스템 및 통화 요금제](/microsoftteams/calling-plan-landing-page) 를 읽고 통화 요금제에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="4e57b-152">온라인 사용자에 게 제공 되는 **로그인 옵션** 은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="4e57b-153">**Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom 전화 로그온을 보여 주는 스크린샷](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="4e57b-155">**T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![옛 Alink 전화 로그온을 보여 주는 스크린샷](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="4e57b-157">제조업체에서 지 원하는 로그인 옵션에 대 한 자세한 내용은 [비즈니스용 Skype Online에서 전화 받기](getting-phones-for-skype-for-business-online.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="4e57b-158">**사용자 ID** 휴대폰의 키패드 또는 화상 키보드 (사용 가능한 경우)를 사용 하 여 사용자는 조직의 사용자 이름 및 암호를 사용 하 여 휴대폰에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="4e57b-159">예를 들어 사용자 이름에 <em>amosm@contoso.com</em> 와 같은 UPN 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![로그인 화면을 보여 주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="4e57b-161">LPE 및 파트너 IP 전화의 비즈니스용 Skype Online에는 PIN 인증이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="4e57b-162">**PC 사용** 사용자 PC에 설치 된 이더넷 (BToE) 소프트웨어를 사용 하는 경우 사용자는 Windows 비즈니스용 Skype 앱의 인증 창을 통해 전화에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="4e57b-163">다른 정보에 대 한 [디바이스 페어링 및 이더넷 (btoe))을 통해 더 잘 연결 된 경우에는 7 단계 (선택 사항)](deploying-skype-for-business-online-phones.md#BK_BTOE) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="4e57b-164">사용자는 조직의 사용자 이름 및 암호를 사용 하 여 휴대폰에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="4e57b-165">예를 들어 사용자 이름에 <em>amosm@contoso.com</em> 와 같은 UPN 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![로그인 화면을 보여 주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="4e57b-167">**웹 로그인 사용**: 온라인 사용자가 표준 웹 브라우저를 사용 하 여 인증 하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="4e57b-168">사용자에 게 브라우저를 사용 하 여 로그인 할 때 수행할 수 있는 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="4e57b-169">**Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom 지침을 보여 주는 스크린샷](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="4e57b-171">**T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![옛 Alink 명령을 보여주는 스크린샷](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="4e57b-173">생성 되는 코드는 15 분 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="4e57b-174">만료 되 면 사용자는 휴대폰에 따라 새 코드를 생성 하기 위해 **다시 시도** 또는 **확인** 을 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="4e57b-175">**Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![만료 된 Polycom 코드를 보여 주는 스크린샷](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="4e57b-177">**T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![만료 된 옛 Alink 코드를 보여 주는 스크린샷](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="4e57b-179">브라우저를 사용 하 여 휴대폰에 표시 된 주소로 이동 하 고 비즈니스용 Skype 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![전자 메일 확인을 보여 주는 스크린샷](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="4e57b-181">휴대폰에 표시 되는 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-181">Enter the code shown on the phone.</span></span>
    
     ![로그인 화면에 코드 입력이 표시 된 스크린샷](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="4e57b-183">사이트에 "[전화 제조업체 이름] **비즈니스용 Skype 인증 전화**"가 표시 되는지 확인 하 고 **계속**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![이름 확인을 보여 주는 스크린샷](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="4e57b-185">사용자의 자격 증명을 클릭 하거나 **다른 계정 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![자격 증명 옵션을 보여 주는 스크린샷](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="4e57b-187">다음 페이지가 표시 되 면 브라우저를 닫는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![확인 메시지를 보여주는 스크린샷](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="4e57b-189">비즈니스용 Skype Online 지원에 대 한 LPE 전화는 USB 테더 링만 통해 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="4e57b-190">**지원 되는 배포** 아래 표에는 Exchange 통합, MFA (다단계 인증을 사용 하는 최신 인증), 비즈니스용 Skype Online 및 온-프레미스를 비롯 하 여 현재 지원 되는 배포 모델에 대 한 지원 되는 인증 유형이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e57b-191">**비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="4e57b-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="4e57b-192">**교환**</span><span class="sxs-lookup"><span data-stu-id="4e57b-192">**Exchange**</span></span> <br/> |<span data-ttu-id="4e57b-193">**휴대폰 로그인 방법**</span><span class="sxs-lookup"><span data-stu-id="4e57b-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="4e57b-194">**비즈니스용 Skype 액세스**</span><span class="sxs-lookup"><span data-stu-id="4e57b-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="4e57b-195">**최신 인증 및 MFA를 사용 하는 Exchange Access**</span><span class="sxs-lookup"><span data-stu-id="4e57b-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="4e57b-196">**최신 인증 및 MFA를 사용 하는 Exchange Access**</span><span class="sxs-lookup"><span data-stu-id="4e57b-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="4e57b-197">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-197">Online</span></span>  <br/> |<span data-ttu-id="4e57b-198">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-198">Online</span></span>  <br/> |<span data-ttu-id="4e57b-199">웹 로그인</span><span class="sxs-lookup"><span data-stu-id="4e57b-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="4e57b-200">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-200">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-201">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-201">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-202">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-202">Yes</span></span>  <br/> |
|<span data-ttu-id="4e57b-203">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-203">Online</span></span>  <br/> |<span data-ttu-id="4e57b-204">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-204">Online</span></span>  <br/> |<span data-ttu-id="4e57b-205">사용자 이름/비밀 번호</span><span class="sxs-lookup"><span data-stu-id="4e57b-205">Username/Password</span></span>  <br/> |<span data-ttu-id="4e57b-206">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-206">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-207">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-207">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-208">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-208">No</span></span>  <br/> |
|<span data-ttu-id="4e57b-209">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-209">Online</span></span>  <br/> |<span data-ttu-id="4e57b-210">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-210">On-premises</span></span>  <br/> |<span data-ttu-id="4e57b-211">웹 로그인</span><span class="sxs-lookup"><span data-stu-id="4e57b-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="4e57b-212">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-212">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-213">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-213">No</span></span>  <br/> |<span data-ttu-id="4e57b-214">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-214">No</span></span>  <br/> |
|<span data-ttu-id="4e57b-215">온라인</span><span class="sxs-lookup"><span data-stu-id="4e57b-215">Online</span></span>  <br/> |<span data-ttu-id="4e57b-216">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-216">On-Premises</span></span>  <br/> |<span data-ttu-id="4e57b-217">사용자 이름/비밀 번호</span><span class="sxs-lookup"><span data-stu-id="4e57b-217">Username/Password</span></span>  <br/> |<span data-ttu-id="4e57b-218">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-218">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-219">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-219">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-220">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-220">No</span></span>  <br/> |
|<span data-ttu-id="4e57b-221">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-221">On-premises</span></span>  <br/> |<span data-ttu-id="4e57b-222">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="4e57b-223">PIN 인증</span><span class="sxs-lookup"><span data-stu-id="4e57b-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="4e57b-224">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-224">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-225">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-225">No</span></span>  <br/> |<span data-ttu-id="4e57b-226">아니요</span><span class="sxs-lookup"><span data-stu-id="4e57b-226">No</span></span>  <br/> |
|<span data-ttu-id="4e57b-227">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-227">On-premises</span></span>  <br/> |<span data-ttu-id="4e57b-228">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="4e57b-229">사용자 이름/비밀 번호</span><span class="sxs-lookup"><span data-stu-id="4e57b-229">Username/Password</span></span>  <br/> |<span data-ttu-id="4e57b-230">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-230">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-231">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-231">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-232">해당 없음</span><span class="sxs-lookup"><span data-stu-id="4e57b-232">N/A</span></span>  <br/> |
|<span data-ttu-id="4e57b-233">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-233">On-premises</span></span>  <br/> |<span data-ttu-id="4e57b-234">온라인/온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4e57b-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="4e57b-235">PC를 통한 로그인 (BTOE)</span><span class="sxs-lookup"><span data-stu-id="4e57b-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="4e57b-236">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-236">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-237">예</span><span class="sxs-lookup"><span data-stu-id="4e57b-237">Yes</span></span>  <br/> |<span data-ttu-id="4e57b-238">해당 없음</span><span class="sxs-lookup"><span data-stu-id="4e57b-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="4e57b-239">**전화 기능** 기능 집합은 IP 전화 파트너에 따라 약간씩 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="4e57b-240">전체 기능 집합 및 각 전화 제조업체의 기능에 대 한 자세한 내용은 [비즈니스용 Skype Online에서 전화 받기](getting-phones-for-skype-for-business-online.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="4e57b-241">**전화-잠금** 기능은 휴대폰을 보호 하는 데 사용 되는 비즈니스용 Skype 인증 전화에서 최근에 소개 된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="4e57b-242">이 설정을 사용 하면 인증에 성공한 사용자에 게 PIN을 만들라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="4e57b-243">일단 만든 유휴 시간 제한이 만료 되는 경우, 사용자가 수동으로 휴대폰을 잠그거나 전화 연결을 사용 하 여 PC 잠금과 휴대폰 잠금을 동기화 할 때 전화가 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="4e57b-244">전화 잠금 PIN을 여러 번 잘못 입력 한 경우, 휴대폰은 사용자에 게 로그인 하거나 전화를 잠금 해제 하기 위해 관리자의 코드가 필요 하지만,이는 휴대폰 파트너에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="4e57b-245">사용자의 PIN은 6 ~ 15 자리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="4e57b-246">조직에 대해 전화 (기본적으로 설정 되어 있음)를 사용 하지 않도록 설정할 수 있으며, 유휴 시간 제한을 변경 하 고, 사용자가 inband-설정을 사용 하지 않거나 잠겨 있는 동안 전화를 걸 수 있는지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="4e57b-247">이러한 설정에 대 한 자세한 내용은 [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="4e57b-248">7 단계 (선택 사항)-이더넷 (BToE)를 통해 디바이스 페어링과 더 나은 기능을 함께 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4e57b-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="4e57b-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="4e57b-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="4e57b-250">BToE는 사용자의 휴대폰을 Windows 용 비즈니스용 Skype 앱과 쌍을 이루는 파트너 IP 전화에 대 한 전화기 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="4e57b-251">BToE 지를 통해 사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="4e57b-252">비즈니스용 Skype 데스크톱 앱 (PC 사용)을 사용 하 여 자신의 IP 전화에 로그인</span><span class="sxs-lookup"><span data-stu-id="4e57b-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="4e57b-253">전화 동기화-PC 잠금과 잠금</span><span class="sxs-lookup"><span data-stu-id="4e57b-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="4e57b-254">클릭 하 여 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="4e57b-254">Click to call</span></span>
    
<span data-ttu-id="4e57b-255">BToE는 두 가지 모드 ( *자동* (기본값)와 *수동* )에서 작동 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="4e57b-256">비즈니스용 Skype 대역내 설정을 사용 하는 사용자에 대해 사용 하도록 설정 (기본값)/사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="4e57b-257">*수동* 모드에서 작업 하는 경우 사용자는 Windows 앱과 휴대폰을 연결 하는 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="4e57b-258">**사용자에 게 BToE를 배포 하려면**</span><span class="sxs-lookup"><span data-stu-id="4e57b-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="4e57b-259">PC 포트를 사용 하 여 PC를 전화기에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![PC 연결을 보여 주는 스크린샷](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="4e57b-261">아래 링크에서 제조업체 웹 사이트의 최신 BToE 소프트웨어를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="4e57b-262">사용자 환경을 개선 하기 위해 Microsoft 끝점 구성 관리자와 같은 관리 배포 솔루션을 사용 하 여 BToE 소프트웨어를 배포 하 고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="4e57b-263">구성 관리자를 사용 하는 방법에 대 한 도움말은 [Configuration manager에서 패키지 및 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="4e57b-264">Polycom BToE 소프트웨어 다운로드 사이트</span><span class="sxs-lookup"><span data-stu-id="4e57b-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="4e57b-265">옛 alink 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e57b-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="4e57b-266">오디오 코드 BToE 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e57b-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="4e57b-267">BToE에 대 한 서버 설정은 기본적으로 **사용** 으로 설정 되 고 **자동 모드** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="4e57b-268">이러한 설정을 변경 하려면 [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e57b-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e57b-269">BToE는 현재 Mac 및 VDI 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e57b-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4e57b-270">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e57b-270">Related topics</span></span>
[<span data-ttu-id="4e57b-271">비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="4e57b-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="4e57b-272">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="4e57b-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="4e57b-273">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="4e57b-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
