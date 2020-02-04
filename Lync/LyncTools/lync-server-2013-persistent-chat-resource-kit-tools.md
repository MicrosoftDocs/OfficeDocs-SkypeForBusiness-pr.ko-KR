---
title: Lync Server 2013 영구 채팅 리소스 키트 도구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a827892dac61ff88d0527eafb7d94948afa21885
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="c1c13-102">Lync Server 2013 영구 채팅 리소스 키트 도구</span><span class="sxs-lookup"><span data-stu-id="c1c13-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1c13-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c1c13-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c1c13-104">Lync Server 2013 영구 채팅 리소스 키트 도구는 Lync Server 2013 영구 채팅 서버를 배포 하 고 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="c1c13-105">이 항목에서는 설치 지침 외에 각 도구의 목적과 사용 예제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="c1c13-106">리소스 키트 도구 설치</span><span class="sxs-lookup"><span data-stu-id="c1c13-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="c1c13-107">Lync Server 2013, 리소스 키트 도구를 설치 하려면 **PersistentChatReskit**를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="c1c13-108">간단한 설치를 수행 하려면 **PersistentChatReskit** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="c1c13-109">.Msi는 다음 경로에 모든 도구를 설치 합니다. \\ **프로그램\\ 파일 Microsoft Lync server 2013\\영구 채팅 서버 리소스 키트**.</span><span class="sxs-lookup"><span data-stu-id="c1c13-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="c1c13-110">자체 포함 된 실행 파일의 도구는이 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="c1c13-111">파일이 있는 도구는 고유한 하위 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1c13-112">Lync Server 2013, Resource Kit 도구를 설치한 후 <STRONG>PsExec</STRONG> 를 설치 하 고 <STRONG>PsExec</STRONG> 를 \\ <STRONG>프로그램 파일 \ Microsoft Lync server 2013 \ 영구 채팅 서버 리소스 Kit\ChatStressTool</STRONG>경로에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="c1c13-113"><STRONG>PsExec</STRONG>을 복사 하지 않으면 영구 채팅 스트레스 도구에서 오류 예외가 발생 하 고 제대로 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="c1c13-114">도구를 실행 하기 전에이 선행 조건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="c1c13-115"><STRONG>PsExec</STRONG>를 설치 하는 방법에 대 한 <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c13-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="c1c13-116">지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="c1c13-116">Supported Environments</span></span>

<span data-ttu-id="c1c13-117">최적의 성능을 위해서는 lync Server 2013, 리소스 키트 도구를 동일한 환경에 설치 하 고 Lync Server 2013에 필요한 사양과 동일 하 게 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="c1c13-118">리소스 키트 도구 개요</span><span class="sxs-lookup"><span data-stu-id="c1c13-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="c1c13-119">Lync Server 2013 영구 채팅 리소스 키트에 제공 되는 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="c1c13-120">다음 섹션에서는 요구 사항과 예제 사용을 포함 하 여 각 도구에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="c1c13-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="c1c13-121">AffCheck</span></span>

  - <span data-ttu-id="c1c13-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="c1c13-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="c1c13-123">가을 스트레스 도구</span><span class="sxs-lookup"><span data-stu-id="c1c13-123">ChatStress Tool</span></span>

  - <span data-ttu-id="c1c13-124">로이 업그레이드 확인 프로그램</span><span class="sxs-lookup"><span data-stu-id="c1c13-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="c1c13-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="c1c13-125">ChatUsageReport</span></span>

  - <span data-ttu-id="c1c13-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="c1c13-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="c1c13-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="c1c13-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-128">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-128">Description</span></span>

<span data-ttu-id="c1c13-129">AffCheck 도구는 영구 채팅 백 엔드 데이터베이스 사용자 및 그룹에 연결 된 레코드가 Active Directory 도메인 서비스와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-130">Requirements</span></span>

