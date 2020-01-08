---
title: 다양 한 정책 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="afd00-102">다양 한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd00-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="afd00-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="afd00-104">다양 한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-104">Configuring the Various Policies</span></span>

<span data-ttu-id="afd00-105">Lync server 2013 스트레스 및 성능 도구를 실행 하기 전에 Lync Server 2013 토폴로지에서 구성할 수 있는 다양 한 정책에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="afd00-106">보관 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="afd00-107">예제 스크립트 ArchivingPolicy을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="afd00-108">이 스크립트는 토폴로지에 보관 서버가 배포 된 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="afd00-109">자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013에서 cmdlet을 기록 하 고 모니터링](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))하는 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="afd00-110">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="afd00-111">예제 스크립트 MeetingPolicy을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="afd00-112">자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 웹 회의 cmdlet](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="afd00-113">연락처 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="afd00-114">예: 연락처 Spolicy. ps1을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="afd00-115">자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 IM 및 현재 상태 cmdlet](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="afd00-116">페더레이션 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="afd00-117">예제 FederationPolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="afd00-118">자세한 내용은 lync Server 2013 설명서 및 lync server [2013의 Edge server cmdlet](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) 에 대 한 cmdlet 도움말 및 [lync Server 2013의 페더레이션 및 외부 액세스 cmdlet](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="afd00-119">통화 허용 제어 정책 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="afd00-120">예제 BandwidthPolicy를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="afd00-121">자세한 내용은 lync server 2013에서 lync server [2013의 통화 허용 제어](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) 에 대 한 개요 및 lync [Server 2013의 통화 허용 제어 cmdlet](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="afd00-122">음성 라우팅 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="afd00-123">예제 RoutingRules를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="afd00-124">음성 라우팅 규칙을 구성할 때 전화 컨텍스트 (즉,/위치 프로필 또는/SimpleName) 및 내부/외부 지역 코드를 기록 하 여 사용자를 만들 때, 그리고 LyncPerfTool 구성 중에 (특히 PSTN-UC 및 UC-PSTN 용)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="afd00-125">예를 들어 RoutingRules의 **새-CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수는 다음 UserProfileGenerator 그림의 locationprofile 값에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="afd00-126">![샘플 음성 라우팅 규칙입니다.] (images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "샘플 음성 라우팅 규칙입니다.")</span><span class="sxs-lookup"><span data-stu-id="afd00-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="afd00-127">자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 엔터프라이즈 음성 cmdlet](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="afd00-128">회의 수행자 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="afd00-129">예제 ConferenceAutoAttendantConfiguration를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="afd00-130">구성 생성을 위해 LConferencingAutoAttendant Cperf Tool 구성 도구에 입력할 수 있도록 기본적으로 1121111111 등의 전화 번호를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="afd00-131">회의(images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "수행자 응용") ![프로그램 구성]</span><span class="sxs-lookup"><span data-stu-id="afd00-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="afd00-132">자세한 내용은 lync Server 2013 설명서와 lync server [2013의 웹 회의](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) cmdlet에 대 한 cmdlet 도움말 및 [lync Server 2013의 전화 접속 회의 cmdlet](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="afd00-133">Lync Server 통화 공원 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="afd00-134">통화 공원는 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-134">Call Park is disabled by default.</span></span> <span data-ttu-id="afd00-135">예제 CallParkConfiguration를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="afd00-136">자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 통화 공원 응용 프로그램 cmdlet](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="afd00-137">비상 전화 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="afd00-138">긴급 통화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="afd00-139">비상 전화에 대 한 음성 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="afd00-140">이 음성 경로 설정에 대 한 예는 "PSTN으로 E911 라우팅"의 "RoutingRules 스크립트"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="afd00-141">RoutingRules의 예제 명령에 911이 아닌 숫자 119를 포함 하는 숫자 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="afd00-142">부하 테스트 중에 로컬 비상 운영자에 게 실수로 전화를 하지 않도록 911 (또는 실제 로컬 비상 번호)를 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="afd00-143">이 구성은 시뮬레이션 용도로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="afd00-144">다음 그림과 같이 UserProvisioningTool의 **LIS** 탭에 있는 값을 입력 하 여 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="afd00-145">![위치 정보 서비스 구성] (images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "위치 정보 서비스 구성")</span><span class="sxs-lookup"><span data-stu-id="afd00-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="afd00-146">**LIS 구성 파일 생성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="afd00-147">포트, 서브넷, 스위치 및 WAPs (무선 액세스 지점)의 CSV 파일과 Lync Server 2013 스트레스 및 성능 도구의 XML 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="afd00-148">CSV 파일은 LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 입력 (동일한 폴더에서)으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="afd00-149">생성 된 Locations0 파일을 Lync Server 2013 스트레스 및 성능 도구 실행 파일과 동일한 폴더로 이동 합니다 (이 경우 위치 프로필 (다이얼 플랜) 시나리오를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="afd00-150">사용자 만들기, 설정, 구성, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="afd00-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="afd00-151">다음 스크립트를 실행 하기 전에 모든 사용자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="afd00-152">사용자 [및 연락처 만들기](create-users-and-contacts.md) 의 지침에 따라 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="afd00-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="afd00-153">자세한 내용은 온 [-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set Csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))및 [Disable-Csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlet에 대 한 Lync Server 2013 cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="afd00-154">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="afd00-154">Configuring Response Group application</span></span>

<span data-ttu-id="afd00-155">예: ResponseGroupConfiguration. ps1을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="afd00-156">자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 응답 그룹 응용 프로그램 cmdlet](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요. 응답 그룹 응용 프로그램 구성을 검토 하려면 다음 그림과 `https://<poolfqdn>/RgsConfig/`같이을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd00-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="afd00-157">![응답 그룹 구성 도구입니다.] (images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "응답 그룹 구성 도구입니다.")</span><span class="sxs-lookup"><span data-stu-id="afd00-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

