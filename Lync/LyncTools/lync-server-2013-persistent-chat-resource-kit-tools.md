---
title: Lync Server 2013 영구 채팅 리소스 킷 도구
description: Lync Server 2013 영구 채팅 리소스 키트 도구
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
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542354"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="08f59-103">Lync Server 2013 영구 채팅 리소스 킷 도구</span><span class="sxs-lookup"><span data-stu-id="08f59-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f59-104">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="08f59-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="08f59-105">Lync Server 2013 영구 채팅 리소스 키트 도구를 통해 Lync Server 2013 영구 채팅 서버를 배포 하 고 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="08f59-106">이 항목에서는 설치 지침 외에도, 각 도구의 목적과 사용 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="08f59-107">리소스 키트 도구 설치</span><span class="sxs-lookup"><span data-stu-id="08f59-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="08f59-108">Lync Server 2013, 리소스 키트 도구를 설치 하려면 **PersistentChatReskit.msi**를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="08f59-109">단순 설치를 수행 하려면 **PersistentChatReskit.msi** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="08f59-110">.Msi는 \\ **프로그램 파일 \\ Microsoft Lync Server 2013 \\ 영구 채팅 서버 Resource Kit**경로에 있는 모든 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="08f59-111">자체 포함 된 실행 파일은이 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="08f59-112">파일을 포함 하는 도구는 자체 하위 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08f59-113">Lync Server 2013, Resource Kit Tools를 설치한 후에 <STRONG>PsExec.exe</STRONG> 를 설치 하 고 <STRONG>PsExec.exe</STRONG> 를 \\ <STRONG>프로그램 파일 \ Microsoft Lync Server 2013 \ 영구 채팅 서버 리소스 Kit\ChatStressTool</STRONG>경로에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="08f59-114"><STRONG>PsExec.exe</STRONG>를 복사 하지 않으면 영구 채팅 스트레스 도구에서 오류 예외를 throw 하며 제대로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="08f59-115">도구를 실행 하기 전에이 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="08f59-116"><STRONG>PsExec.exe</STRONG>설치에 대 한 자세한 내용은를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .</span><span class="sxs-lookup"><span data-stu-id="08f59-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="08f59-117">지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="08f59-117">Supported Environments</span></span>

<span data-ttu-id="08f59-118">최적의 성능을 위해서는 lync server 2013, Resource Kit 도구를 동일한 환경 및 Lync Server 2013에 필요한 사양과 동일 하 게 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="08f59-119">리소스 키트 도구 개요</span><span class="sxs-lookup"><span data-stu-id="08f59-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="08f59-120">Lync Server 2013 영구 채팅 리소스 키트에 제공 되는 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="08f59-121">다음 섹션에서는 요구 사항 및 사용 예제를 비롯 한 각 도구에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="08f59-122">AffCheck</span><span class="sxs-lookup"><span data-stu-id="08f59-122">AffCheck</span></span>

  - <span data-ttu-id="08f59-123">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="08f59-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="08f59-124">(가) 스트레스 도구</span><span class="sxs-lookup"><span data-stu-id="08f59-124">ChatStress Tool</span></span>

  - <span data-ttu-id="08f59-125">\ 업그레이드 확인 프로그램</span><span class="sxs-lookup"><span data-stu-id="08f59-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="08f59-126">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="08f59-126">ChatUsageReport</span></span>

  - <span data-ttu-id="08f59-127">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="08f59-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="08f59-128">AffCheck</span><span class="sxs-lookup"><span data-stu-id="08f59-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-129">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-129">Description</span></span>

<span data-ttu-id="08f59-130">AffCheck 도구는 영구 채팅 백 엔드 데이터베이스 사용자 및 그룹 정보 레코드가 Active Directory 도메인 서비스와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-131">Requirements</span></span>

<span data-ttu-id="08f59-132">이 도구는 도메인에 가입 된 컴퓨터에서 PersistentChatResKit 설치 관리자와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="08f59-133">도구를 실행 하는 데 사용 되는 사용자 계정에 영구 채팅 백 엔드 데이터베이스 및 Active Directory 도메인 서비스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-134">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-134">Usage</span></span>