<span data-ttu-id="c1c13-131">이 도구는 도메인에 가입 된 컴퓨터에서 PersistentChatResKit 설치 관리자와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="c1c13-132">도구가 실행 되는 사용자 계정에는 영구 채팅 백 엔드 데이터베이스 및 Active Directory 도메인 서비스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-133">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-133">Usage</span></span>

<span data-ttu-id="c1c13-134">Config 파일의 지침에 따라 AffCheck 파일을 구성 하 고 명령줄 매개 변수 없이 AffCheck 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="c1c13-135">다음은 기본 AffCheck의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="c1c13-136">**AffCheck:**</span><span class="sxs-lookup"><span data-stu-id="c1c13-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="c1c13-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="c1c13-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-138">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-138">Description</span></span>

<span data-ttu-id="c1c13-139">PersistentChatMonitoringSummary 도구는 모니터링 데이터베이스에서 지정 된 CSV 로그 파일로 지속적인 채팅 모니터링 정보를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="c1c13-140">CSV 파일에는 총 세션 수, 성공한 세션, 예기치 않은 오류, 예상 오류, 진단 ID에의 한 예기치 않은 오류 분석, 오류 횟수, 오류 설명 등의 지속적인 채팅 세션의 분석이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-141">Requirements</span></span>

<span data-ttu-id="c1c13-142">모니터링 데이터베이스에 액세스할 수 있는 도메인에 연결 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="c1c13-143">도구가 실행 되는 사용자 계정에는 모니터링 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="c1c13-144">파일에는 모니터링 데이터베이스에 대 한 연결 문자열을 정의 \<하\> 는 connectionStrings 섹션이 포함 되어 있어야 합니다 PersistentChatMonitoringSummary.</span><span class="sxs-lookup"><span data-stu-id="c1c13-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="c1c13-145">또한 모니터링 데이터를 수집 하는 PersistentChatEndpointUri에 대 한 키와 생성 될 CSV 파일의 위치에 대 한 파일 경로를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="c1c13-146">예제를 보려면 설치 된 구성 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c13-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="c1c13-147">이 파일은 도구와 같은 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-148">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="c1c13-149">이러한 매개 변수는 데이터 선택 항목을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="c1c13-150">**StartDateTime:** 선택 기간의 시작 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="c1c13-151">기본값: 오전 1/1/1753 12:00:00</span><span class="sxs-lookup"><span data-stu-id="c1c13-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="c1c13-152">**Enddatetime:** 선택 기간의 마지막 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="c1c13-153">기본값: 이제</span><span class="sxs-lookup"><span data-stu-id="c1c13-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c1c13-154">예</span><span class="sxs-lookup"><span data-stu-id="c1c13-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="c1c13-155">영구 채팅 스트레스 도구</span><span class="sxs-lookup"><span data-stu-id="c1c13-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-156">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-156">Description</span></span>

<span data-ttu-id="c1c13-157">영구 채팅 스트레스 도구를 사용 하 여 예상 되는 사용 시나리오에 맞게 다양 한 사용자 모델을 포함 하 여 실제 성과를 테스트 하는 영구 채팅을 쉽게 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-158">Requirements</span></span>

<span data-ttu-id="c1c13-159">영구 채팅 백 엔드 데이터베이스에 액세스할 수 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c1c13-160">이 *컨트롤러* 컴퓨터 외에도 여러 *로더* 컴퓨터를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="c1c13-161">사용자 모델의 모든 10K 사용자는 로더 컴퓨터에 최소 4GB의 무료 RAM이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="c1c13-162">예를 들어, 80K 사용자와의 실행에는 모든 로더 컴퓨터에서 32GB의 RAM이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="c1c13-163">예상 되는 로드에 관계 없이 세 개 이상의 로더 컴퓨터를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="c1c13-164">로더 컴퓨터에는 .NET 4.5 프레임 워크 및 Visual c + + 2012 재배포 가능이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="c1c13-165">구성</span><span class="sxs-lookup"><span data-stu-id="c1c13-165">Configuration</span></span>

