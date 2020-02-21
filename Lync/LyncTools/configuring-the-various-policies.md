---
title: 다양 한 정책 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98cb69c1c83b794292c31c43ba9778e8efb8cb99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="9f4d0-102">다양 한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f4d0-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9f4d0-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="9f4d0-104">다양 한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-104">Configuring the Various Policies</span></span>

<span data-ttu-id="9f4d0-105">Lync server 2013 스트레스 및 성능 도구를 실행 하기 전에 Lync Server 2013 토폴로지에서 구성할 수 있는 다양 한 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="9f4d0-106">보관 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="9f4d0-107">예제 스크립트 ArchivingPolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="9f4d0-108">이 스크립트는 토폴로지에 보관 서버를 배포한 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="9f4d0-109">자세한 내용은 lync server 2013 설명서 및 [Lync server 2013의 보관 및 모니터링 cmdlet](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="9f4d0-110">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="9f4d0-111">예제 스크립트 Microsoft.rtc.management.writableconfig.policy.meeting.meetingpolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="9f4d0-112">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 웹 회의 cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="9f4d0-113">연락처 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="9f4d0-114">예: 연락처 이름 Spolicy.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="9f4d0-115">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 IM 및 현재 상태 cmdlet](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="9f4d0-116">페더레이션 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="9f4d0-117">예제 FederationPolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="9f4d0-118">자세한 내용은 lync server 2013 설명서 및 lync server 2013 및 [페더레이션 및 외부 액세스 2013 cmdlet](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))의 [Edge server cmdlet](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) 에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="9f4d0-119">통화 허용 제어 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="9f4d0-120">예제 BandwidthPolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="9f4d0-121">자세한 내용은 lync server 2013 설명서에서 lync server [2013의 통화 허용 제어 개요](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) 및 [lync Server 2013의 통화 허용 제어 cmdlet](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="9f4d0-122">음성 라우팅 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="9f4d0-123">예제 RoutingRules를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="9f4d0-124">음성 라우팅 규칙을 구성할 때는 사용자를 만들 때 및 LyncPerfTool 구성 (특히 PSTN-UC 및 UC PSTN 용)을 사용할 때 전화 컨텍스트 (예:/Location,/Dinename)와 내부/외부 지역 코드를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="9f4d0-125">예를 들어 Userprofilegenerator.exe 공용의 다음 그림에서 LocationProfile 값에 대해 RoutingRules의 **새 CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="9f4d0-126">![샘플 음성 라우팅 규칙입니다.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "샘플 음성 라우팅 규칙입니다.")</span><span class="sxs-lookup"><span data-stu-id="9f4d0-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="9f4d0-127">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 Enterprise Voice cmdlet](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="9f4d0-128">회의 전화 교환 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="9f4d0-129">예제 ConferenceAutoAttendantConfiguration를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="9f4d0-130">구성 생성을 위해 LyncPerf 도구 구성 도구에 입력할 수 있도록 ConferencingAutoAttendant 전화 번호 (기본적으로 1121111111)를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="9f4d0-131">![회의 전화 교환 응용 프로그램 구성](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "회의 전화 교환 응용 프로그램 구성")</span><span class="sxs-lookup"><span data-stu-id="9f4d0-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="9f4d0-132">자세한 내용은 lync server 2013 설명서 및 lync server 2013 및 [전화 접속 회의 2013 cmdlet](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))의 [웹 회의 cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) 에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="9f4d0-133">Lync Server 통화 대기 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="9f4d0-134">통화 대기는 기본적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-134">Call Park is disabled by default.</span></span> <span data-ttu-id="9f4d0-135">예제 CallParkConfiguration를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="9f4d0-136">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 통화 대기 응용 프로그램 cmdlet](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="9f4d0-137">긴급 통화 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="9f4d0-138">긴급 통화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="9f4d0-139">비상 전화를 위해 음성 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="9f4d0-140">이 음성 경로를 설정 하는 예제를 보려면 "Route E911 to PSTN" 설명에 나오는 RoutingRules 스크립트를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9f4d0-141">RoutingRules의 예제 명령에 911가 아닌 119 수를 포함 하는 숫자 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="9f4d0-142">부하 테스트 중에 로컬 응급 운영자에 게 실수로 전화를 걸 수 없도록 911 (또는 실제 로컬 비상 번호)를 사용 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="9f4d0-143">이 구성은 시뮬레이션 목적 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="9f4d0-144">다음 그림에 표시 된 것 처럼 UserProvisioningTool의 **LIS** 탭에 있는 값을 채워서 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9f4d0-145">![위치 정보 서비스 구성](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "위치 정보 서비스 구성")</span><span class="sxs-lookup"><span data-stu-id="9f4d0-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="9f4d0-146">**LIS 구성 파일 생성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="9f4d0-147">포트, 서브넷, 스위치 및 Wap (무선 액세스 지점)에 대 한 CSV 파일 및 Lync Server 2013 스트레스 및 성능 도구인 XML 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="9f4d0-148">이 CSV 파일은 LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 동일한 폴더에서 입력으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="9f4d0-149">생성 된 Locations0 파일을 Lync Server 2013 스트레스 및 성능 도구 실행 파일 (여기서는 위치 프로필 (다이얼 플랜) 시나리오를 실행 하는 LyncPerfTool)과 동일한 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="9f4d0-150">사용자 만들기, 설정, 구성 및 해제</span><span class="sxs-lookup"><span data-stu-id="9f4d0-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="9f4d0-151">다음 스크립트를 실행 하기 전에 모든 사용자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="9f4d0-152">사용자 만들기 [및 연락처 만들기](create-users-and-contacts.md) 의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="9f4d0-153">자세한 내용은 [css\user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-Csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))및 [Disable-Csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlet에 대 한 Lync Server 2013 cmdlet 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="9f4d0-154">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="9f4d0-154">Configuring Response Group application</span></span>

<span data-ttu-id="9f4d0-155">ResponseGroupConfiguration. p 예를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="9f4d0-156">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 응답 그룹 응용 프로그램 cmdlet](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오. 응답 그룹 응용 프로그램 구성을 검토 하려면 다음 그림 `https://<poolfqdn>/RgsConfig/`에 표시 된 것 처럼를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f4d0-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="9f4d0-157">![응답 그룹 구성 도구](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "응답 그룹 구성 도구")</span><span class="sxs-lookup"><span data-stu-id="9f4d0-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

