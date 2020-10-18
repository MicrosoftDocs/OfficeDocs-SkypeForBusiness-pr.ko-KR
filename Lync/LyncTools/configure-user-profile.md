---
title: 사용자 프로필 구성
description: 사용자 프로필을 구성 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573094"
---
# <a name="configure-user-profile"></a><span data-ttu-id="e40f5-103">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="e40f5-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e40f5-104">_**마지막으로 수정 된 항목:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="e40f5-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="e40f5-105">Lync Server 2013 스트레스 및 성능 도구 패키지에 포함 된 도구를 사용 하 여 부하 시뮬레이션을 실행 하는 데 사용할 수 있는 테스트 사용자 계정을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="e40f5-106">Lync Server 2013 사용자 만들기 도구를 사용 하 여 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="e40f5-107">자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md)를 참조 하십시오. 사용자를 만든 후 Lync Server 2013 부하 구성 도구를 사용 하 여 사용자 프로필을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="e40f5-108">Lync Server 2013 Load 구성 도구 실행</span><span class="sxs-lookup"><span data-stu-id="e40f5-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="e40f5-109">사용자 프로필을 구성 하려면 Lync Server 2013 로드 구성 도구 (UserProfileGenerator.exe)를 실행 하 고 각 탭에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="e40f5-110">UserProfileGenerator.exe에서는 시뮬레이션을 실행 하는 데 필요한 각 클라이언트 컴퓨터에 대 한 디렉터리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="e40f5-111">또한 각 클라이언트 디렉터리는 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool.exe)의 모든 인스턴스를 시작 하는 스크립트와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e40f5-112">Userprofilegenerator.exe 공용에 지정 된 사용자 관련 값은 풀에 대 한 Lync Server 2013 사용자 만들기 도구 (UserProvisioningTool)에 지정 된 값과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="e40f5-113">다음 섹션에서 설명 하는 대로 Lync Server 2013 부하 구성 도구의 각 탭에 있는 필드를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="e40f5-114">일반 구성</span><span class="sxs-lookup"><span data-stu-id="e40f5-114">Common Configuration</span></span>