<span data-ttu-id="c1c13-166">ChatStressTool 파일을 모든 로더 컴퓨터에서 액세스할 수 있는 공유 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="c1c13-167">스트레스 실행에 사용할 사용자 및 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="c1c13-168">사용자에 게 필요한 만큼의 사용자를 만들고 Lync에서 사용할 수 있도록 설정 하 고 영구 채팅 정책을 사용으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="c1c13-169">스트레스 채널의 범주를 만든 다음 해당 범주 아래에 필요한 만큼의 채팅방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="c1c13-170">범주에는 모든 스트레스 사용자의 **허용** 목록 (OU를 추가 하는 방법)이 있어야 하며, 스트레스 방에는 **공개**의 개인 정보 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="c1c13-171">추가 스트레스 방을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="c1c13-172">다음 Windows PowerShell 명령줄 인터페이스 명령을 사용 하 여 5만 방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="c1c13-173">토폴로지에 맞게 구성 파일을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="c1c13-174">**LoaderProcess**에서 "controller.contoso.com"를 컨트롤러 컴퓨터의 FQDN (정규화 된 도메인 이름)으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="c1c13-175">**StressLauncher에서 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1c13-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="c1c13-176">"LoaderBinary" 설정 값을 공유 폴더의 경로로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="c1c13-177">"AdminUser"/"Adminuser"를 관리자 액세스 권한이 있는 자격 증명으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="c1c13-178">"ChannelCategory"를 스트레스 채널이 생성 된 범주의 이름으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="c1c13-179">스트레스 사용자 자격 증명과 일치 하는 서식 파일로 "UserNamePattern" 및 "UserPasswordPattern"을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="c1c13-180">{0}사용자의 인덱스 번호로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="c1c13-181">"도메인"을 테스트 토폴로지의 SIP 도메인으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="c1c13-182">"ConnectionString"을 영구 채팅 백 엔드 데이터베이스에 대 한 연결 문자열로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="c1c13-183">"UserIndexStart"를 첫 번째 스트레스 사용자의 인덱스로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="c1c13-184">"L Cfqdn"을 프런트 엔드 풀의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="c1c13-185">"컴퓨터" 목록을 수정 하 여 모든 로더 컴퓨터의 컴퓨터 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="c1c13-186">서비스 끝점의 baseAddress (기본값은 "controller.contoso.com")을 컨트롤러 컴퓨터의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-187">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-187">Usage</span></span>

<span data-ttu-id="c1c13-188">구성이 완료 되 면 컨트롤러 컴퓨터에서 StressLauncher를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="c1c13-189">모든 사용자로 StressLauncher를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="c1c13-190">Loader 시스템에서 시작 하는 로더 프로세스를 구성 파일에서 지정 해야 하는 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="c1c13-191">또한 영구 채팅 백 엔드 데이터베이스에 대 한 읽기 권한이 있는 연결 문자열을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c1c13-192">이 연결 문자열이 Windows 통합 인증을 사용 하는 경우이 액세스 권한이 있는 사용자로 StressLauncher를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="c1c13-193">필요에 따라 사용자 모델 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="c1c13-194">**로드 시작** 을 클릭 하 여 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="c1c13-195">1 분이 지난 후에도 사용자가 로그인 하 고 진행률 표시줄이 채우기 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="c1c13-196">이 시점에서 컨트롤러 컴퓨터가 작동 하 고 성능 측정을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="c1c13-197">로이 업그레이드 확인 프로그램</span><span class="sxs-lookup"><span data-stu-id="c1c13-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-198">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-198">Description</span></span>