<span data-ttu-id="08f59-135">Config 파일의 지침에 따라 AffCheck.exe.config 파일을 구성 하 고 명령줄 매개 변수를 사용 하지 않고 AffCheck 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="08f59-136">다음은 기본 AffCheck.exe.config의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="08f59-137">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="08f59-137">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="08f59-138">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="08f59-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-139">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-139">Description</span></span>

<span data-ttu-id="08f59-140">PersistentChatMonitoringSummary 도구는 모니터링 데이터베이스의 영구 채팅 모니터링 정보를 지정 된 CSV 로그 파일로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="08f59-141">CSV 파일에는 전체 세션 수, 성공한 세션, 예기치 않은 오류, 예상 오류 및 진단 ID에서 예기치 않은 오류 분석, 오류 발생 횟수 및 실패 설명 별 영구 채팅 세션의 분석 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-142">Requirements</span></span>

<span data-ttu-id="08f59-143">모니터링 데이터베이스에 액세스할 수 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="08f59-144">도구를 실행 하는 데 사용 하는 사용자 계정에는 모니터링 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="08f59-145">PersistentChatMonitoringSummary.exe.config 파일은 \<connectionStrings\> 모니터링 데이터베이스에 대 한 연결 문자열을 정의 하는 섹션을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="08f59-146">또한 모니터링 데이터를 수집할 PersistentChatEndpointUri 키와 생성 될 CSV 파일의 위치에 대 한 파일 경로를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="08f59-147">예를 보려면 설치 된 구성 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="08f59-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="08f59-148">이 파일은 도구와 같은 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-149">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="08f59-150">다음 매개 변수는 데이터의 선택 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="08f59-151">**StartDateTime:** 선택 기간의 시작 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="08f59-152">기본값: 오전 1/1/1753 12:00:00</span><span class="sxs-lookup"><span data-stu-id="08f59-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="08f59-153">**Enddatetime:** 선택 기간의 마지막 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="08f59-154">기본값: Now</span><span class="sxs-lookup"><span data-stu-id="08f59-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="08f59-155">예제</span><span class="sxs-lookup"><span data-stu-id="08f59-155">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="08f59-156">영구 채팅 스트레스 도구</span><span class="sxs-lookup"><span data-stu-id="08f59-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-157">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-157">Description</span></span>

<span data-ttu-id="08f59-158">영구 채팅 스트레스 도구를 사용 하면 예상 되는 사용 시나리오에 보다 적합 한 다양 한 사용자 모델을 포함 하 여 실제 성능을 테스트 하기 위한 영구 채팅의 사용량을 쉽게 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-159">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-159">Requirements</span></span>

<span data-ttu-id="08f59-160">영구 채팅 백 엔드 데이터베이스에 대 한 액세스 권한이 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="08f59-161">이 *컨트롤러* 컴퓨터 외에도 여러 *로더* 컴퓨터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="08f59-162">사용자 모델의 모든 10K 사용자에 대해 로더 컴퓨터에 최소한 4GB의 사용 가능한 RAM이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="08f59-163">예를 들어, 80K 사용자와의 실행에는 모든 로더 컴퓨터에 대해 32GB의 RAM이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="08f59-164">예상 되는 부하에 관계 없이 최소 3 개의 로더 컴퓨터를 보유 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="08f59-165">로더 컴퓨터에는 Visual c + + 2012 재배포 가능 패키지와 함께 .NET 4.5 Framework가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="08f59-166">구성</span><span class="sxs-lookup"><span data-stu-id="08f59-166">Configuration</span></span>

