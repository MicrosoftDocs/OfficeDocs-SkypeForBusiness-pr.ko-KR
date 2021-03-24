---
title: Skype 룸 시스템 관리 가능성 및 도구
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 이 항목을 읽고 Skype 룸 시스템의 관리 도구에 대해 자세히 알아보습니다.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093552"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="0e7d2-103">Skype 룸 시스템 관리 가능성 및 도구</span><span class="sxs-lookup"><span data-stu-id="0e7d2-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="0e7d2-104">이 항목을 읽고 Skype 룸 시스템의 관리 도구에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="0e7d2-105">관리 포털</span><span class="sxs-lookup"><span data-stu-id="0e7d2-105">Administrative Portal</span></span>

<span data-ttu-id="0e7d2-106">비즈니스용 Skype 서버 사내 배포의 경우 Skype 룸 시스템 관리 포털을 사용하여 조직 내에서 Skype 룸 시스템 배포를 적극적으로 관리하고 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="0e7d2-107">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="0e7d2-108">비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포</span><span class="sxs-lookup"><span data-stu-id="0e7d2-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="0e7d2-109">Exchange 검사 목록</span><span class="sxs-lookup"><span data-stu-id="0e7d2-109">Exchange Checklist</span></span>

- <span data-ttu-id="0e7d2-110">자동iscover가 설정되어 있으며 내부 DNS A/CNAME 레코드를 사용할 수 autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="0e7d2-111">Ping autodiscover(예: Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0e7d2-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="0e7d2-112">Microsoft 연결 분석기 도구를 사용하여 자동 검색 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="0e7d2-113">첫 번째 테스트인 "Office Outlook으로 로그온할 수 없습니다."를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="0e7d2-114">회의실에 이미 리소스 사서함이 있는 경우 Skype 룸 시스템에 대해 이 계정을 확장합니다(예: 페이지 아래쪽의 스크립트).</span><span class="sxs-lookup"><span data-stu-id="0e7d2-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="0e7d2-115">비즈니스용 Skype 검사 목록</span><span class="sxs-lookup"><span data-stu-id="0e7d2-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="0e7d2-116">다음 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="0e7d2-117">비즈니스용 Skype 모범 사례 분석기</span><span class="sxs-lookup"><span data-stu-id="0e7d2-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="0e7d2-118">비즈니스용 Skype 상태 분석 도구(Excel)</span><span class="sxs-lookup"><span data-stu-id="0e7d2-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="0e7d2-119">skype for Business Connectivity Analyzer 32비트 또는 64비트</span><span class="sxs-lookup"><span data-stu-id="0e7d2-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="0e7d2-120">[Office 365에 대한](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)유용한 새 문제 해결 및 분석 도구를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="0e7d2-121">비즈니스용 Skype 풀과 Office Web Apps 서버가 있으며 비즈니스용 Skype 클라이언트를 사용하여 PowerPoint 데크를 공유할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0e7d2-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="0e7d2-122">회의실에 이미 리소스 사서함이 있는 경우 비즈니스용 Skype에서 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="0e7d2-123">필요한 경우 회의실 시스템에 대해 DID(전화 번호)를 요청하고 Active Directory 도구에서 일반 전화 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="0e7d2-124">네트워크</span><span class="sxs-lookup"><span data-stu-id="0e7d2-124">Network</span></span>

- <span data-ttu-id="0e7d2-125">Skype 룸 시스템에 대한 유선 네트워크 연결이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="0e7d2-126">비즈니스용 Skype에 대한 네트워크 계획 가이드를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="0e7d2-127">비즈니스용 Skype 파트너에게 비즈니스용 Skype 네트워크 평가를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="0e7d2-128">비즈니스용 Skype 상태 분석 도구(Excel)에서 캡처한 성능 데이터를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="0e7d2-129">네트워크 분석 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="0e7d2-130">사전 통화 진단 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="0e7d2-131">Skype 룸 시스템 보안</span><span class="sxs-lookup"><span data-stu-id="0e7d2-131">Skype Room System Security</span></span>

<span data-ttu-id="0e7d2-132">Skype 룸 시스템은 비즈니스용 Skype 보안 모델, 권한 관리 및 SCOM과 같은 관리 도구를 사용하여 Windows 배포에 완전히 통합할 수 있는 포함된 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="0e7d2-133">기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-133">Features include:</span></span>
  
- <span data-ttu-id="0e7d2-134">사용자 모드에서 디스크 쓰기를 방지하는 쓰기 필터</span><span class="sxs-lookup"><span data-stu-id="0e7d2-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="0e7d2-135">앱 보관 - 권한이 없는 앱이 실행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="0e7d2-136">모든 USB 포트는 사용자 모드에서 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="0e7d2-137">Skype 룸 시스템 하드웨어에는 표준 앱이나 뷰어가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="0e7d2-138">모든 콘텐츠는 HTTP 또는 RDP 프로토콜을 통해 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="0e7d2-139">어플라이언스 PC는 Windows Embedded Standard 7 운영 체제를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="0e7d2-140">장치를 포함한 모든 하드웨어는 OEM 파트너가 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="0e7d2-141">AD DS(Active Directory 도메인 서비스에 대한 선택적 도메인 가입)를 통해 로컬 보안 계정 관리 및 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="0e7d2-142">비즈니스용 Skype 관리 센터를 사용하여 로컬 관리자 계정을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="0e7d2-143">Skype 룸 시스템은 표준 Microsoft 업데이트 프로세스를 통해 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="0e7d2-144">Skype 룸 시스템은 비즈니스용 Skype와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="0e7d2-145">비즈니스용 Skype는 모든 통신 모드에 종단 간 암호화 및 권한 부여를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="0e7d2-146">Skype 룸 시스템은 비즈니스용 Skype 보안 및 규정 준수 표준을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="0e7d2-147">자세한 [내용은 비즈니스용 Skype 서버의 보안 계획을](../../plan-your-deployment/security/security.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="0e7d2-148">License</span><span class="sxs-lookup"><span data-stu-id="0e7d2-148">License</span></span>

<span data-ttu-id="0e7d2-149">소프트웨어를 정 인증하는 데 KMS를 사용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="0e7d2-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="0e7d2-150">이 경우 비즈니스용 Skype 클라이언트 KMS 키를 확인하거나 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="0e7d2-151">KMS를 사용하지 않는 경우 비즈니스용 Skype 클라이언트 MAK에 대한 볼륨 라이선스 키를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="0e7d2-152">라이선스 키</span><span class="sxs-lookup"><span data-stu-id="0e7d2-152">License keys</span></span>

<span data-ttu-id="0e7d2-153">Skype 룸 시스템은 백그라운드에서 비즈니스용 Skype 데스크톱 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="0e7d2-154">Skype 룸 시스템이 도메인 구성원인 경우 KMS를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="0e7d2-155">볼륨 라이선싱 KMS 키가 있는 경우 자동으로 정품 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="0e7d2-156">볼륨 라이선스는 xxxxx-xxxxx-xxx-xx-xxx를 표시하는 MAK도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="0e7d2-157">MAK를 사용하여 정품 인증하려면 인터넷에 연결해야 하지만 KMS는 정품 인증하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="0e7d2-158">자세한 내용은 Volume activation of Office 2013을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="0e7d2-159">MAK 키를 입력하려면 OEM 설정 SRS 라이선스 \> 도구로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="0e7d2-160">상태 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-160">Click Check Status.</span></span> <span data-ttu-id="0e7d2-161">상태가 "제품이 정품 인증되지 않았습니다."라고 표시되면 키를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="0e7d2-162">정품 인증 중에 "소프트웨어 라이선스 서비스에서 제품 키가 잘못 보고되었습니다."라는 오류가 표시될 경우 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="0e7d2-163">키를 올바르게 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="0e7d2-164">다른 키가 아니라 비즈니스용 Skype MAK 키를 입력한 경우</span><span class="sxs-lookup"><span data-stu-id="0e7d2-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="0e7d2-165">시스템에 인터넷에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="0e7d2-166">전화를 통해 정품 인증할 수 있지만 먼저 SRS 라이선스 도구를 사용하여 정품 인증을 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="0e7d2-167">전화를 통해 정품 인증하려면 테스트 모임을 시작해야 합니다(너무 짧은 테스트 통화 아미기).</span><span class="sxs-lookup"><span data-stu-id="0e7d2-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="0e7d2-168">Office 정품 인증 마법사에서 전화 정품 인증을 선택하고 Microsoft에 전화를 걸고 긴 번호를 입력한 다음 응답을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="0e7d2-169">인증 기관</span><span class="sxs-lookup"><span data-stu-id="0e7d2-169">Certificate Authority</span></span>

<span data-ttu-id="0e7d2-170">Office Web Apps Server 2013 인증서를 발급하는 데 사용되는 인증 기관에 인증서 해지 목록 속성에 포함된 HTTP 경로가 포함되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="0e7d2-171">비즈니스용 Skype 서버를 사용하는 경우 인증서 파일(.crt)을 Skype 룸 시스템으로 가져오기</span><span class="sxs-lookup"><span data-stu-id="0e7d2-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="0e7d2-172">CA 서버의 CertEnroll 공유 또는 도메인에 가입된 PC의 신뢰할 수 있는 루트 폴더에서 쉽게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="0e7d2-173">인증서</span><span class="sxs-lookup"><span data-stu-id="0e7d2-173">Certificates</span></span>

<span data-ttu-id="0e7d2-174">인증 기관에 인증서 해지 목록에 대한 http 경로가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0e7d2-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="0e7d2-175">그렇지 않은 경우 CA를 업데이트하여 CA를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="0e7d2-176">시스템 설정 인증서 관리자에서 Skype 룸 시스템의 관리자 설정에 \> 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="0e7d2-177">내부 인증서에 대한 엔터프라이즈 루트 CA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="0e7d2-178">필요한 인증서를 얻는 한 가지 방법은 인증서를 발급한 CA를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="0e7d2-179">비즈니스용 Skype 서버의 경우 비즈니스용 Skype의 PC에서 설정 도구 전화 접속 \> \> 회의 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="0e7d2-180">그러면 내부 인증서를 발급한 CA에 의해 보안된 웹 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="0e7d2-181">브라우저 주소 표시줄에서 잠금 아이콘을 클릭하여 보안 보고서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="0e7d2-182">인증서 보기를 클릭하고 CRL 배포 지점 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="0e7d2-183">두 번째 CN 매개 변수는 CA의 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="0e7d2-184">이제 이 주소 \\ \< CA Server Name \> \CertEnroll에 대한 Windows 탐색기를 니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="0e7d2-185">두 .crl 파일과 .crt 파일을 플래시 드라이브에 복사하고 SMART 보드의 왼쪽에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="0e7d2-186">.crt 파일을 신뢰할 수 있는 방 인증 기관 폴더의 Skype 채팅방 시스템으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="0e7d2-187">Skype 채팅방 시스템에서 중간 인증 기관 폴더 아래에서 .crl 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="0e7d2-188">파일을 확인하려면 인증서 관리자의 파일 확장명 필터를 .crl로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="0e7d2-189">참고: Office Web Apps 2013 서버는 비즈니스용 Skype와 동일한 CA를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="0e7d2-190">그렇지 않은 경우 모임에서 PowerPoint를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="0e7d2-191">위에서 설명한 대로 IT에 확인하고 CA 네트워크 공유 CertEnroll에서 CRT 및 CRL 파일을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="0e7d2-192">도메인 멤버 자격은 Skype 룸 시스템을 Windows 시스템으로 취급할 수 있으며 일부 인증서 측면에 대해 Active Directory를 사용할 수 있기 때문에 일부 작업을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="0e7d2-193">그러나 수동으로 관리하는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e7d2-193">However, it's best to manually manage this.</span></span>