<span data-ttu-id="c1c13-199">메시지 Upgradeverifier는 영구 채팅 관련 데이터베이스 비교 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="c1c13-200">이 도구는 그룹 채팅 2007 R2 또는 그룹 채팅 2010 데이터베이스 (2007/2010Db)를 영구 채팅 2013 데이터베이스 (2013Db)와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="c1c13-201">이 도구는 2007/2010Db의 각 범주, 영구 채팅방, 추가 기능을 검사 하 여 2013Db에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="c1c13-202">비교에는 범주, 채팅방 또는 추가 기능에 대 한 모든 설정, 범주에 속하는 모든 주체, 범주 또는 채팅방의 역할에 속하는 모든 사용자에 대 한 검사가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="c1c13-203">2013Db에 범주 또는 채팅방이 올바르게 표시 되지 않는 경우 차이점은 충돌 파일에 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="c1c13-204">업그레이드가 발생 한 후에 2007/2010Db가 변경 되 고이 도구가 실행 되 면 충돌 파일에 차이점이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="c1c13-205">이 응용 프로그램은 데이터베이스 비교 도구 이므로 업그레이드 프로세스의 유효성을 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-206">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-206">Requirements</span></span>

<span data-ttu-id="c1c13-207">영구 채팅 백 엔드 데이터베이스에 액세스할 수 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다 (이전 버전과 영구 채팅의 최신 버전).</span><span class="sxs-lookup"><span data-stu-id="c1c13-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="c1c13-208">도구가 실행 되는 사용자 계정에 영구 채팅 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="c1c13-209">GroupChat2007R2Db 매개 변수 또는 GroupChat2010Db 매개 변수 중 하나를 포함 해야 하며,이는 적절 한 그룹 채팅 데이터베이스 (Groupchat 2007R2 또는 2010)에 대 한 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="c1c13-210">또한 영구 채팅 2013 데이터베이스에 대 한 연결 문자열을 사용 하 여 PersistentChat2013Db 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-211">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-211">Usage</span></span>

<span data-ttu-id="c1c13-212">매개 변수 없이 \* | **verifier** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c1c13-213">예</span><span class="sxs-lookup"><span data-stu-id="c1c13-213">Example</span></span>