<span data-ttu-id="08f59-167">ChatStressTool 파일을 모든 로더 컴퓨터에서 액세스할 수 있는 공유 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="08f59-168">스트레스 실행에 사용할 사용자 및 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="08f59-169">사용자 모델 호출에 필요한 수 만큼 사용자를 만들고, Lync에 사용 하도록 설정 하 고, 영구 채팅 정책을 사용으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="08f59-170">스트레스 채널에 대 한 범주를 만든 다음 해당 범주에 필요한 만큼의 대화방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="08f59-171">범주는 모든 스트레스 사용자를 **허용** 된 목록 (OU 추가)에 포함 해야 하며, 전체 스트레스 대화방은 **공개**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="08f59-172">추가 스트레스 방을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="08f59-173">다음 Windows PowerShell 명령줄 인터페이스 명령을 사용 하 여 5만 채팅방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="08f59-174">토폴로지에 맞게 구성 파일을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="08f59-175">**LoaderProcess.exe.config**에서 "controller.contoso.com"를 컨트롤러 컴퓨터의 FQDN (정규화 된 도메인 이름)으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="08f59-176">**StressLauncher.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="08f59-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="08f59-177">"LoaderBinary" 설정 값을 공유 폴더의 경로로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="08f59-178">로더 컴퓨터에 대 한 관리자 액세스 권한이 있는 자격 증명으로 "AdminUser"/"Adminuser"를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="08f59-179">"ChannelCategory"를 스트레스 채널이 만들어진 범주의 이름으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="08f59-180">"UserNamePattern" 및 "UserPasswordPattern"을 스트레스 사용자 자격 증명과 일치 하는 서식 파일로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="08f59-181">{0} 사용자의 인덱스 번호로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="08f59-182">"도메인"을 테스트 토폴로지의 SIP 도메인으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="08f59-183">"ConnectionString"를 영구 채팅 백 엔드 데이터베이스에 대 한 연결 문자열로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="08f59-184">"UserIndexStart"를 첫 번째 스트레스 사용자의 인덱스로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="08f59-185">"LyncFQDN"을 프런트 엔드 풀의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="08f59-186">모든 로더 컴퓨터의 컴퓨터 이름을 포함 하도록 "컴퓨터" 목록을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="08f59-187">서비스 끝점의 baseAddress (기본값: "controller.contoso.com")를 컨트롤러 컴퓨터의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-188">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-188">Usage</span></span>

<span data-ttu-id="08f59-189">구성이 완료 되 면 컨트롤러 컴퓨터에서 StressLauncher.exe를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="08f59-190">모든 사용자로 StressLauncher을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="08f59-191">로더 시스템에서 시작 하는 로더 프로세스를 구성 파일에 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="08f59-192">또한 영구 채팅 백 엔드 데이터베이스에 대 한 읽기 권한이 있는 연결 문자열을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="08f59-193">이 연결 문자열이 Windows 통합 인증을 사용 하는 경우에는이 액세스 권한이 있는 사용자로 StressLauncher을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="08f59-194">필요에 따라 사용자 모델 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="08f59-195">**로드 시작** 을 클릭 하 여 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="08f59-196">1 분 후에 사용자는 로그인을 시작 하 고 진행률 표시줄이 채우기 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="08f59-197">이때 컨트롤러 시스템이 작동 하 고 성능 측정이 수행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="08f59-198">\ 업그레이드 확인 프로그램</span><span class="sxs-lookup"><span data-stu-id="08f59-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-199">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-199">Description</span></span>

<span data-ttu-id="08f59-200">\ 업그레이드 확인 프로그램은 영구 채팅 관련 데이터베이스 비교 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="08f59-201">이 도구는 그룹 채팅 2007 R2 또는 그룹 채팅 2010 데이터베이스 (2007/2010Db)를 영구 채팅 2013 데이터베이스 (2013Db)로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="08f59-202">이 도구는 2007/2010Db에서 하나씩, 하나씩, 각 범주, 영구 채팅방 및 추가 기능을 검사 하 여 2013Db에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="08f59-203">비교에는 범주, 대화방 또는 추가 기능의 모든 설정, 해당 범주의 범위에 있는 모든 주체 및 범주 또는 대화방의 역할에 있는 모든 사용자의 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="08f59-204">2013Db에서 범주나 대화방이 올바르게 나타나지 않으면 충돌 파일에 차이가 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="08f59-205">업그레이드가 발생 한 후에 2007/2010Db가 변경 되 고이 도구가 실행 되 면 충돌 파일에 차이가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="08f59-206">이 응용 프로그램은 데이터베이스 비교 도구이 고 업그레이드 프로세스를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-207">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-207">Requirements</span></span>