<span data-ttu-id="e40f5-115">Lync Server 2013 부하 구성 도구의 **일반 구성** 탭이 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="e40f5-116">다음 단계에 설명 된 대로 **일반 구성** 탭의 필드에 내용을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="e40f5-117">![일반 구성 탭](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "일반 구성 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="e40f5-118">사용 **가능한 컴퓨터 수**에서 LyncPerfTool.exe를 실행 하는 데 사용할 컴퓨터 수를 입력 하거나 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="e40f5-119">시뮬레이션할 모든 4500 사용자에 대해 컴퓨터 한 대를 보유 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="e40f5-120">이 숫자는 부하 수준을 줄이거나 사용 가능한 기능의 하위 집합만 사용 하는 경우에 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="e40f5-121">(부하 수준은 **일반 시나리오** 탭에서 설정 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="e40f5-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="e40f5-122">**사용자 이름의 접두사**에 사용자의 사용자 이름에 대 한 접두사를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="e40f5-123">로그인 하려면 URI (Uniform Resource Identifier)가 UserPrefix \[ 사용자 시작 인덱스입니다. (사용자 수-1) \] @User 도메인</span><span class="sxs-lookup"><span data-stu-id="e40f5-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="e40f5-124">**모든 사용자의 암호**에 사용자를 만드는 데 사용 된 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="e40f5-125">이 필드를 비워 두면 사용자 이름이 암호로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="e40f5-126">**사용자 시작 인덱스**에서 구성할 첫 번째 사용자의 인덱스를 클릭 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="e40f5-127">유형이 나 부하 수준에 따라 서로 다른 범위를 구성할 수 있지만, 구성 하려는 범위에 따라 UserProfileGenerator.exe를 한 번 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="e40f5-128">**사용자 수**에서 구성할 총 사용자 수를 클릭 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="e40f5-129">**사용자 도메인**에서 SIP URI에 사용 되는 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="e40f5-130">이는 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition 서버에 로그온 하는 각 사용자의 SIP URI를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="e40f5-131">이 도메인은 계정 도메인과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="e40f5-132">**계정 도메인**에 Active Directory 도메인 서비스 도메인 로그온을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="e40f5-133">도구가 모든 끝점/사용자에 게 로그인 할 최대 동시 끝점 수 **(인스턴스당)** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="e40f5-134">권장 속도는 \< 초당 = 2/STANDARD SKU FE입니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="e40f5-135">**액세스 프록시 또는 풀 FQDN**에 클라이언트와 연결 하려는 서버의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="e40f5-136">사용자가 외부에서 로그온 하는 경우 액세스 프록시를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="e40f5-137">내부 사용자 인 경우 해당 풀 또는 Standard Edition 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="e40f5-138">**포트**에서 사용자가 SIP에 사용 하도록 할 포트를 클릭 하거나 입력 합니다 (기본값: 5061).</span><span class="sxs-lookup"><span data-stu-id="e40f5-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="e40f5-139">외부 네트워크 서버 설정에 대해 **액세스 프록시 또는 풀 FQDN** 및 **포트**를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="e40f5-140">이러한 설정은 외부 끝점 부하 시뮬레이션에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="e40f5-141">일반 시나리오</span><span class="sxs-lookup"><span data-stu-id="e40f5-141">General Scenarios</span></span>

<span data-ttu-id="e40f5-142">Lync Server 2013 부하 구성 도구의 **일반 시나리오** 탭은 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="e40f5-143">실행 하려는 일반 시나리오 각각에 대해 부하 수준 및 매개 변수를 구성 하거나 사용 하지 않도록 설정 된 상태로 두세요.</span><span class="sxs-lookup"><span data-stu-id="e40f5-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="e40f5-144">![일반 시나리오 탭](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "일반 시나리오 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="e40f5-145">피어 투 피어 및 회의를 포함 하는 **인스턴트 메시징**에서 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e40f5-146">위치 정보 서비스를 제외한 모든 필드에 대 한 부하 수준 값은 <STRONG>사용 안 함</STRONG>, <STRONG>낮음</STRONG>, <STRONG>중간</STRONG>, <STRONG>높음</STRONG>, <STRONG>사용자 지정</STRONG>입니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="e40f5-147">낮음, 중간, 높음 또는 사용자 지정을 선택 하면 각 모달 및 클라이언트에 대 한 구성이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="e40f5-148">높은 경우 서버에 대해 지원 되는 최대 부하가 생성 되 고, 중간 크기는 부하의 60%에 해당 하며, 낮은 부하의 30%에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="e40f5-149">오디오 **회의 에서만**가능 하며 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="e40f5-150">피어 투 피어 통화에 대해서는이 항목의 뒷부분에 나오는 Voice 시나리오 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="e40f5-151">멀티뷰를 사용 하도록 설정 하려면 해당 형식에 대 한 **고급** 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="e40f5-152">**응용 프로그램 공유**에서 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="e40f5-153">데이터 회의를 포함 하는 **데이터 공동 작업**에서 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="e40f5-154">**메일 그룹 확장**에서 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="e40f5-155">또한 **고급** 단추를 클릭 한 다음 Lync Server 사용자 만들기 도구 (UserProvisioningTool.exe)의 **메일 그룹** 탭에서 구성한 값과 동일한 필드를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="e40f5-156">이러한 필드에 대 한 자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e40f5-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="e40f5-157">주소록 **웹 쿼리**(주소록이 파일을 다운로드 하는 것이 아님)에서 로드 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="e40f5-158">주소록 다운로드를 사용 하도록 설정 하려면 해당 하는 **고급** 단추를 클릭 한 다음 **EnableABSDownload** 를 true로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="e40f5-159">**응답 그룹 서비스**에서 부하 수준에 적절 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="e40f5-160">또한 해당 하는 **고급** 단추를 클릭 한 다음 응답 그룹 서비스 에이전트를 프로 비전 할 때 이미 만든 응답 그룹의 uri를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="e40f5-161">하나 이상의 응답 그룹을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-161">You must specify at least one response group.</span></span> <span data-ttu-id="e40f5-162">세미콜론을 사용 하 여 여러 응답 그룹을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="e40f5-163">실제 값으로 RGSUriSuffixStartIndex 및 RGSUriSuffixEndIndex를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="e40f5-164">**위치 정보 서비스**에서 부하 수준에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="e40f5-165">위치 정보 서비스에 대 한 부하 수준을 **사용** 하거나 **사용 하지 않도록**설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e40f5-166">각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있으며, 시나리오 변형을 가능 하 게 하는 확인란 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="e40f5-167"><STRONG>Ad-hoc은</STRONG> 한 시간 동안 생성 되는 회의 시뮬레이션을 생성 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="e40f5-168"><STRONG>큰</STRONG> 컨퍼런스는 대규모 회의 시나리오가 시뮬레이션 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="e40f5-169"><STRONG>외부</STRONG> 를 통해 외부 사용자를 시뮬레이션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="e40f5-170">이러한 단추 및 확인란을 사용 하면 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정할 수 있도록 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="e40f5-171"><STRONG>일반 시나리오</STRONG> 탭 (위치 정보 서비스 제외)의 각 시나리오에서는 부하 수준 값이 <STRONG>Custom</STRONG>인 경우 <STRONG>고급</STRONG> 대화 상자의 해당 필드를 사용 하 여 대화 속도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="e40f5-172">필드 이름은 시나리오에 따라 다르지만 필드 설명에는 "참고:이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 경우에만 사용 됩니다."</span><span class="sxs-lookup"><span data-stu-id="e40f5-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="e40f5-173">일반적으로 <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, <STRONG>Low</STRONG> 값은 모든 시나리오의 잔고에 해당 하는 사용자 모델을 기준으로 하 여 각 줄에 대 한 대화 속도를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="e40f5-174">예상 사용량의 차이로 인해 모달 형식으로 로드 수준을 변경 해야 하는 경우에는 <STRONG>사용자 지정</STRONG> 대화 비율을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="e40f5-175">음성 시나리오</span><span class="sxs-lookup"><span data-stu-id="e40f5-175">Voice Scenarios</span></span>

<span data-ttu-id="e40f5-176">Lync Server 2013 부하 구성 도구의 **음성 시나리오** 탭이 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="e40f5-177">음성 **시나리오** 탭을 사용 하 여 모든 음성 관련 시나리오를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="e40f5-178">![음성 시나리오 탭](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "음성 시나리오 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="e40f5-179">**VoIP**에서 **고급** 단추를 클릭 한 다음 **PhoneAreaCode** 및 **locationprofile** (다이얼 플랜) 필드에 대 한 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="e40f5-180">또한 **부하 수준**에 대 한 값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="e40f5-181">**VoIP** 및 **Uc/PSTN 게이트웨이에** 대 한 로드 수준이 사용 하도록 설정 된 경우 외부 통화를 시뮬레이트하기 위한 공중 전화망 (uc) 구성 파일에 대 한 공공 전화망 (PSTN)이 항상 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="e40f5-182">**UC/PSTN 게이트웨이에서**부하 수준 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="e40f5-183">**사용 안 함**이외의 부하 수준을 선택한 경우에는 중재 서버 및 PSTN에서 **추가** 단추를 클릭 하 여 **pstn 지역 번호** 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="e40f5-184">해당 지역 번호에 대해 경로가 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e40f5-185">Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 음성 경로 구성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="e40f5-186">**회의 전화 교환**에서 부하 수준에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="e40f5-187">**사용 하지 않도록 설정**된 부하를 제외 하 고 로드 수준을 선택 하면 **전화 번호** 필드가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="e40f5-188">사용할 자동 전화 교환의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="e40f5-189">또한 **고급** 단추를 클릭 한 다음 **locationprofile** 필드에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="e40f5-190">**통화 대기 서비스**에서 **부하 수준**에 적합 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="e40f5-191">**중재 서버 및 PSTN**에서 사용 하려는 각 중재 서버에 대해 별도의 PSTN 시뮬레이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="e40f5-192">시뮬레이터로 사용할 클라이언트를 결정 한 후에는 사용자가 구성한 PSTN 시뮬레이터 포트에서 해당 컴퓨터로 통화를 라우팅하도록 중재 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="e40f5-193">**추가** 를 클릭 하 여 중재 서버의 값을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e40f5-194">각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="e40f5-195">이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="e40f5-196"><STRONG>음성 시나리오</STRONG> 탭의 각 시나리오에서 <STRONG>부하 수준</STRONG> 값이 <STRONG>Custom</STRONG>이면 <STRONG>Advanced (고급</STRONG> ) 대화 상자에서 해당 하는 필드를 사용 하 여 대화 속도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="e40f5-197">필드 이름은 시나리오에 따라 다르지만 필드 설명에는 "참고:이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 경우에만 사용 됩니다."</span><span class="sxs-lookup"><span data-stu-id="e40f5-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="e40f5-198">지원함</span><span class="sxs-lookup"><span data-stu-id="e40f5-198">Reach</span></span>

<span data-ttu-id="e40f5-199">Front-End 서버에 설치 된 통합 커뮤니케이션 웹 API (WA) 서버를 통해 회의 시나리오를 지 원하는 Lync Server 2013의 새로운 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="e40f5-200">Lync Server 2013 부하 구성 도구의 **Reach** 탭은 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="e40f5-201">**Reach 탭을** 사용 하 여 모든 관련 시나리오를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="e40f5-202">![연결 탭](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "연결 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="e40f5-203">**일반 연결 설정**옆에 있는 **고급** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="e40f5-204">**UcwaTargetServerUrl** 필드를 디렉터 풀 vip (가상 IP) 또는 프런트 엔드 풀 vip로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="e40f5-205">**응용 프로그램 공유**, **데이터 공동 작업**및 **IM**에서 **부하 수준**에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e40f5-206">각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="e40f5-207">이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="e40f5-208">각 시나리오에서 <STRONG>로드 수준이</STRONG> <STRONG>Custom</STRONG>인 경우에는 <STRONG>ConversationsPerHour</STRONG> 필드에 지정 된 값이 기본값 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="e40f5-209">**이동성 탭을** 사용 하 여 모든 모바일 관련 시나리오를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="e40f5-210">![모바일 기능 탭](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "모바일 기능 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="e40f5-211">**Mobility (DATWA)** 옆에 있는 **고급** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="e40f5-212">**UcwaTargetServerUrl** 필드를 디렉터 풀 vip (가상 IP) 또는 프런트 엔드 풀 vip로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="e40f5-213">**현재 상태 및 P2P 인스턴트 메시징 \\ 오디오**에서 **부하 수준** 에 대 한 적절 한 값을 선택 하 여 이동성 시나리오 시뮬레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e40f5-214">각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="e40f5-215">이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="e40f5-216">각 시나리오에서 <STRONG>로드 수준이</STRONG> <STRONG>Custom</STRONG>인 경우에는 <STRONG>ConversationsPerHour</STRONG> 필드에 지정 된 값이 기본값 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="e40f5-217">요약</span><span class="sxs-lookup"><span data-stu-id="e40f5-217">Summary</span></span>

<span data-ttu-id="e40f5-218">Lync Server 2013 Load 구성 도구의 **요약** 탭은 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="e40f5-219">![요약 탭](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "요약 탭")</span><span class="sxs-lookup"><span data-stu-id="e40f5-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="e40f5-220">**요약** 탭에는 각 시나리오에 사용할 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="e40f5-221">사용자 **지정 사용자 범위 생성 사용** 확인란을 선택한 후 사용자 지정 하려는 **사용자 범위가** 있는 테이블에서 시나리오를 두 번 클릭 하는 방법으로, 직접 번호 범위를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="e40f5-222">확인 (RunClient.bat) 시작 시 로그인 지연을 추가 하 여 생성 된 배치 파일에서 로그인 속도에 해당 하는 지연을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="e40f5-223">이 기능은 많은 사용자에 게 로그인 할 때 서버 오버 로드를 방지 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="e40f5-224">**파일 생성**을 클릭 하 고 구성을 생성할 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="e40f5-225">파일을 성공적으로 만든 후에는 다음 그림과 같은 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e40f5-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="e40f5-226">![파일이 생성 되었음을 승인 합니다.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "파일이 생성 되었음을 승인 합니다.")</span><span class="sxs-lookup"><span data-stu-id="e40f5-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e40f5-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e40f5-227">See Also</span></span>


[<span data-ttu-id="e40f5-228">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="e40f5-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