<span data-ttu-id="c1c13-214">![ChatUpgradeVerifier.exe 실행.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe 실행.")</span><span class="sxs-lookup"><span data-stu-id="c1c13-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="c1c13-215">영구 채팅 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="c1c13-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-216">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-216">Description</span></span>

<span data-ttu-id="c1c13-217">ChatUsageReport 도구는 영구 채팅 서비스 사용 현황에 대 한 HTML 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-218">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-218">Requirements</span></span>

<span data-ttu-id="c1c13-219">영구 채팅 백 엔드 데이터베이스에 액세스할 수 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c1c13-220">도구가 실행 되는 사용자 계정에 영구 채팅 백 엔드 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c1c13-221">ChatUsageReport 파일에는 영구 채팅 백 엔드 데이터베이스에 대 한 \<연결\> 문자열을 정의 하는 connectionStrings 섹션이 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c1c13-222">기본 구성 파일의 내용은 참조에 대해 여기에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-223">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="c1c13-224">이러한 매개 변수는 데이터 선택 항목을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="c1c13-225">시작 날짜 **:** 선택 기간의 UTC 시작 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="c1c13-226">기본값: 가장 빠른 날짜</span><span class="sxs-lookup"><span data-stu-id="c1c13-226">Default: Earliest Date</span></span>

<span data-ttu-id="c1c13-227">**EndDate:** 선택 기간의 UTC 종료 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="c1c13-228">기본값: 이제</span><span class="sxs-lookup"><span data-stu-id="c1c13-228">Default: Now</span></span>

<span data-ttu-id="c1c13-229">이러한 매개 변수는 표시 되는 데이터 및 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="c1c13-230">**Topactiveusers:** 이를 지정 하는 경우, 보고서에는 사용자가 선택한 기간 동안 채팅방에 게시 한 메시지 수에 대 한 조건으로 n 개 중 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="c1c13-231">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="c1c13-231">Default: 10</span></span>

<span data-ttu-id="c1c13-232">**TopActiveRooms:** 이를 지정 하는 경우 보고서에는 선택한 기간 동안 방에 게시 된 메시지 수에 대 한 조건으로 n 개의 가장 활발 한 채팅방이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="c1c13-233">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="c1c13-233">Default: 10</span></span>

<span data-ttu-id="c1c13-234">**LeastActiveRooms:** 이를 지정 하면 보고서에는 선택한 기간에 대 한 채팅방에 게시 된 메시지 수에 따라 n 개의 최소 활성 채팅방이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="c1c13-235">채팅방에는 하나 이상의 메시지가 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="c1c13-236">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="c1c13-236">Default: 10</span></span>

<span data-ttu-id="c1c13-237">**RoomsInactiveSince:** 이를 지정 하면 보고서에는 지정 된 날짜 이후에 비활성화 된 채팅방 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="c1c13-238">기본값: 전체 시간</span><span class="sxs-lookup"><span data-stu-id="c1c13-238">Default: Entire Time</span></span>

<span data-ttu-id="c1c13-239">**Outputfolder:** ChatUsageReport 및 그래프 이미지를 배치할 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="c1c13-240">이는 config 파일 또는 명령줄에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="c1c13-241">모든 명령줄 매개 변수 값은 도구와 같은 디렉터리에 있는 ChatUsageReport 파일에도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="c1c13-242">Config 파일과 명령줄에 모두 값이 지정 되어 있으면 명령줄 값이 config 파일 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="c1c13-243">결과물</span><span class="sxs-lookup"><span data-stu-id="c1c13-243">Output</span></span>

<span data-ttu-id="c1c13-244">보고서에는 항상 다음 출력이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="c1c13-245">최고 n 개의 가장 활발 한 채팅방 선택한 기간의 메시지 게시물 수를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c1c13-246">선택한 기간 동안 가장 많은 수의 메시지 게시물에 대 한 최고 n의 활성 사용자</span><span class="sxs-lookup"><span data-stu-id="c1c13-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c1c13-247">선택한 기간에 대 한 메시지 게시물 수에 따라 상위 n 개의 가장 활발 한 채팅방 채팅방입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c1c13-248">데이터베이스의 전체 수명 동안 또는 지정 된 날짜 이후로 사용할 수 없는 채팅방입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="c1c13-249">선택한 기간에 대 한 일일 메시지 게시 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="c1c13-250">선택한 기간에 대 한 주간 메시지 게시 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="c1c13-251">선택한 기간에 대 한 월간 메시지 게시 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="c1c13-252">선택한 기간의 총 메시지 게시물입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="c1c13-253">사용 하도록 설정 된 회의실의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c1c13-254">예</span><span class="sxs-lookup"><span data-stu-id="c1c13-254">Example</span></span>

<span data-ttu-id="c1c13-255">다음 예제에서는 전체 연도 2001에 대 한 사용 현황 보고서를 생성 하 고 보고서를 ChatUsageReport에 지정 된 OutputFolder에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="c1c13-256">ChatUsageReport:</span><span class="sxs-lookup"><span data-stu-id="c1c13-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="c1c13-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="c1c13-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c1c13-258">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-258">Description</span></span>

<span data-ttu-id="c1c13-259">ScheduleADSyncForPrincipal는 영구 채팅 백 엔드 데이터베이스에 연결 되어 있을 때 SQL Server Management Studio 내에서 직접 실행 해야 하는 Microsoft SQL Server 2012 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c1c13-260">이 스크립트를 사용 하면 영구 채팅을 통해 사용자의 레코드를 예약 된 동기화 시간을 기다리지 않고 Active Directory 도메인 서비스의 해당 레코드로 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c1c13-261">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c13-261">Requirements</span></span>

<span data-ttu-id="c1c13-262">스크립트를 실행 하는 사용자 계정에 영구 채팅 백 엔드 데이터베이스에 대 한 소유자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c1c13-263">용도</span><span class="sxs-lookup"><span data-stu-id="c1c13-263">Usage</span></span>

<span data-ttu-id="c1c13-264">다음은 기본 스크립트의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