<span data-ttu-id="08f59-208">영구 채팅 백 엔드 데이터베이스에 대 한 액세스 권한이 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다 (영구 채팅의 이전 버전과 현재 버전).</span><span class="sxs-lookup"><span data-stu-id="08f59-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="08f59-209">도구를 실행 하는 데 사용 하는 사용자 계정에 영구 채팅 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="08f59-210">ChatUpgradeVerifier.exe.config 파일에는 GroupChat2007R2Db 매개 변수 또는 GroupChat2010Db 매개 변수가 포함 되어야 하며 해당 그룹 채팅 데이터베이스 (Groupchat 2007R2 또는 2010)에 대 한 연결 문자열을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="08f59-211">또한 영구 채팅 2013 데이터베이스에 대 한 연결 문자열을 사용 하 여 PersistentChat2013Db 매개 변수도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-212">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-212">Usage</span></span>

<span data-ttu-id="08f59-213">매개 변수를 사용 하지 않고 \ **업그레이드 확인 프로그램** 을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="08f59-214">예제</span><span class="sxs-lookup"><span data-stu-id="08f59-214">Example</span></span>

<span data-ttu-id="08f59-215">![ChatUpgradeVerifier.exe 실행](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe 실행")</span><span class="sxs-lookup"><span data-stu-id="08f59-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="08f59-216">영구 채팅 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="08f59-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-217">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-217">Description</span></span>

<span data-ttu-id="08f59-218">ChatUsageReport 도구는 영구 채팅 서비스 사용 현황에 대 한 HTML 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-219">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-219">Requirements</span></span>

<span data-ttu-id="08f59-220">영구 채팅 백 엔드 데이터베이스에 대 한 액세스 권한이 있는 도메인에 가입 된 컴퓨터에 영구 채팅 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="08f59-221">도구를 실행 하는 데 사용 되는 사용자 계정에 영구 채팅 백 엔드 데이터베이스에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="08f59-222">ChatUsageReport.exe.config 파일은 \<connectionStrings\> 영구 채팅 백 엔드 데이터베이스에 대 한 연결 문자열을 정의 하는 섹션을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="08f59-223">기본 구성 파일의 내용은 참조용으로 여기에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-224">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="08f59-225">다음 매개 변수는 데이터의 선택 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="08f59-226">시작 날짜 **:** 선택 기간의 UTC 시작 날짜를 선택적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="08f59-227">기본값: 가장 빠른 날짜</span><span class="sxs-lookup"><span data-stu-id="08f59-227">Default: Earliest Date</span></span>

<span data-ttu-id="08f59-228">**EndDate:** 선택적으로 선택 기간의 UTC 종료 날짜를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="08f59-229">기본값: Now</span><span class="sxs-lookup"><span data-stu-id="08f59-229">Default: Now</span></span>

<span data-ttu-id="08f59-230">다음 매개 변수는 표시 되는 데이터 및 결과를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="08f59-231">**Topactiveusers:** 이 값이 지정 된 경우 보고서에는 사용자가 선택한 기간 동안 대화방에 게시 한 메시지 수에 대 한 용어의 가장 활성 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="08f59-232">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="08f59-232">Default: 10</span></span>

<span data-ttu-id="08f59-233">**TopActiveRooms:** 이 값이 지정 된 경우 보고서에는 선택한 기간 동안 대화방에 게시 된 메시지 수에 대 한 용어로 가장 많이 사용 하는 채팅방이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="08f59-234">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="08f59-234">Default: 10</span></span>

<span data-ttu-id="08f59-235">**LeastActiveRooms:** 이 값이 지정 된 경우 보고서에는 선택한 기간에 대해 대화방에 게시 된 메시지 수에 따라 최소 활성 대화방이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="08f59-236">대화방에는 하나 이상의 메시지가 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="08f59-237">기본값: 10</span><span class="sxs-lookup"><span data-stu-id="08f59-237">Default: 10</span></span>

<span data-ttu-id="08f59-238">**RoomsInactiveSince:** 이를 지정 하면 보고서에 지정 된 날짜 이후에 비활성화 된 대화방 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="08f59-239">기본값: 전체 시간</span><span class="sxs-lookup"><span data-stu-id="08f59-239">Default: Entire Time</span></span>

<span data-ttu-id="08f59-240">**Outputfolder:** ChatUsageReport.html 및 그래프 이미지를 배치할 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="08f59-241">이는 config 파일 또는 명령줄에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="08f59-242">도구와 같은 디렉터리에 있는 ChatUsageReport.exe.config 파일에 모든 명령줄 매개 변수 값을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="08f59-243">Config 파일과 명령줄에 모두 값이 지정 되어 있으면 명령줄 값이 config 파일 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="08f59-244">출력</span><span class="sxs-lookup"><span data-stu-id="08f59-244">Output</span></span>

<span data-ttu-id="08f59-245">보고서에는 항상 다음과 같은 출력이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="08f59-246">선택 된 기간 동안의 메시지 게시물 수에 따라 최고 n 개 가장 활발 한 채팅방 대화방입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="08f59-247">선택한 기간에 대 한 메시지 게시물 수 별 최고 n 명의 가장 활성 사용자</span><span class="sxs-lookup"><span data-stu-id="08f59-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="08f59-248">선택한 기간에 대 한 메시지 게시물 수 별 가장 낮은 최소 활성 대화방 대화방</span><span class="sxs-lookup"><span data-stu-id="08f59-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="08f59-249">데이터베이스의 전체 수명 동안 또는 지정 된 날짜 이후에 비활성 상태인 대화방입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="08f59-250">선택한 기간에 대 한 일별 메시지 사후 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="08f59-251">선택한 기간에 대 한 주간 메시지 게시 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="08f59-252">선택한 기간에 대 한 월별 메시지 사후 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="08f59-253">선택한 기간에 대 한 총 메시지 게시물입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="08f59-254">사용 하도록 설정 된 대화방의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="08f59-255">예제</span><span class="sxs-lookup"><span data-stu-id="08f59-255">Example</span></span>

<span data-ttu-id="08f59-256">다음 예제에서는 전체 연도 2001에 대 한 사용 현황 보고서를 생성 하 고 ChatUsageReport.exe.config에 지정 된 OutputFolder에 보고서를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="08f59-257">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="08f59-257">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="08f59-258">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="08f59-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="08f59-259">설명</span><span class="sxs-lookup"><span data-stu-id="08f59-259">Description</span></span>

<span data-ttu-id="08f59-260">ScheduleADSyncForPrincipal은 영구 채팅 백 엔드 데이터베이스에 연결 될 때 SQL Server Management Studio 내에서 직접 실행 해야 하는 Microsoft SQL Server 2012 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="08f59-261">이 스크립트를 사용 하면 예약 된 동기화 시간을 기다리지 않고 영구 채팅을 통해 사용자의 레코드를 Active Directory 도메인 서비스와 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="08f59-262">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f59-262">Requirements</span></span>

<span data-ttu-id="08f59-263">스크립트를 실행 하는 데 사용 되는 사용자 계정에 영구 채팅 백 엔드 데이터베이스에 대 한 소유자 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="08f59-264">Usage</span><span class="sxs-lookup"><span data-stu-id="08f59-264">Usage</span></span>

<span data-ttu-id="08f59-265">다음은 기본 스크립트의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="08f59-265">Following are the contents of the default script:</span></span>

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

