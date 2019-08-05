---
title: Skype 실 시스템 관리 효율성 및 도구
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Skype 대화방 시스템용 관리 도구에 대해 자세히 알아보려면이 항목을 참조 하세요.
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196388"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="49d1f-103">Skype 실 시스템 관리 효율성 및 도구</span><span class="sxs-lookup"><span data-stu-id="49d1f-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="49d1f-104">Skype 대화방 시스템용 관리 도구에 대해 자세히 알아보려면이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="49d1f-105">관리 포털</span><span class="sxs-lookup"><span data-stu-id="49d1f-105">Administrative Portal</span></span>

<span data-ttu-id="49d1f-106">비즈니스용 Skype Server 온-프레미스 배포의 경우 Skype 대화방 시스템 관리 포털을 사용 하 여 조직 내에서 Skype 채팅방 시스템 배포를 적극적으로 관리 하 고 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="49d1f-107">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="49d1f-108">비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포</span><span class="sxs-lookup"><span data-stu-id="49d1f-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="49d1f-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="49d1f-109">System Center Operations Manager</span></span>

<span data-ttu-id="49d1f-110">Skype 채팅방 시스템 [관리 팩](https://www.microsoft.com/download/details.aspx?id=42320) 을 다운로드 하 고 scom server에 설치 하 여 시스템 센터 운영 관리자 (scom)를 통해이를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="49d1f-111">SCOM를 사용 하 여 알림을 설정 하 고, Skype 대화방 시스템의 상태를 모니터링 하 고, 가동 시간 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="49d1f-112">Skype 채팅방 시스템에는 SCOM server를 가리키도록 구성할 수 있는 사전 설치 된 모니터링 에이전트가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="49d1f-113">Skype 대화방 시스템에서 모니터링 에이전트를 구성 하는 방법을 알아보려면 Skype 채팅방 시스템 제조업체에서 제공 하는 설치 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="49d1f-114">Exchange 검사 목록</span><span class="sxs-lookup"><span data-stu-id="49d1f-114">Exchange Checklist</span></span>

- <span data-ttu-id="49d1f-115">자동 검색을 설정 하 고 내부 DNS A/CNAME 레코드를 autodiscover.domain.com에 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="49d1f-116">Ping 자동 검색 (예: Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="49d1f-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="49d1f-117">Microsoft 연결 분석기 도구를 사용 하 여 자동 검색 서비스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="49d1f-118">첫 번째 테스트 인 "Office Outlook을 사용 하 여 로그온 할 수 없음"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="49d1f-119">회의실에 이미 리소스 사서함이 있는 경우 Skype 대화방 시스템 (페이지 하단에 있는 예제 스크립트)에 대해이 계정을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="49d1f-120">비즈니스용 Skype 검사 목록</span><span class="sxs-lookup"><span data-stu-id="49d1f-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="49d1f-121">다음 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="49d1f-122">비즈니스용 Skype 모범 사례 분석기</span><span class="sxs-lookup"><span data-stu-id="49d1f-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="49d1f-123">비즈니스용 Skype 상태 분석 도구 (Excel)</span><span class="sxs-lookup"><span data-stu-id="49d1f-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="49d1f-124">비즈니스용 Skype 연결 분석기 32 비트 또는 64 비트</span><span class="sxs-lookup"><span data-stu-id="49d1f-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="49d1f-125">[Office 365에 대 한 유용한 새로운 문제 해결 및 분석 도구](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="49d1f-126">비즈니스용 Skype 풀 및 Office Web Apps 서버가 있는지 확인 하 고 비즈니스용 Skype 클라이언트를 사용 하 여 PowerPoint 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="49d1f-127">회의실에 이미 리소스 사서함이 있는 경우 비즈니스용 Skype에 대해이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="49d1f-128">필요한 경우 회의실 시스템에 대 한 번호 (전화 번호)를 요청 하 고 Active Directory 도구에서 일반 전화 필드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="49d1f-129">사설망</span><span class="sxs-lookup"><span data-stu-id="49d1f-129">Network</span></span>

- <span data-ttu-id="49d1f-130">Skype 채팅방 시스템에 대 한 유선 네트워크 연결을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="49d1f-131">비즈니스용 Skype에 대 한 네트워크 계획 가이드를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="49d1f-132">비즈니스용 Skype 파트너 로부터 비즈니스용 Skype 네트워크 평가를 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="49d1f-133">비즈니스용 Skype 상태 분석 도구 (Excel)에서 캡처한 성능 데이터를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="49d1f-134">네트워크 분석 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="49d1f-135">사전 호출 진단 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="49d1f-136">Skype 실 시스템 보안</span><span class="sxs-lookup"><span data-stu-id="49d1f-136">Skype Room System Security</span></span>

<span data-ttu-id="49d1f-137">Skype 실 시스템은 비즈니스용 Skype 보안 모델, 권한 관리, SCOM 등의 관리 도구를 사용 하 여 Windows 배포에 완벽 하 게 통합할 수 있는 임베디드 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="49d1f-138">기능에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-138">Features include:</span></span>
  
- <span data-ttu-id="49d1f-139">사용자 모드에서 디스크 쓰기를 방지 하는 쓰기 필터</span><span class="sxs-lookup"><span data-stu-id="49d1f-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="49d1f-140">앱 락커를 통해 권한이 없는 앱이 실행 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-140">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="49d1f-141">사용자 모드에서 모든 USB 포트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-141">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="49d1f-142">Skype 채팅방 시스템 하드웨어에는 표준 앱 또는 뷰어가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="49d1f-143">모든 콘텐츠는 HTTP 또는 RDP 프로토콜을 통해 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="49d1f-144">기기 PC는 Windows Embedded 표준 7 운영 체제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-144">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="49d1f-145">장치를 포함 하 여 모든 하드웨어는 OEM 파트너가 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-145">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="49d1f-146">AD DS (Active Directory 도메인 서비스)에 대 한 선택적 도메인 가입으로 로컬 보안 계정 관리 및 제어권을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="49d1f-147">비즈니스용 Skype 관리 센터를 사용 하 여 로컬 관리자 계정을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="49d1f-148">Skype 채팅방 시스템은 표준 Microsoft 업데이트 프로세스를 통해 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="49d1f-149">Skype 채팅방 시스템은 비즈니스용 Skype로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="49d1f-150">비즈니스용 Skype는 모든 통신 모드에 대 한 종단 간 암호화 및 권한 부여를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="49d1f-151">Skype 실 시스템은 비즈니스용 Skype 보안 및 규정 준수 표준을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="49d1f-152">자세한 내용은 비즈니스용 [Skype 서버의 보안 계획](../../plan-your-deployment/security/security.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="49d1f-153">동의</span><span class="sxs-lookup"><span data-stu-id="49d1f-153">License</span></span>

<span data-ttu-id="49d1f-154">소프트웨어를 정품 인증 하기 위해 KMS를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="49d1f-155">그렇다면 비즈니스용 Skype 클라이언트 KMS 키를 확인 하거나 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="49d1f-156">KMS를 사용 하지 않는 경우 비즈니스용 Skype 클라이언트 MAK에 대 한 볼륨 라이선스 키를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="49d1f-157">라이선스 키</span><span class="sxs-lookup"><span data-stu-id="49d1f-157">License keys</span></span>

<span data-ttu-id="49d1f-158">Skype 채팅방 시스템은 백그라운드에서 비즈니스용 Skype 데스크톱 클라이언트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="49d1f-159">Skype 채팅방 시스템은 도메인 구성원 인 경우, KMS를 검색 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="49d1f-160">(볼륨 라이선스 KMS 키가 있는 경우 자동으로 활성화 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="49d1f-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="49d1f-161">또한 볼륨 라이선스는 xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx-xxxxx를 표시 하면서 입력 하는 MAK를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="49d1f-162">(KMS가 아닌 MAK를 사용 하 여 정품 인증을 받으려면 인터넷에 액세스 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="49d1f-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="49d1f-163">자세한 내용은 Office 2013의 볼륨 정품 인증을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d1f-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="49d1f-164">MAK 키를 입력 하려면 OEM 설정 \> SRS 라이선스 도구로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="49d1f-165">상태 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-165">Click Check Status.</span></span> <span data-ttu-id="49d1f-166">상태가 "제품이 활성화 되지 않음" 이라고 표시 되 면 키를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="49d1f-167">정품 인증 하는 동안 "" 소프트웨어 라이선스 서비스에서 제품 키가 유효 하지 않다고 보고 했습니다. "라는 오류가 표시 되는 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="49d1f-168">키를 올바르게 입력 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="49d1f-169">다른 키가 아닌 비즈니스용 Skype MAK 키를 입력 하셨습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="49d1f-170">시스템에서 인터넷에 접속 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="49d1f-171">전화기를 통해 정품 인증을 받을 수 있지만 먼저 SRS 라이선스 도구를 사용 하 여 정품 인증을 시도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="49d1f-172">전화기를 통해 정품 인증을 받으려면 테스트 모임이 아닌 것으로 테스트 통화가 시작 되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="49d1f-173">Office 인증 마법사에서 전화 정품 인증을 선택 하 고, Microsoft에 전화를 걸어, 긴 숫자를 입력 하 고, 응답을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="49d1f-174">인증 기관</span><span class="sxs-lookup"><span data-stu-id="49d1f-174">Certificate Authority</span></span>

<span data-ttu-id="49d1f-175">Office Web Apps 서버 2013 인증서에 발급 하는 데 사용 되는 인증 기관 확인 인증서 해지 목록 속성에 HTTP 경로가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="49d1f-176">비즈니스용 Skype 서버를 사용 하는 경우 인증서 파일 (.crt)을 Skype 대화방 시스템으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="49d1f-177">CA 서버의 CertEnroll 공유 또는 도메인에 연결 된 PC의 신뢰할 수 있는 루트 폴더에서 쉽게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="49d1f-178">인증</span><span class="sxs-lookup"><span data-stu-id="49d1f-178">Certificates</span></span>

<span data-ttu-id="49d1f-179">인증 기관에 인증서 해지 목록에 대 한 http 경로가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-179">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="49d1f-180">그렇지 않은 경우 CA를 포함 하도록 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-180">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="49d1f-181">시스템 설정 \> 인증서 관리자에서 Skype 대화방 시스템의 관리자 설정에 인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="49d1f-182">내부 인증서에 대 한 엔터프라이즈 루트 CA가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="49d1f-183">필요한 인증서를 획득 하는 한 가지 방법은 인증서를 발급 한 CA를 검색 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="49d1f-184">비즈니스용 skype Server의 경우 비즈니스용 Skype의 PC에서 설정 \> 도구 \> 전화 접속 회의 설정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="49d1f-185">이렇게 하면 내부 인증서를 발급 한 CA에서 보호 하는 웹 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="49d1f-186">브라우저 주소 표시줄에서 잠금 아이콘을 클릭 하 여 보안 보고서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="49d1f-187">인증서 보기를 클릭 하 고 CRL 배포 지점의 속성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="49d1f-188">두 번째 CN 매개 변수는 CA의 서버 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="49d1f-189">이제 해당 주소 \\ \< 에 대 한 Windows 탐색기를 엽니다 \>. CA 서버 이름 \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="49d1f-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="49d1f-190">두 개의 crl 파일과 .crt 파일을 플래시 드라이브에 복사 하 고 스마트 보드의 왼쪽에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="49d1f-191">해당 .crt 파일을 신뢰할 수 있는 룸 인증 기관 폴더 아래의 Skype 채팅방 시스템으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="49d1f-192">중개 인증 기관 폴더 아래에 있는 Skype 대화방 시스템에서. s e s 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="49d1f-193">(파일을 보려면 인증서 관리자의 파일 확장명 필터를. crl로 변경 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="49d1f-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="49d1f-194">참고: Office Web Apps 2013 서버는 비즈니스용 Skype와 같은 CA를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="49d1f-195">모임에서 PowerPoint를 공유 하지 못하는 경우</span><span class="sxs-lookup"><span data-stu-id="49d1f-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="49d1f-196">이를 확인 하 고 위에 설명 된 대로 CA 네트워크 공유 CertEnroll에서 CRT 및 CRL 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="49d1f-197">도메인 구성원 자격은 Skype 채팅방 시스템을 Windows 시스템으로 취급할 수 있고 일부 인증서 측면에 대해 Active Directory를 사용할 수 있기 때문에 일부 작업을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="49d1f-198">그러나이를 수동으로 관리 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="49d1f-198">However, it's best to manually manage this.</span></span>
  

