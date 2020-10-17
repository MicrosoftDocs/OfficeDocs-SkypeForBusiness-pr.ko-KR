---
title: Lync Server 2013 Resource Kit 도구 설명서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c2260f5729c45455596f0ab2477f7a190ef520
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509225"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="b133d-102">Lync Server 2013 Resource Kit 도구 설명서</span><span class="sxs-lookup"><span data-stu-id="b133d-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b133d-103">_**마지막으로 수정 된 항목:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="b133d-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="b133d-104">이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 Lync Server 2013 Resource Kit에 포함 되는 도구에 대해 설명 합니다. Lync Server 2013, Resource Kit 도구를 통해 Lync Server 2013를 배포 및 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="b133d-105">예를 들어 **웹 회의 데이터** 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="b133d-106">**SEFAUtil** 도구를 사용 하 여 사용자에 대 한 착신 전환 및 응답을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="b133d-107">IT 관리자는 이러한 도구를 사용 하 여 Lync Server 2013을 보다 효율적으로 관리할 수 있도록 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="b133d-108">리소스 키트 도구 설치</span><span class="sxs-lookup"><span data-stu-id="b133d-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="b133d-109">Lync Server 2013, 리소스 키트 도구를 설치 하려면 **OCSReskit.msi**를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="b133d-110">리소스 키트 도구 설치 관리자는의 다운로드 센터에서 다운로드할 수 있습니다 [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .</span><span class="sxs-lookup"><span data-stu-id="b133d-110">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="b133d-111">단순 설치를 수행 하려면 **OCSResKit.msi** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="b133d-112">.Msi는 다음 경로에 있는 모든 도구를 설치 합니다: **% Program Files% \\ Microsoft Lync Server 2013 \\ ResKit**.</span><span class="sxs-lookup"><span data-stu-id="b133d-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="b133d-113">자체 포함 된 실행 파일은이 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="b133d-114">파일을 포함 하는 도구는 자체 하위 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="b133d-115">지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="b133d-115">Supported Environments</span></span>

<span data-ttu-id="b133d-116">최적의 성능을 위해서는 lync server 2013, Resource Kit 도구를 동일한 환경 및 Lync Server 2013에 필요한 사양과 동일 하 게 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="b133d-117">리소스 키트 도구 개요</span><span class="sxs-lookup"><span data-stu-id="b133d-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="b133d-118">다음 목록에서는 Lync Server 2013 Resource Kit에서 제공 되는 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="b133d-119">요구 사항 및 사용 예를 비롯 한 각 도구에 대 한 설명은 다음 섹션에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="b133d-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b133d-120">ABSConfig</span></span>

  - <span data-ttu-id="b133d-121">대역폭 정책 서비스 모니터</span><span class="sxs-lookup"><span data-stu-id="b133d-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="b133d-122">대역폭 사용률 분석기</span><span class="sxs-lookup"><span data-stu-id="b133d-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="b133d-123">통화 Parkometer</span><span class="sxs-lookup"><span data-stu-id="b133d-123">Call Parkometer</span></span>

  - <span data-ttu-id="b133d-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b133d-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="b133d-125">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="b133d-125">DBAnalyze</span></span>

  - <span data-ttu-id="b133d-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b133d-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="b133d-127">Lcssync.dll</span><span class="sxs-lookup"><span data-stu-id="b133d-127">LCSSync</span></span>

  - <span data-ttu-id="b133d-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="b133d-128">LookupUserConsole</span></span>

  - <span data-ttu-id="b133d-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b133d-129">MsTurnPing</span></span>

  - <span data-ttu-id="b133d-130">네트워크 구성 뷰어</span><span class="sxs-lookup"><span data-stu-id="b133d-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="b133d-131">응답 그룹 에이전트 라이브</span><span class="sxs-lookup"><span data-stu-id="b133d-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="b133d-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b133d-132">SEFAUtil</span></span>

  - <span data-ttu-id="b133d-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b133d-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="b133d-134">할당 되지 않은 번호 알림 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b133d-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="b133d-135">웹 회의 데이터</span><span class="sxs-lookup"><span data-stu-id="b133d-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="b133d-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b133d-136">ABSConfig</span></span>

<span data-ttu-id="b133d-137">ABSConfig (주소록 서비스 구성 도구)는 관리자가 Lync Server 2013에서 주소록 서비스 구성을 사용자 지정 하는 데 도움이 되는 관리 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="b133d-138">또한이 도구를 사용 하면 Lync Server 2013 관리자가 기본 주소록 서비스 설정을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-139">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-139">Description</span></span>

<span data-ttu-id="b133d-140">ABSConfig는 관리자가 주소록 서비스와 관련 된 Active Directory 도메인 서비스 특성을 구성할 수 있도록 하는 그래픽 사용자 인터페이스 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="b133d-141">도구에 대 한 기본 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="b133d-142">관리자가 Active Directory 도메인 서비스의 특성을 Lync Server 2013의 특성에 매핑할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="b133d-143">관리자가 주소록 서비스 파일에 포함 하거나 제외할 Active Directory 도메인 서비스 특성을 지정할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="b133d-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="b133d-144">관리자가 기본 주소록 서비스 설정을 복원 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="b133d-145">ABSConfig 도구는 absConfig.exe 파일을 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="b133d-146">도구를 열면 **특성 구성** 탭이 열립니다. 이 테이블에는 Active Directory 도메인 서비스 특성을 Lync Server 2013의 특성 필드에 매핑하고, 특정 특성 필터를 기준으로 주소록 서비스 파일에 포함 하거나 제외할 사용자를 지정 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="b133d-147">또한 주소록 파일에 포함할 전화 번호의 값을 사용자 지정 하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="b133d-148">관리자는 **기본값 복원** 옵션을 사용 하 여 주소록 서비스 설정을 기본값으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="b133d-149">Lync Server 2010의 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b133d-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="b133d-150">Lync Server 2013 ABS 구성 도구에서 특성에 대해 "사용" 확인란을 선택 취소 하 여 특성 (행)을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="b133d-151">이는 Lync Server 2010에서 행을 삭제 하는 것과 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-152">사용 확인란은 오른쪽 끝 열에 있습니다. 열을 보려면 오른쪽으로 스크롤해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-153">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-153">Output</span></span>

<span data-ttu-id="b133d-154">ABSConfig는 주소록 서비스 구성을 데이터베이스에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-155">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-155">Purpose</span></span>

<span data-ttu-id="b133d-156">ABSConfig에서는 Lync Server 2013 주소록 서비스를 빠르고 쉽게 사용자 지정할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="b133d-158">컴퓨터</span><span class="sxs-lookup"><span data-stu-id="b133d-158">Computer</span></span>

<span data-ttu-id="b133d-159">ABSConfig은 Lync Server 2013이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="b133d-160">Lync Server 2013, Enterprise Edition의 경우 설치 중에 주소록 서비스가 사용 하도록 설정 된 모든 프런트 엔드 서버에서이 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="b133d-161">네트워크</span><span class="sxs-lookup"><span data-stu-id="b133d-161">Network</span></span>

<span data-ttu-id="b133d-162">컴퓨터가 프런트 엔드 풀 및 백 엔드 데이터베이스에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="b133d-163">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="b133d-163">Software</span></span>

<span data-ttu-id="b133d-164">ABSConfig 도구를 실행 하려면 먼저 다음 소프트웨어 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="b133d-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b133d-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="b133d-166">사용자</span><span class="sxs-lookup"><span data-stu-id="b133d-166">Users</span></span>

<span data-ttu-id="b133d-167">Lync Server 2013 배포를 업데이트 하는 데 필요한 사용 권한이 있는 관리자</span><span class="sxs-lookup"><span data-stu-id="b133d-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-168">예</span><span class="sxs-lookup"><span data-stu-id="b133d-168">Examples</span></span>

<span data-ttu-id="b133d-169">ABSConfig는 명령 프롬프트에 **ABSConfig.exe** 를 입력 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="b133d-170">아래에는 ABSConfig 도구 사용자 인터페이스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="b133d-171">![ABSConfig.exe 도구입니다.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe 도구입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-172">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-172">Summary</span></span>

<span data-ttu-id="b133d-173">관리자는 ABSConfig 도구를 사용 하 여 Lync Server 2013 주소록 서비스를 빠르고 간편 하 게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="b133d-174">대역폭 정책 서비스 모니터</span><span class="sxs-lookup"><span data-stu-id="b133d-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="b133d-175">대역폭 정책 서비스 모니터 도구는 관리자가 다음 목록을 볼 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="b133d-176">토폴로지의 모든 구성 된 Lync Server 2013 대역폭 정책 서비스 (인증 및 코어)</span><span class="sxs-lookup"><span data-stu-id="b133d-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="b133d-177">각 서비스가 다른 대역폭 정책 서비스와에 지 서버에 대해 수행 하는 연결</span><span class="sxs-lookup"><span data-stu-id="b133d-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="b133d-178">네트워크 구성 문서에 구성 된 모든 링크 및 각 대역폭 정책 서비스에서 보고 하는 실시간 대역폭 사용</span><span class="sxs-lookup"><span data-stu-id="b133d-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-179">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-179">Description</span></span>

<span data-ttu-id="b133d-180">대역폭 정책 서비스 모니터 도구는 GUI 기반 응용 프로그램으로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="b133d-181">관리자는 PDPMonUI.exe를 실행 하 여 도구를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="b133d-182">이 도구는 시작 될 때 토폴로지의 대역폭 정책 서비스 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="b133d-183">초기 업데이트가 완료 되 면 창 왼쪽의 창에는 자신이 속한 클러스터 별로 그룹화 된 서비스 목록이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="b133d-184">관리자가 특정 대역폭 정책 서비스를 선택 하면 오른쪽의 창에 해당 특정 서비스에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="b133d-185">또한이 창에는 정보를 표시 하는 두 개의 기본 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="b133d-186">컴퓨터 정보 탭</span><span class="sxs-lookup"><span data-stu-id="b133d-186">Machine Info Tab</span></span>

<span data-ttu-id="b133d-187">**컴퓨터 정보** 탭에는 선택한 대역폭 정책 서비스의 세부 정보 및 선택한 대역폭 정책 서비스에 의해 다른 서비스에 대 한 모든 연결의 목록과 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="b133d-188">토폴로지 정보 탭</span><span class="sxs-lookup"><span data-stu-id="b133d-188">Topology Info Tab</span></span>

<span data-ttu-id="b133d-189">**토폴로지 정보** 탭에는 네트워크 구성 설정에 구성 되어 있는 모든 링크의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="b133d-190">각 링크에 대해 오디오 및 비디오 대역폭 용량이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="b133d-191">또한 현재 사용 되는 대역폭이 Kbps 및 용량에 대 한 백분율로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="b133d-192">이 도구는 색 구분을 사용 하 여 용량과 근접 한 사용률을 갖는 링크를 강조 표시 하므로 관리자가 이러한 링크를 빠르게 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-193">대역폭 정책 서비스 모니터 도구에서 구성 된 대역폭 정책 서비스에 연결할 때 오류가 발생 하면 <STRONG>컴퓨터 정보</STRONG> 및 <STRONG>토폴로지 정보</STRONG> 탭의 정보가 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="b133d-194">그러나이 도구는 처음에는 연결할 수 있지만 이후에는 서비스에 대 한 연결이 끊어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="b133d-195">이러한 경우 관리자에 게 오래 된 정보가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="b133d-196">관리자가 특정 대역폭 정책 서비스에 대해 데이터를 마지막으로 업데이트 한 날짜를 볼 수 있도록 허용 하는 각 탭에 <STRONG>마지막으로 업데이트</STRONG> 된 타임 스탬프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-197">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-197">Output</span></span>

<span data-ttu-id="b133d-198">명령줄 출력은 없습니다. 프로그램 출력은 기본 GUI (그래픽 사용자 인터페이스) 내에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-199">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-199">Purpose</span></span>

<span data-ttu-id="b133d-200">대역폭 정책 서비스 모니터 도구의 목적은 관리자가 토폴로지에 정의 된 각 대역폭 정책 서비스의 상태를 볼 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="b133d-201">또한 관리자는 네트워크 구성 문서에 정의 된 모든 링크에 대 한 실시간 대역폭 사용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-202">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-202">Requirements</span></span>

<span data-ttu-id="b133d-203">Lync Server 토폴로지의 일부인 컴퓨터에서 대역폭 정책 서비스 모니터 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-204">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-204">Summary</span></span>

<span data-ttu-id="b133d-205">대역폭 정책 서비스 모니터 도구는 토폴로지의 모든 대역폭 정책 서비스의 상태를 조사할 수 있도록 관리자에 게 유용한 리소스 이며, 더 중요 한 이유는 네트워크 구성 설정에 정의 된 링크에 대 한 실시간 대역폭 사용률을 얻을 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="b133d-206">대역폭 사용률 분석기</span><span class="sxs-lookup"><span data-stu-id="b133d-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b133d-207">대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크에서 UC 끝점에 의해 다양 한 대역폭 소비 보기에 대 한 보고서를 작성 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="b133d-208">이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획에 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-209">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-209">Description</span></span>

<span data-ttu-id="b133d-210">대역폭 사용률 분석기는 GUI 기반 응용 프로그램으로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="b133d-211">이 도구는 네트워크를 통한 오디오 사용률에 대 한 보고서를 생성 하 고 용량 계획에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="b133d-212">또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-213">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-213">Output</span></span>

<span data-ttu-id="b133d-214">대역폭 사용률 분석기는 시스템에 구성 되어 있는 모든 WAN 링크에 대 한 대역폭 용량 및 오디오 사용률을 그래픽으로 플롯 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-215">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-215">Purpose</span></span>

<span data-ttu-id="b133d-216">음성 및 비디오 배포에서는 엔터프라이즈 네트워크 전체에서의 대역폭 사용률 추세를 모니터링 하 고 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="b133d-217">대역폭 사용률 분석기 도구를 사용 하면 관리자가 해당 항목만 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="b133d-218">이 도구는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-218">This tool does the following:</span></span>

  - <span data-ttu-id="b133d-219">네트워크를 통한 오디오 사용률에 대 한 특정 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="b133d-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="b133d-220">다양 한 링크에 할당 된 대역폭 용량에 대 한 보다 효율적인 용량 계획 및 반복을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="b133d-221">대역폭 사용률 분석기는 대역폭 용량 및 사용률 보고서의 그래픽 플롯을 생성할 수 있습니다. 이러한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="b133d-222">엔터프라이즈 네트워크의 모든 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="b133d-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="b133d-223">선택한 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="b133d-224">연결 용량을 초과한 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="b133d-225">프로 비전 된 대역폭을 이용 하 여 온 WAN 링크로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="b133d-226">중요 한 수준에 도달한 WAN 링크로 필터링 (WAN 링크의 대역폭 용량을 90% 초과 하는 대역폭 사용률)</span><span class="sxs-lookup"><span data-stu-id="b133d-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="b133d-227">WAN 링크 유형 (네트워크-사이트 링크, 인터 지역별 링크 및 사이트 내의 링크)을 기준으로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="b133d-228">네트워크 지역별로 필터링 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="b133d-229">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b133d-229">Applications</span></span>

<span data-ttu-id="b133d-230">대역폭 사용률 분석기에는 다음과 같은 두 가지 응용 프로그램 (도구)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="b133d-231">**WanLinkLogCollector.exe**     이 도구를 사용 하면 사용자가 필요한 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="b133d-232">**BandwidthUtilizationAnalyzer.xlsm**    Microsoft Excel 스프레드시트 소프트웨어 보고서는 WanLinkLogCollector.exe에 의해 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="b133d-233">이 응용 프로그램을 통해 사용자는이 문서 뒷부분에 나와 있는 것 처럼 보고서에 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="b133d-234">대역폭 사용률 분석기 사용 단계</span><span class="sxs-lookup"><span data-stu-id="b133d-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b133d-235">대역폭 사용률 분석기를 사용 하는 경우 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="b133d-236">WanLinkLogCollector.exe를 사용 하 여 수행 되는 로그 수집</span><span class="sxs-lookup"><span data-stu-id="b133d-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="b133d-237">BandwidthUtilizationAnalyzer.xlsm을 사용 하 여 수행 하는 보고서 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b133d-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b133d-238">최종 사용자가 수동으로 m BandwidthUtilizationAnalyzer.xls를 시작 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="b133d-239">대역폭 사용률 분석기 시작</span><span class="sxs-lookup"><span data-stu-id="b133d-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b133d-240">명령 프롬프트 또는 Windows 탐색기를 사용 하 여 WanLinkLogCollector.exe을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="b133d-241">\*\*WanLinkLogCollector.exe사용 \*\*</span><span class="sxs-lookup"><span data-stu-id="b133d-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="b133d-242">WanLinkLogCollector.exe를 사용 하는 세 가지 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="b133d-243">**시간 표시 막대 기록**     보고서를 생성 해야 하는 시간 표시 막대를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="b133d-244">**파일 디렉터리 지정**     파일 위치 정보 제공</span><span class="sxs-lookup"><span data-stu-id="b133d-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="b133d-245">**로그 수집 및 보고서 뷰어 실행**    보고서를 생성 하는 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="b133d-246">1 단계-시간 표시 막대 기록</span><span class="sxs-lookup"><span data-stu-id="b133d-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="b133d-247">시간 표시줄 로깅을 사용 하면 도구 사용자가 아래 그림에 나와 있는 것 처럼 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="b133d-248">**시작 날짜** 보고서를 생성할 시간 표시 막대의 시작 날짜입니다. 예를 들어, 2010 년 8 월 1 일</span><span class="sxs-lookup"><span data-stu-id="b133d-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="b133d-249">**종료 날짜** 보고서를 생성할 시간 표시 막대의 종료 날짜 이며, 예를 들어, 2010 년 9 월 30 일을 예로 들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="b133d-250">![대역폭 사용률 A의 시작 및 종료 날짜](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "대역폭 사용률 A의 시작 및 종료 날짜")</span><span class="sxs-lookup"><span data-stu-id="b133d-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="b133d-251">2 단계-파일 디렉터리 지정</span><span class="sxs-lookup"><span data-stu-id="b133d-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="b133d-252">표시 된 대로 사용자가 다음 파일 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="b133d-253">**서버 로그 파일 위치** 대역폭 정책 서버 로그가 저장 되는 폴더 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="b133d-254">이는 일반적으로 \<fileserver\> \\ \<choice of FE\> \\ appserverfiles \\ PDP에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="b133d-255">**임시 파일 저장 위치** 보고서를 생성 하는 동안 중간 파일이 저장 되는 임시 파일 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="b133d-256">![대역폭 사용률의 파일 디렉터리](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "대역폭 사용률의 파일 디렉터리")</span><span class="sxs-lookup"><span data-stu-id="b133d-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-257">서버 로그 및 임시 파일 저장소 폴더에 대 한 충분 한 파일 액세스 권한이 도구 사용자에 게 제공 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="b133d-258">3 단계-로그를 수집 하 고 보고서 뷰어를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="b133d-259">로그를 수집 하 고 보고서 뷰어를 시작 하려면 아래 표시 된 대로 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="b133d-260">이 단계에서는 필요한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-260">This step collects the required data.</span></span>

<span data-ttu-id="b133d-261">![대역폭 사용률 Utilization에서 데이터 수집](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "대역폭 사용률 Utilization에서 데이터 수집")</span><span class="sxs-lookup"><span data-stu-id="b133d-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="b133d-262">입력 유효성 검사가 성공적으로 완료 되 면 아래 표시 된 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="b133d-263">![Utili 대역폭에서 수집 된 알림을 기록 합니다.](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Utili 대역폭에서 수집 된 알림을 기록 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="b133d-264">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-264">Click **OK**.</span></span> <span data-ttu-id="b133d-265">BandwidthUtilizationAnalyzer.xlsm이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="b133d-266">메시지 상자의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="b133d-267">자세한 내용은 다음 섹션에서 **BandwidthUtilizationAnalyzer.xlsm 사용** 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b133d-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="b133d-268">**BandwidthUtilizationAnalyzer.xlsm 사용**</span><span class="sxs-lookup"><span data-stu-id="b133d-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="b133d-269">BandwidthUtilizationAnalyzer.xlsm이 자동으로 시작 되 면 아래 표시 된 대로 **새로 고침** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="b133d-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="b133d-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="b133d-271">파일 폴더가 열리면 아래와 같이 메시지 상자에 지정 된 위치에서 consolidated.csv를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="b133d-272">또한 **C: \\ Temp**로 위치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="b133d-273">![BandwidthUtilizationAnalyzer에서 폴더 열기](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "BandwidthUtilizationAnalyzer에서 폴더 열기")</span><span class="sxs-lookup"><span data-stu-id="b133d-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="b133d-274">**가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-274">Click **Import**.</span></span>

4.  <span data-ttu-id="b133d-275">그래픽 플롯이 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="b133d-276">배경 작업 포인터가 사라지면 서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="b133d-277">![보고서 보기에 필터를 적용 합니다.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "보고서 보기에 필터를 적용 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="b133d-278">보고서 보기에 필터 적용</span><span class="sxs-lookup"><span data-stu-id="b133d-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="b133d-279">아래에 표시 된 것 처럼 보고서 보기에 적용할 수 있는 필터는 다음과 같이 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="b133d-280">![보고서 보기에 필터를 적용 합니다.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "보고서 보기에 필터를 적용 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="b133d-281">**이름** WAN 링크로 필터링 (그래프 오른쪽에 필터가 있습니다.) 접두사는 다음 링크 형식을 나타냅니다. 세로 (파란색) 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="b133d-282">**S 사이트** 네트워크 사이트에서 네트워크 지역으로의 WAN 연결</span><span class="sxs-lookup"><span data-stu-id="b133d-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="b133d-283">**사이트 간** 두 네트워크 사이트 간의 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="b133d-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="b133d-284">**R 지역 간** 두 네트워크 지역 간의 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="b133d-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="b133d-285">**제한 초과** 대역폭 사용량이 대역폭 용량 보다 많은 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="b133d-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="b133d-286">**중요 수준** 대역폭 사용률이 대역폭 용량 보다 90% 이상에 도달 했을 때의 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="b133d-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="b133d-287">**미달 사용** 대역폭 사용률이 대역폭 용량의 25% 미만인 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="b133d-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="b133d-288">**연결 유형** 다음 WAN 링크 유형으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="b133d-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="b133d-289">**네트워크 사이트** 유형</span><span class="sxs-lookup"><span data-stu-id="b133d-289">**Network site** type</span></span>
    
      - <span data-ttu-id="b133d-290">**사이트 간** 유형</span><span class="sxs-lookup"><span data-stu-id="b133d-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="b133d-291">**지역 간 링크** 형식</span><span class="sxs-lookup"><span data-stu-id="b133d-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="b133d-292">**지역** 네트워크 지역별로 필터링</span><span class="sxs-lookup"><span data-stu-id="b133d-292">**Region** Filter by network region</span></span>

<span data-ttu-id="b133d-293">다음 그림에서는 앞에서 설명한 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="b133d-294">**이름을**기준으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-294">Filter by **Name**.</span></span> <span data-ttu-id="b133d-295">그래프에 표시 해야 하는 링크 목록을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="b133d-296">![BandwidthUtilizationAnalyzer에서 이름을 기준으로 필터링 합니다.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "BandwidthUtilizationAnalyzer에서 이름을 기준으로 필터링 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="b133d-297">**제한을 초과**하 여 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="b133d-298">**True** 를 선택 하 여 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b133d-299">![제한을 초과한 필터링](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "제한을 초과한 필터링")</span><span class="sxs-lookup"><span data-stu-id="b133d-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="b133d-300">**중요 수준**으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="b133d-301">**True** 를 선택 하 여 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b133d-302">![중요 수준별로 필터링](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "중요 수준별로 필터링")</span><span class="sxs-lookup"><span data-stu-id="b133d-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="b133d-303">**과소**사용으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="b133d-304">**True** 를 선택 하 여 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b133d-305">![과소 사용을 기준으로 필터링](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "과소 사용을 기준으로 필터링")</span><span class="sxs-lookup"><span data-stu-id="b133d-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="b133d-306">**링크 형식**으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-306">Filter by **Link Type**.</span></span> <span data-ttu-id="b133d-307">표시 해야 하는 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="b133d-308">![링크 형식별 필터링](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "링크 형식별 필터링")</span><span class="sxs-lookup"><span data-stu-id="b133d-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="b133d-309">**지역별로**필터링</span><span class="sxs-lookup"><span data-stu-id="b133d-309">Filter by **Region**.</span></span> <span data-ttu-id="b133d-310">링크를 표시 해야 하는 지역 목록을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="b133d-311">![지역별 필터링](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "지역별 필터링")</span><span class="sxs-lookup"><span data-stu-id="b133d-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-312">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-312">Requirements</span></span>

  - <span data-ttu-id="b133d-313">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="b133d-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="b133d-314">Microsoft Excel 2010 또는 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="b133d-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-315">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-315">Summary</span></span>

<span data-ttu-id="b133d-316">대역폭 사용률 분석기는 네트워크를 통해 UC 트래픽에 대 한 오디오 대역폭 사용률을 그리는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="b133d-317">이 도구는 네트워크의 비디오 대역폭 사용률을 보고 하는 데에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="b133d-318">통화 Parkometer</span><span class="sxs-lookup"><span data-stu-id="b133d-318">Call Parkometer</span></span>

<span data-ttu-id="b133d-319">Call Parkometer는 통화 대기 궤도 데이터베이스에 쉽게 액세스할 수 있게 해 주는 명령줄 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-320">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-320">Description</span></span>

<span data-ttu-id="b133d-321">Call Parkometer는 현재 대기 중인 통화를 추적 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="b133d-322">또한 궤도 및 CPS (통화 대기 서버) 사용에 대 한 통계를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="b133d-323">이 명령줄 도구는 로컬 또는 원격으로 연결 된 컴퓨터에서 CPS 궤도 SQL Server 데이터베이스에 대 한 읽기 및 쓰기 액세스를 모두 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="b133d-324">모든 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-324">All options are mutually exclusive.</span></span> <span data-ttu-id="b133d-325">명령줄 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="b133d-326">**-o** parameter-이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="b133d-327">**– n** 매개 변수-이 풀에서 현재 사용 되는 모든 궤도를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="b133d-328">표시 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="b133d-329">Parkee 및 parker의 SIP URI (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="b133d-330">통화가 대기 중인 CPS의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="b133d-331">통화가 대기 되었을 때의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="b133d-332">**– f** 매개 변수-풀에서 현재 사용 가능한 궤도의 수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="b133d-333">\*\*– r \<n\> \*\* parameter-마지막으로 대기 된 통화를 나열 합니다 \<n\> .</span><span class="sxs-lookup"><span data-stu-id="b133d-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="b133d-334">표시 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="b133d-335">Parkee SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="b133d-336">Parker SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="b133d-337">통화가 파킹 된 CPS의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="b133d-338">통화를 검색 하거나 삭제할 때의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="b133d-339">\*\*-t \<n\> \*\* parameter-지정 된 궤도 번호의 임의성을 표시 하기 위해 데이터베이스의 궤도를 예약 하는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-340">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-340">Output</span></span>

<span data-ttu-id="b133d-341">명령 프롬프트에서 지정한 입력 매개 변수에 따라 Call Parkometer에는 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="b133d-342">이 풀에 대해 구성 된 모든 궤도 범위</span><span class="sxs-lookup"><span data-stu-id="b133d-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="b133d-343">현재 대기 중인 통화</span><span class="sxs-lookup"><span data-stu-id="b133d-343">Currently parked calls</span></span>

  - <span data-ttu-id="b133d-344">사용할 수 있는 사용 가능한 공간 (사용 가능) 궤도</span><span class="sxs-lookup"><span data-stu-id="b133d-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="b133d-345">최근 대기 통화</span><span class="sxs-lookup"><span data-stu-id="b133d-345">Recently parked calls</span></span>

  - <span data-ttu-id="b133d-346">Uniform 및 random 궤도 값을 테스트 하기 위해 예약 된 궤도</span><span class="sxs-lookup"><span data-stu-id="b133d-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-347">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-347">Purpose</span></span>

<span data-ttu-id="b133d-348">CPS 도구의 용도는 CPS 데이터베이스에 대 한 명령줄 액세스를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="b133d-349">관리자는 CPS 사용량을 확인 하 고 풀에 할당 된 궤도 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-350">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-350">Requirements</span></span>

<span data-ttu-id="b133d-351">CPS를 실행 하는 동일한 컴퓨터에서이 도구를 실행 하는 경우에는 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="b133d-352">원격 컴퓨터에서이 도구를 실행 하는 경우 Lync Server 2013에서 사용 하는 SQL Server 데이터베이스를 원격 액세스를 허용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="b133d-353">풀의 SQL Server에 연결 하려면 Call Parkometer를 SQL Server 데이터베이스 연결 문자열로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="b133d-354">이 SQL Server 데이터베이스 연결 문자열은 구성 파일 **parkometer.exe.config**에 정의 되어 있습니다. parkometer.exe가 있는 디렉터리에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="b133d-355">다음 XML 파일은 parkometer.exe.config의 예입니다. 구성 해야 하는 매개 변수는 사용자 이름 (예: mydomain \\ 관리자), 암호 (예: mypassword) 및 호스트 이름 (예: myserver)입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-356">예</span><span class="sxs-lookup"><span data-stu-id="b133d-356">Examples</span></span>

<span data-ttu-id="b133d-357">배포한 궤도 범위:-o 매개 변수는 표시 된 것 처럼이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="b133d-358">![통화 Parkometer의 궤도 범위입니다.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "통화 Parkometer의 궤도 범위입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="b133d-359">현재 대기 중인 통화:-n 매개 변수는이 풀에서 현재 사용 되는 모든 궤도를 표시 된 대로 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="b133d-360">![통화 Parkometer에서 현재 대기 중인 통화입니다.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "통화 Parkometer에서 현재 대기 중인 통화입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="b133d-361">Free 궤도의 수: – f 매개 변수는 다음과 같이 풀에 현재 사용 가능한 궤도 수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="b133d-362">![통화 Parkometer의 무료 궤도입니다.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "통화 Parkometer의 무료 궤도입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="b133d-363">최근에 대기 된 통화:-r \<n\> 매개 변수는 표시 된 마지막 대기 통화를 나열 합니다. \<n\></span><span class="sxs-lookup"><span data-stu-id="b133d-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="b133d-364">![통화 Parkometer의 최근에 파킹 된 통화입니다.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "통화 Parkometer의 최근에 파킹 된 통화입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="b133d-365">Test 궤도 예약: – t \<n\> 매개 변수 테스트에서는 다음과 같이 데이터베이스의 궤도를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="b133d-366">![통화 Parkometer에서 궤도 예약을 테스트 합니다.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "통화 Parkometer에서 궤도 예약을 테스트 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-367">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-367">Summary</span></span>

<span data-ttu-id="b133d-368">Call Parkometer는 통화 대기 서버에 대 한 자세한 정보를 제공 하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="b133d-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b133d-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="b133d-370">CleanupStorageServiceData resource kit 도구를 사용 하면 Lync Server 저장소 서비스 (LYSS)에서 사용 하는 데이터베이스에서 분리 된 데이터를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="b133d-371">저장소 서비스의 한 가지 기능은 SQL Server 및 Exchange와 같은 다양 한 백 엔드 데이터 저장소 끝점과 Lync Server 간의 통신을 버퍼링 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-372">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-372">Description</span></span>

<span data-ttu-id="b133d-373">높은 가용성을 지원 하기 위해 LYSS는 풀의 여러 프런트 엔드 서버에 있는 데이터의 복사본을 일시적으로 수락 및 저장 하 고, 해당 데이터를 최종 장기 저장소 위치로 배달 한 후에 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="b133d-374">정상적인 작동 중에 발생할 수 있는 비정상적인 상황이 발생 하 고, 서버에 충돌이 있거나, 처리 문제가 발생할 수 있으며, 일부 데이터가 제대로 정리 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="b133d-375">이 데이터는 무해 하지만 제한 된 처리 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="b133d-376">대부분의 일반 필수 데이터 유지 관리가 자동화 되지만이 도구를 사용 하면 자동화 된 제거를 수행할 수 없는 경우 이러한 고아 데이터를 안전 하 게 식별 하 고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="b133d-377">이 도구의 사용은 관리자가 풀의 로컬 LYSS 데이터베이스에서 불필요 한 데이터를 제거 하도록 요청 하는 SCOM (System Center Operations Manager) 경고가 발생 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="b133d-378">경고를 트리거한 프런트 엔드에서 이벤트 로그에 해당 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="b133d-379">이벤트 세부 정보에는 프런트 엔드에 포함 된 분리 된 데이터의 양에 대 한 정보가 포함 되며 해당 데이터가 미리 결정 된 특정 임계값을 초과 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-380">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-380">Requirements</span></span>

<span data-ttu-id="b133d-381">Lync Server 2013, 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b133d-382">이 도구는 Lync Server 및 Lync Server 2013 관리 셸이 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="b133d-383">이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="b133d-384">그런 다음 **RtcLocal** 데이터베이스가 설치 된 풀의 컴퓨터에서 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="b133d-385">이 데이터베이스는 CleanupStorageServiceData 도구에서 Lync Server 라우팅 서비스와 통신 하는 데 필요한 연결 세부 정보를 가져오는 데 사용 됩니다. 마지막으로 도구를 호출 하는 계정 또는 자격 증명에는 출력 로그를 쓸 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 또한이 도구는 풀이 안정적인 상태임을 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="b133d-386">즉, 모든 프런트 엔드 서버가 가동 되 고 실행 중 이어야 하 고 SQL Server LYNCLOCAL instance 및 LYSS 데이터베이스를 연결할 수 있어야 하며 각 라우팅 그룹에는 1 개의 기본 프런트 엔드 서버와 2 개의 보조 프런트 엔드 서버가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-387">예</span><span class="sxs-lookup"><span data-stu-id="b133d-387">Examples</span></span>

<span data-ttu-id="b133d-388">C: \\ 프로그램 파일 \\ Microsoft Lync Server 2013 \\ ResKit \\ StorageService \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="b133d-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="b133d-389">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="b133d-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-390">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-390">Description</span></span>

<span data-ttu-id="b133d-391">DBAnalyze는 관리자가 Lync Server 2013 데이터베이스에 대 한 분석 보고서를 수집할 수 있도록 하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="b133d-392">DBAnalyze에는 진단, 사용자 데이터, 회의, MCUs 및 디스크 조각화 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="b133d-393">**진단 모드**     테이블 (레코드 수, 조각, 데이터 크기 및 인덱스 크기)에 대 한 정보를 포함 하는 보고서를 만듭니다. 데이터 및 로그 파일 크기, 최근 백업 시간, 마지막 다시 실행 시간은 Microsoft Office Communications Server, 사용자 당 평균 사용 권한, 연락처, 컨테이너, 구독, 게시, 사용자별 끝점, 모든 부적절 한 홈 사용자, 사용자에 게 구성 된 최대 전화 회의 수, 예약 된 전화 회의, 활성 회의 및 데이터베이스 버전 등이 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-394">진단 모드 실행은 서버 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="b133d-395">**사용자 데이터 모드**   지정 된 사용자 또는 해당 사용자가 대화 상대 및 사용 권한 목록에 있는 사용자에 대 한 연락처, 컨테이너, 구독, 게시, 사용 권한 및 연락처 그룹 데이터를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="b133d-396">또한이 모드는 사용자가 구성 하거나 초대 하는 전화 회의에 대 한 요약 데이터를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="b133d-397">**전화 회의 모드**     회의에 대 한 모든 일정 시간 정보, 초대 대 상자, 회의에 허용 되는 미디어 유형 목록, 활성 참가자 목록 및 각 참가자의 신호 상태를 비롯 하 여 특정 회의에 대 한 자세한 데이터를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="b133d-398">**디코드 모임 ID**    **/Pstnid** 스위치로 지정 되는 공중 전화망 (PSTN) 모임 ID를 디코딩하고 자세한 정보는 백 엔드에 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="b133d-399">**전화 회의**     문제 해결 **/Pstnid** 스위치에 지정 된 PSTN 모임 id를 디코딩하고 ID가 나타내는 전화 회의에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="b133d-400">**MCUs 모드**    풀의 각 MCU에 대 한 ID, 미디어 유형, URL, 하트 비트 상태, 회의 부하 및 참가자 부하를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="b133d-401">**디스크 조각화 모드**    모든 디스크의 조각화 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="b133d-402">이 도구를 사용 하 여 다양 한 문제를 진단 하거나 관리자가 용량 계획을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="b133d-403">예를 들어 서버 A에 있는 대부분의 사용자가 자신의 연락처로 서버 B에 있는 사용자를 선택 하는 경우 관리자는 서버 A의 사용자를 서버 B로 이동 하 여 서버 간 트래픽을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-404">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-404">Output</span></span>

<span data-ttu-id="b133d-405">이 도구는 Lync Server 2013 데이터베이스에 대 한 미리 정의 된 보고서를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="b133d-406">**경로:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Reskit</span><span class="sxs-lookup"><span data-stu-id="b133d-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-407">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-407">Purpose</span></span>

<span data-ttu-id="b133d-408">Dbanalyze.exe을 설치 하려면 해당 파일을 로컬 폴더에 복사한 다음 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="b133d-409">이 도구를 사용 하려면 명령줄에서 다음 명령을 실행 합니다.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="b133d-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="b133d-410">명령줄 옵션에 대 한 설명은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="b133d-411">![Dbanalyze.exe에 대 한 명령줄 옵션입니다.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe에 대 한 명령줄 옵션입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-412">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-412">Requirements</span></span>

<span data-ttu-id="b133d-413">**컴퓨터** DBAnalyze는 Lync Server 2013이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="b133d-414">**네트워크** 컴퓨터에서 백 엔드 데이터베이스에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="b133d-415">**소프트웨어** DBAnalyze를 실행 하기 전에 Lync Server 2013 소프트웨어 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="b133d-416">**사용자** 아래 표에는 Lync Server 2013 데이터베이스에 액세스 하는 데 필요한 권한이 있는 관리자가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="b133d-417">![Dbanalyze.exe에 대 한 사용 권한 테이블입니다.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe에 대 한 사용 권한 테이블입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-418"><STRONG>/Preport: 디스크</STRONG> 모드에는 로컬 관리자 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-419">예</span><span class="sxs-lookup"><span data-stu-id="b133d-419">Examples</span></span>

<span data-ttu-id="b133d-420">다음은 유효한 Dbanalyze.exe 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-421">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-421">Summary</span></span>

<span data-ttu-id="b133d-422">DBAnalyzer는 관리자에 게 Lync Server 2013 데이터베이스를 빠르고 쉽게 분석할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="b133d-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b133d-423">ImportStorageServiceData</span></span>

<span data-ttu-id="b133d-424">ImportStorageServiceData resource kit 도구를 사용 하면 저장소 서비스 (LYSS)에서 플러시된 큐 및 끝점 데이터를 저장소 서비스로 다시 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-425">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-425">Description</span></span>

<span data-ttu-id="b133d-426">저장소 서비스에서 플러시된 데이터는 큐 항목 상태 또는 데이터베이스 크기에 따라 자동 (주기적)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="b133d-427">이 문제는 풀 장애 조치 (failover) cmdlet 또는 풀 장애 조치 (failover) cmdlet이 호출 하는 StorageServiceFullFlush cmdlet의 수동 호출로 인해 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="b133d-428">프런트 엔드에서 저장소 서비스 (LYSS) 데이터베이스 크기가 일반 수준 위에 있는 경우에는 데이터를 다시 가져올 필요가 없기 때문에이 작업을 수행 하면 더 많은 데이터를 다시 내보낼 수 있습니다. 또한 저장소 서비스 큐 증가를 일으킨 오류에 대 한 영향을 받을 수 있는 모든 문제 (예: Exchange 끝점 오류, 네트워크 문제 또는 기타 문제)를 먼저 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="b133d-429">**시나리오 1:** 풀 장애 조치 (failover) 중에 각 프런트 엔드에서 파일을 저장소 서비스에서 플러시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="b133d-430">장애 조치 (failover)가 완료 되 면 도구를 실행 하 여 데이터를 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="b133d-431">**시나리오 2:** 데이터를 매일 자동으로 플러시 중이거나 저장소 서비스 데이터베이스에 대 한 응답으로 특정 크기 임계값 (예: 60%, 80%, 90% full)을 초과 하는 경우</span><span class="sxs-lookup"><span data-stu-id="b133d-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="b133d-432">자동으로 플러시된 데이터는 관리자가 정기적으로 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="b133d-433">위의 상황에서 모니터링 SCOM pack이 배포 되지 않은 경우 저장소 서비스에서 플러시하는 데이터와 관련 된 Lync Server 저장소 서비스에 대 한 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="b133d-434">이벤트 Id 32075 (전체 플러시 작업을 시작 함), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작), 32083 (, 유지 관리 수준 플러시 완료), 32089 (데이터베이스를 채우는 중에 플러시 발생)</span><span class="sxs-lookup"><span data-stu-id="b133d-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="b133d-435">참고 이러한 이벤트 Id는 RTM 릴리스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="b133d-436">관리자에 게 이러한 이벤트가 표시 되 면 플러시 된 파일이 있음을 의미 합니다. 이 도구를 사용 하 여이 데이터를 정기적으로 다시 가져와야 합니다 (예: 일주일에 한 번).</span><span class="sxs-lookup"><span data-stu-id="b133d-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="b133d-437">온라인 서비스 릴리스의 경우 Lync Server에 대 한 상태 모니터링 SCOM pack이 배포 되는 경우 관리자에 게 플러시된 데이터를 다시 저장소 서비스에 재 가져오도록 요청 하는 새로운 경고가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="b133d-438">프런트 엔드 서버의 이벤트 로그에 경고를 트리거한 해당 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="b133d-439">이 이벤트는 플러시된 데이터 파일이 있는 상위 경로에 대 한 설명과, 경고 조건을 충족 하는 파일 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="b133d-440">경고 기준은 특정 상위 경로 아래에 Y 일이 지난 파일 (X 및 Y는 StorageService 내에서 사전 설정 되지만 APPCONFIG 파일을 변경 하 여 재정의할 수 있음)이 포함 되어 있다는 것입니다. 상태 경고를 트리거할 수 있는 이벤트의 두 가지 예는 다음과 같습니다 (상위 경로).</span><span class="sxs-lookup"><span data-stu-id="b133d-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="b133d-441">웹 서비스 파일 공유 아래에는 각 프런트 엔드의 로컬 응용 프로그램 데이터 디렉터리인 한 가지 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="b133d-442">예를 들면 c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService).</span><span class="sxs-lookup"><span data-stu-id="b133d-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="b133d-443">그러면 관리자가이 reskit 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="b133d-444">이 도구는 도구를 실행 하는 프런트 엔드에서 데이터를 소유 하지 않는 경우에도 실행 중인 프런트 엔드에서 CPU 및 IO 부하를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="b133d-445">프런트 엔드의 CPU 및 IO 부하가 많지 않은 경우 (예: 사용량이 가장 많은 시간 외에)이 도구를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="b133d-446">그런 다음이 도구는 데이터 파일 하나를 가져오는 데 2 ~ 3 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="b133d-447">도구 실행 시간을 추정할 때이 점에 유의 하세요. 도구에서 생성 되는 자세한 로그 파일은 기본적으로 파일 저장소에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="b133d-448">로그 파일의 크기가 수십 개이 하 이므로 오류가 보고 되지 않은 경우 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="b133d-449">![예제 저장소 서버 이벤트 로그 이벤트](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "예제 저장소 서버 이벤트 로그 이벤트")</span><span class="sxs-lookup"><span data-stu-id="b133d-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-450">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-450">Requirements</span></span>

<span data-ttu-id="b133d-451">Lync Server 2013, 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b133d-452">이 도구는 Lync Server 및 Lync Server 관리 셸이 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="b133d-453">이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="b133d-454">그런 다음 **RtcLocal** 데이터베이스가 설치 된 풀의 컴퓨터에서 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="b133d-455">이 데이터베이스는 도구에서 풀에 대 한 WEBSERVICE 파일 공유 위치를 검색 하는 데 사용 됩니다. 또한이 도구를 사용 하기 전에 각 프런트 엔드 서버에서 먼저 각 프런트 엔드 서버에서 **enable-psremoting** 를 사용 하 여 Windows PowerShell Remoting을 사용 하도록 설정 해야 하며,이 도구를 실행 하는 컴퓨터도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="b133d-456">그렇지 않은 경우에는이 도구의 원격 Windows PowerShell 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="b133d-457">풀에 있는 모든 프런트 엔드 서버를 완료 한 후에는 Windows PowerShell Remoting을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="b133d-458">마지막으로 도구를 호출 하는 계정 또는 자격 증명에는이 도구를 실행 하는 풀에 대 한 webservice 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="b133d-459">그렇지 않으면 도구에서 IO 권한 오류가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-460">Windows Server 2012에서는 windows PowerShell Remoting이 기본적으로 사용 하도록 설정 되어 있지만 Windows Server 2008 운영 체제에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-461">예</span><span class="sxs-lookup"><span data-stu-id="b133d-461">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="b133d-462">Lcssync.dll</span><span class="sxs-lookup"><span data-stu-id="b133d-462">LCSSync</span></span>

<span data-ttu-id="b133d-463">LCSSync 도구는 다중 포리스트 환경에서 Lync Server 2013 통신 소프트웨어를 배포 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="b133d-464">이 도구는 다른 사용자 포리스트에서 사용자 및 그룹을 Active Directory 도메인 서비스 연락처 개체로, Lync Server 2013이 설치 된 중앙 포리스트로 동기화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-465">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-465">Description</span></span>

<span data-ttu-id="b133d-466">LCSSync는 중앙 포리스트에서 동기화 된 Active Directory 도메인 서비스 대화 상대 개체를 사용 하 여 사용자가 Lync Server를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="b133d-467">Single sign-on을 제공 하려면 기본 사용자 계정을 Lync Server 2013에 대 한 중앙 포리스트의 Active Directory 도메인 서비스 대화 상대 개체에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="b133d-468">이 도구는 해당 매핑을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="b133d-469">이 도구는 Microsoft Identity 통합 서버에서 관리 에이전트를 만들기 위한 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-470">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-470">Summary</span></span>

<span data-ttu-id="b133d-471">LCSSync 도구는 다중 포리스트 환경에서 Lync Server를 배포 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="b133d-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="b133d-472">LookupUserConsole</span></span>

<span data-ttu-id="b133d-473">LookupUserConsole 도구는 특정 사용자에 대 한 내부 Lync Server 라우팅 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="b133d-474">이 정보는 Microsoft에서 배포 및 라우팅 문제를 진단 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-475">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-475">Description</span></span>

<span data-ttu-id="b133d-476">LookupUserConsole.exe를 실행 하면 SIP 주소를 허용 하 고 해당 항목과 관련 된 내부 Lync Server 라우팅 정보를 표시 하려고 하는 명령 프롬프트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="b133d-477">**Exit** 를 입력 하 여 LookupUserConsole 도구를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-478">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-478">Requirements</span></span>

<span data-ttu-id="b133d-479">Lync Server 2013, 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b133d-480">이 도구는 Lync Server가 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-481">예</span><span class="sxs-lookup"><span data-stu-id="b133d-481">Examples</span></span>

<span data-ttu-id="b133d-482">C: \\ 프로그램 파일 \\ Microsoft Lync Server 2013 \\ ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="b133d-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="b133d-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b133d-483">MsTurnPing</span></span>

<span data-ttu-id="b133d-484">Microsoft Lync Server 2013 통신 소프트웨어 관리자는 MSTurnPing 도구를 사용 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버 뿐만 아니라 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-485">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-485">Description</span></span>

<span data-ttu-id="b133d-486">MSTurnPing 도구를 사용 하면 Lync Server 2013 통신 소프트웨어 관리자가 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버 뿐만 아니라 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="b133d-487">이 도구를 사용 하면 관리자가 다음과 같은 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="b133d-488">A/V에 지 서버 테스트:이 도구는 다음을 수행 하 여 토폴로지의 모든 A/V에 지 서버에 대해 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="b133d-489">Lync Server 오디오/비디오 인증 서비스가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="b133d-490">Lync Server 오디오/비디오에 지 서비스가 시작 되었는지 확인 하 고 리소스를 외부에 지에 성공적으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="b133d-491">대역폭 정책 서비스 테스트: 도구는 다음을 수행 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 모든 서버에 대해 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="b133d-492">Lync Server 대역폭 정책 서비스 (인증)가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="b133d-493">Lync Server Core (대역폭 정책 서비스)가 시작 되었으며 대역폭 확인을 정상적으로 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="b133d-494">토폴로지의 일부인 컴퓨터에서이 도구를 실행 하 고 로컬 저장소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-495">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-495">Output</span></span>

<span data-ttu-id="b133d-496">이 도구는 각 작업의 결과를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="b133d-497">**AudioVideoEdgeServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="b133d-498">토폴로지에서 Lync Server 오디오/비디오 인증 서비스를 제공 하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="b133d-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="b133d-499">토폴로지에서 Lync Server 오디오/비디오에 지 서비스를 제공 하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="b133d-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="b133d-500">**BandwidthPolicyServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="b133d-501">토폴로지에서 Lync Server 대역폭 정책 서비스 (인증)를 제공 하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="b133d-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="b133d-502">토폴로지에서 Lync Server Core (대역폭 정책 서비스)를 제공 하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="b133d-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-503">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-503">Requirements</span></span>

  - <span data-ttu-id="b133d-504">이 도구는 토폴로지에 있고 로컬 저장소가 있는 컴퓨터에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="b133d-505">이 도구는 로컬 저장소에 대 한 액세스 권한이 있는 관리자 권한으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-506">예</span><span class="sxs-lookup"><span data-stu-id="b133d-506">Examples</span></span>

<span data-ttu-id="b133d-507">다음은 도구 입력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-508">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-508">Summary</span></span>

<span data-ttu-id="b133d-509">이 도구는 오디오/비디오 및 대역폭 정책 서비스를 실행 하는 서버의 상태를 확인 하려는 Lync Server 2013 관리자에 게 유용한 리소스 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="b133d-510">네트워크 구성 뷰어</span><span class="sxs-lookup"><span data-stu-id="b133d-510">Network Configuration Viewer</span></span>

<span data-ttu-id="b133d-511">Microsoft Lync Server 2013 통신 소프트웨어 관리자는 네트워크 구성 뷰어를 사용 하 여 지정 된 대역폭 용량에 따라 음성 또는 비디오 통화와 같은 실시간 통신 세션을 허용 하도록 프로 비전 된 엔터프라이즈에 대 한 CAC (통화 허용 제어) 네트워크 토폴로지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="b133d-512">Lync Server 2013 관리자는 Lync Server 2013와 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-513">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-513">Description</span></span>

<span data-ttu-id="b133d-514">NetworkConfigurationViewer.exe (Network Configuration Viewer)에서는 관리자가 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="b133d-515">Lync Server 2013 배포에서 CAC 네트워크 토폴로지를 그래픽 형식으로 로드 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="b133d-516">CAC 네트워크 토폴로지를 그래픽 형식으로 대역폭 정책 서버 로그 파일에서 로드 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="b133d-517">CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="b133d-518">CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="b133d-519">CAC 네트워크 토폴로지 구성 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="b133d-520">트리 보기 스타일로 CAC 네트워크 토폴로지를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="b133d-521">CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="b133d-522">CAC 네트워크 토폴로지 사이트 정보, 지역 정보, 프로 비전 된 대역폭 정책 및 네트워크 링크 보기</span><span class="sxs-lookup"><span data-stu-id="b133d-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-523">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-523">Purpose</span></span>

<span data-ttu-id="b133d-524">그래픽 인터페이스에서 엔터프라이즈 CAC 네트워크 토폴로지 링크를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-525">예</span><span class="sxs-lookup"><span data-stu-id="b133d-525">Examples</span></span>

<span data-ttu-id="b133d-526">**다음은 Lync Server 2013 배포에서 CAC 네트워크 토폴로지를 그래픽 형식으로 로드 하 고 확인 하** 는 것입니다. Lync Server 2013 관리자는 아래 그림에 나와 있는 것 처럼 **네트워크 구성 다운로드** 옵션을 사용 하 여 lync server 2013 컴퓨터에서 CAC 네트워크 토폴로지 구성을 로드 하 고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="b133d-527">이 도구는 Lync 구성 저장소에 연결 되지 않은 컴퓨터에 배포할 때 이러한 구성을 다운로드 하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="b133d-528">![네트워크 구성을 다운로드 합니다.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "네트워크 구성을 다운로드 합니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="b133d-529">**그래픽 형식으로 대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.** Lync Server 2013 대역폭 정책 서버는 CAC 네트워크 토폴로지를 Lync Server 2013 파일 공유 위치 아래에 있는 로깅 메커니즘의 일부로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="b133d-530">Lync Server 관리자는 아래와 같이 **네트워크 구성 열기** 옵션을 사용 하 여 그래픽 형식으로 이러한 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="b133d-531">![대역폭 정책 서버 로그 파일 열기](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "대역폭 정책 서버 로그 파일 열기")</span><span class="sxs-lookup"><span data-stu-id="b133d-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="b133d-532">CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다. Lync Server 2013 관리자는 아래와 같이 **네트워크 구성 복사본 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성 파일을 xml 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="b133d-533">저장 된 구성 파일은 그래픽 보기를 위해 오프 라인으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="b133d-534">![네트워크 구성을 XML 파일로 저장](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "네트워크 구성을 XML 파일로 저장")</span><span class="sxs-lookup"><span data-stu-id="b133d-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="b133d-535">다음에 설명 된 대로 CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장 및 저장: Lync Server 2013 관리자는 다음과 같이 **네트워크 구성 다이어그램을 그림으로 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성을 그래픽 형식 (JPG 및 BMP 파일 형식)으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="b133d-536">![네트워크 구성을 그림으로 저장](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "네트워크 구성을 그림으로 저장")</span><span class="sxs-lookup"><span data-stu-id="b133d-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="b133d-537">**CAC 네트워크 토폴로지 구성 데이터 보기:** Lync Server 2013 관리자는 아래와 같이 네트워크 구성 데이터 보기 옵션을 사용 하 여 네트워크 지역, 네트워크 사이트, 대역폭 프로필 및 사이트 서브넷 IP 주소와 같은 관련 네트워크 구성 데이터를 텍스트 형식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="b133d-538">![네트워크 구성 데이터 보기](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "네트워크 구성 데이터 보기")</span><span class="sxs-lookup"><span data-stu-id="b133d-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="b133d-539">**트리 보기 스타일로 CAC 네트워크 토폴로지 보기:** Lync Server 2013 관리자는 아래와 같이 도구 창의 왼쪽에 있는 제어판을 사용 하 여 관련 네트워크 구성 데이터를 그래픽 트리 보기 스타일로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="b133d-540">![트리 뷰에서 네트워크 구성 데이터 보기](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "트리 뷰에서 네트워크 구성 데이터 보기")</span><span class="sxs-lookup"><span data-stu-id="b133d-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="b133d-541">**CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.** Lync Server 2013 관리자는 아래와 같이 설정 옵션을 사용 하 여 CAC 네트워크 구성 WAN 링크에 대 한 사용자 지정 그래픽 커넥터를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="b133d-542">이렇게 하면 네트워크 구성에서 프로 비전 되는 다양 한 유형의 네트워크 링크를 구분 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="b133d-543">![CAC 네트워크 토폴로지의 사용자 지정 커넥터 정의](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC 네트워크 토폴로지의 사용자 지정 커넥터 정의")</span><span class="sxs-lookup"><span data-stu-id="b133d-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="b133d-544">**CAC 네트워크 토폴로지 사이트 정보, 지역 정보 및 프로 비전 된 대역폭 정책 보기:** Lync Server 2013 관리자는 아래 표시 된 옵션을 사용 하 여 관련 CAC 네트워크 지역 정보, 사이트 정보 및 CAC 대역폭 프로 비전 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="b133d-545">예를 들어 네트워크 지역 또는 네트워크 사이트 개체에서 **정보** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="b133d-546">![네트워크에 대 한 사용자 지정 커넥터 정의](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "네트워크에 대 한 사용자 지정 커넥터 정의")</span><span class="sxs-lookup"><span data-stu-id="b133d-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-547">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-547">Summary</span></span>

<span data-ttu-id="b133d-548">이 도구는 배포에 대 한 CAC 네트워크 토폴로지를 그래픽 형식으로 보려는 Lync Server 2013 관리자에 게 유용한 리소스 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="b133d-549">응답 그룹 에이전트 라이브</span><span class="sxs-lookup"><span data-stu-id="b133d-549">Response Group Agent Live</span></span>

<span data-ttu-id="b133d-550">에이전트에서는 응답 그룹 응용 프로그램을 사용 하 여 기본 제공 웹 서비스를 통해 유용한 실시간 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="b133d-551">아쉽게도이 데이터에 대 한 그래픽 보기는 응용 프로그램 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="b133d-552">응답 그룹 에이전트 라이브 Resource Kit 도구는이 정보에 액세스 하 여 다른 에이전트와 같은 실시간 Microsoft Lync 2013 통신 소프트웨어 정보를 사용 하 여이 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-553">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-553">Description</span></span>

<span data-ttu-id="b133d-554">응답 그룹 에이전트 라이브는 응답 그룹 에이전트에 로그인 및 로그 아웃 기능과 일부 실시간 정보 (예: 그룹 구성원 자격 및 현재 통화 수)를 제공 하는 Windows 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="b133d-555">이는 Lync 2013에서 액세스할 수 있는 향상 된 버전의 에이전트 그룹 페이지를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-556">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-556">Purpose</span></span>

<span data-ttu-id="b133d-557">응답 그룹 응용 프로그램은 수신 전화를 큐에 대기 시키고 에이전트 그룹에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="b133d-558">서비스에 대 한 호출을 결정 하기 위해, 에이전트는 사용 가능한 다른 에이전트 및 각 큐에서 대기 중인 호출 수와 같은 에이전트 그룹에 대 한 실시간 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="b133d-559">처음에 응답 그룹 서비스를 통해서만 액세스할 수 있는이 정보는 그룹 에이전트 라이브에 대 한 직관적인 방식으로 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="b133d-560">기능</span><span class="sxs-lookup"><span data-stu-id="b133d-560">Features</span></span>

<span data-ttu-id="b133d-561">응답 그룹 에이전트 라이브 도구는 응답 그룹 서비스 및 Microsoft Lync 2013 SDK를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="b133d-562">응답 그룹 에이전트는 응답 그룹 서비스에서 사용할 수 있는 정보 및 기능 (예: 그룹 구성원, 다른 에이전트의 현재 상태 및 대기 통화 수)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="b133d-563">아래 그림에서는 응답 그룹 에이전트 라이브의 주요 인터페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="b133d-564">![응답 그룹 에이전트 라이브 도구입니다.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "응답 그룹 에이전트 라이브 도구입니다.")</span><span class="sxs-lookup"><span data-stu-id="b133d-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="b133d-565">응답 그룹 에이전트 라이브의 에이전트에는 다음과 같은 세 가지 주요 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="b133d-566">**로그인/출력:** Lync 2013에서 액세스할 수 있는 에이전트 그룹 페이지와 반대로, 응답 그룹 에이전트를 사용 하는 경우에는 한 번에 에이전트 에서만 로그인 하거나 모든 에이전트 그룹을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="b133d-567">이 응용 프로그램은 에이전트가 로그인 하거나 로그 아웃할 수 있는 세 가지 빠른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="b133d-568">응용 프로그램 내에서 로그인/출력 (녹색 및 빨강) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="b133d-569">시스템 트레이 아이콘을 마우스 오른쪽 단추로 클릭 하 고 로그인 또는 로그 아웃을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="b133d-570">구성 가능한 바로 가기 키 사용</span><span class="sxs-lookup"><span data-stu-id="b133d-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="b133d-571">**그룹 구성원 자격:** 에이전트 그룹을 선택 하면 응답 그룹 에이전트 Live에 오른쪽 창에서이 그룹의 에이전트 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="b133d-572">Lync 2013이이 응용 프로그램과 동일한 컴퓨터에서 실행 되는 경우 현재 상태 정보 및 대화 상대 카드는 응답 그룹 에이전트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="b133d-573">상담원은 IM을 보내거나 여기에서 다른 에이전트를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="b133d-574">**실시간 통계:** 응답 그룹 에이전트 라이브에서는 모든 에이전트 그룹에 대해 실시간 통계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="b133d-575">업데이트 빈도가 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-575">The update frequency is one minute.</span></span> <span data-ttu-id="b133d-576">응답 그룹에서 전화를 받은 경우 현재 대기 중인 통화 수를 사용 하 여 그룹 이름 옆에 시각적 표시기가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="b133d-577">그룹 위에 포인터를 일시 중지 하면 가장 오래 된 대기 시간이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-578">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-578">Requirements</span></span>

<span data-ttu-id="b133d-579">응답 그룹 에이전트를 사용 하려면 .NET Framework 4.0이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="b133d-580">또한 현재 상태 및 대화 상대 카드 기능을 활용 하려면 Lync 2013을 로컬로 설치 하 고 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="b133d-581">구성</span><span class="sxs-lookup"><span data-stu-id="b133d-581">Configuration</span></span>

<span data-ttu-id="b133d-582">응용 프로그램의 옵션 대화 상자를 사용 하 여 개별 기본 설정에 응답 그룹 에이전트 Live를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="b133d-583">또한 관리자는 RGAgentLive.exe.config 파일의 defaultHostAddress 속성을 직접 편집 하 여 기본 호스트 주소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="b133d-584">아래 그림에서는 상담원이 호스트 주소 및 바로 가기 키를 구성 하는 데 사용할 수 있는 옵션 대화 상자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="b133d-585">주 인터페이스의 오른쪽 위에 있는 옵션 단추를 클릭 하 여이 대화 상자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="b133d-586">![응답 그룹 에이전트 라이브 옵션 대화 상자](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "응답 그룹 에이전트 라이브 옵션 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="b133d-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="b133d-587">응답 그룹 에이전트 라이브 구성에서는 다음과 같은 세 가지 다른 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="b133d-588">호스트 주소:이는 일반적으로 에이전트의 홈 풀에 속하는 웹 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="b133d-589">정확한 응답 그룹 서비스 주소는 호스트 뒤에 적절 한 경로를 추가 하 여이 정보를 바탕으로 백그라운드에서 자동으로 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="b133d-590">바로 가기: 로그인/출력에 대 한 정확한 바로 가기를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="b133d-591">두 바로 가기에는 모두 "Windows 로고" 키 (하나 이상의 키 추가)가 포함 되어야 한다는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="b133d-592">Windows에서 시작: 응용 프로그램이 Windows에서 자동으로 시작 되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-593">예</span><span class="sxs-lookup"><span data-stu-id="b133d-593">Examples</span></span>

<span data-ttu-id="b133d-594">아래 그림에서는 오른쪽 창에서 연락처를 마우스 오른쪽 단추로 클릭 하 여 다른 에이전트로 IM을 호출 하거나 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="b133d-595">![통화 만들기 또는 메신저 대화 보내기](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "통화 만들기 또는 메신저 대화 보내기")</span><span class="sxs-lookup"><span data-stu-id="b133d-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="b133d-596">아래 그림에서는 응답 그룹 에이전트 라이브에 큐의 현재 통화 수와 이러한 모든 수신 전화 간의 대기 시간이 가장 긴 지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="b133d-597">![큐 정보 보기](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "큐 정보 보기")</span><span class="sxs-lookup"><span data-stu-id="b133d-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-598">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-598">Summary</span></span>

<span data-ttu-id="b133d-599">Fast sign-on 및 로그 아웃, 그룹 구성원 자격 및 기본 실시간 통계는 응답 그룹 서비스의 응용 프로그램 외부 에서만 사용할 수 있는 흥미로운 응답 그룹 에이전트 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="b133d-600">응답 그룹 에이전트 라이브 리소스 키트 도구를 사용 하는 경우 Lync 관리자는 사용자가 더 빠르고 그래픽 방식으로 작업을 수행할 수 있도록 하는 Windows 응용 프로그램에 에이전트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="b133d-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b133d-601">SEFAUtil</span></span>

<span data-ttu-id="b133d-602">SEFAUtil (보조 확장 기능 활성화)는 Microsoft Lync Server 2013 통신 소프트웨어 관리자 및 헬프데스크 에이전트에서 Lync Server 2013 사용자를 대신 하 여 위임-링, 착신 전환, 동시 전화 신호, 팀 호출 설정 및 그룹 통화 픽업을 구성할 수 있도록 하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="b133d-603">또한이 도구를 사용 하면 관리자가 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다. SEFAUtil 도구를 사용 하면 관리자가 사용자를 대신 하 여 착신 전환 또는 동시 신호음 울림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="b133d-604">관리자는 대상 (SIP URI 형식)을 지정 하거나 사용자가 이미 게시 한 대상을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="b133d-605">또한 관리자는이 도구를 사용 하 여 사용자 대신 대리인 또는 팀 호출 그룹 구성원을 추가 하거나 제거할 수 있습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (지 수) 3.0를 기반으로 작성 되었으며 관리자가 SEFAUtil에 대 한 중앙 관리 저장소에서 트러스트 된 응용 프로그램을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="b133d-606">SEFAUtil (보조 확장 기능 활성화) Lync server 2013 관리자 및 지원 센터 에이전트가 Lync Server 2013 사용자를 대신 하 여 위임-링, 착신 전환, 동시 신호 울림, 팀 호출 설정 및 그룹 통화 픽업을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="b133d-607">또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-608">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-608">Description</span></span>

<span data-ttu-id="b133d-609">현재 버전의 SEFAUtil는 명령줄 도구에 불과합니다. 지원 그래픽 사용자 인터페이스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="b133d-610">이 도구는 Microsoft 통합 커뮤니케이션 관리 API (c) 3.0를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="b133d-611">관리자 및 헬프데스크 에이전트는이 도구의 기능을 사용 하 여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="b133d-612">사용자에 대 한 모든 통화 라우팅 설정 보기 (통화 전달, 위임, 동시 신호음, 팀 통화 및 그룹 통화 픽업 포함)</span><span class="sxs-lookup"><span data-stu-id="b133d-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="b133d-613">사용/사용 안 함/수정 통화 전달 설정 (대상 및 응답 없음 타이머 포함)</span><span class="sxs-lookup"><span data-stu-id="b133d-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="b133d-614">사용/사용 안 함/수정 전화 착신 전환 즉시 구성</span><span class="sxs-lookup"><span data-stu-id="b133d-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="b133d-615">위임 설정 사용/사용 안 함/수정</span><span class="sxs-lookup"><span data-stu-id="b133d-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="b133d-616">팀 호출 그룹 설정 사용/사용 안 함/수정</span><span class="sxs-lookup"><span data-stu-id="b133d-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-617">Lync Server 2013 SEFAUtil 도구에 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="b133d-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="b133d-618">동시 벨 울림 설정 사용/사용 안 함/수정 (대상 포함)</span><span class="sxs-lookup"><span data-stu-id="b133d-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-619">Lync Server 2013 SEFAUtil 도구에 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="b133d-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="b133d-620">그룹 통화 픽업 설정 사용/사용 안 함/수정</span><span class="sxs-lookup"><span data-stu-id="b133d-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b133d-621">Lync Server 2013 SEFAUtil 도구에 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="b133d-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="b133d-622">이 도구에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="b133d-623">Lync Server 풀에 속한 사용자만 지원 됨</span><span class="sxs-lookup"><span data-stu-id="b133d-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="b133d-624">여러 사용자에 대 한 통화 라우팅 설정의 대량 편집은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-625">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-625">Output</span></span>

<span data-ttu-id="b133d-626">이 도구의 현재 버전은 명령 프롬프트 창에만 출력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="b133d-627">자세한 내용은이 문서 뒷부분의 예 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b133d-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-628">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-628">Purpose</span></span>

<span data-ttu-id="b133d-629">이 도구를 사용할 수 있는 몇 가지 주요 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="b133d-630">Bob은 임원 이며 Lync Server 전화 통신으로 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="b133d-631">기존 PBX 시스템에 대 한 위임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="b133d-632">Lync로 이동의 일부로, 관리자는 기존 위임 구성을 반영 하도록 Bob의 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="b133d-633">Alice가 모바일 고객 중 한 명에 게 중요 한 전화를 거는 것을 인식 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="b133d-634">하지만 호텔에는 해당 컴퓨터에 대 한 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="b133d-635">지원 센터에 전화를 걸고 사용자에 게 회사 번호로 건 모든 통화를 휴대폰으로 전달 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="b133d-636">지원 센터 직원이 자신을 대신해 서 구성을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="b133d-637">Joe의 직장 번호에 대 한 통화는 직장에서 언제 든 지 모바일 음성 메일로 이동 합니다. 그러나 대부분의 다른 위치에서 제대로 작동 하는 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="b133d-638">헬프데스크 기술자는 Joe의 라우팅 구성을 볼 수 있으며, Joe가 휴대폰으로 구성 된 동시 연결을 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="b133d-639">기술자는 귀하의 사무실에 있는 모바일 기능에 대 한 정보를 제공 하 고 동시 벨 울림 규칙으로 인해 네트워크에 문제가 있을 경우 Joe의 모바일 음성 메일로 전화가 이동 하도록 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="b133d-640">Mike는 Contoso의 새로운 직원이 며, Microsoft Lync에 대해 사용 하도록 설정 된 경우 관리자가 팀 호출에 대해 모든 구성원을 포함 하도록 구성 하는 새 팀에 참여 하 고 있으며, 관리자는 팀의 각 구성원에 대해 Mike를 팀 호출 그룹 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="b133d-641">Contoso의 인적 자원 부서에 있는 고객 서비스 연습은 최초 통화 이후 모든 발신자에 게 개인 서비스를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="b133d-642">부서의 모든 구성원이 서로 가까이에 있을 것 이므로 모든 전화가 팀과 동시에 모든 전화를 사용 하는 것은 팀에 게 매우 방해가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="b133d-643">팀 구성원을 중단시 키 지 않고 최상의 서비스를 제공 하기 위해 Lync 관리자는 그룹 통화 픽업 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="b133d-644">관리자가 모든 부서 구성원을 pickup 그룹에 추가 하 고 해당 부서에 pickup 그룹 번호를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="b133d-645">Samantha가 책상에 없으면 Joe가 전화를 걸고 사용자의 책상 으로부터 통화에 응답 하도록 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-646">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-646">Requirements</span></span>

<span data-ttu-id="b133d-647">SEFAUtil 도구는 트러스트 된 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="b133d-648">해당 컴퓨터에 c s p 3.0이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="b133d-649">이 도구를 실행 하려면 SEFAUtil 응용 프로그램 ID가 있는 새 신뢰할 수 있는 응용 프로그램을 해당 풀에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="b133d-650">**SEFAUtil 도구에 대 한 신뢰할 수 있는 응용 프로그램 새로 만들기**</span><span class="sxs-lookup"><span data-stu-id="b133d-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="b133d-651">SEFAUTil 도구는 트러스트 된 응용 프로그램 풀에 속하는 컴퓨터 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="b133d-652">필요한 경우 다음 cmdlet을 사용 하 여 Lync Server 관리 셸을 통해 풀을 새 신뢰할 수 있는 응용 프로그램 풀로 추가 하는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-653">SEFAUtil 도구를 실행 하는 데 사용 되는 모든 컴퓨터에는 c s p 3.0이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="b133d-654">신뢰할 수 있는 응용 프로그램은 SEFAUtil 도구에 대 한 토폴로지에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="b133d-655">SEFAUtil를 새 신뢰할 수 있는 응용 프로그램으로 정의 하려면 Lync Server 관리 셸을 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-656">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="b133d-657">토폴로지 변경 내용을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="b133d-658">다음 cmdlet을 실행 하 여 Lync Server 관리 셸을 통해 토폴로지 변경을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="b133d-659">필요한 경우 SEFAUtil 도구를 실행 하는 데 사용할 Lync Server 2013 Resource Kit 도구 (서버는 신뢰할 수 있는 응용 프로그램 풀의 일부가 되어야 함)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="b133d-660">SEFAUtil가 제대로 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="b133d-661">이렇게 하려면 관리자 권한으로 windows 명령 프롬프트에서 도구를 실행 하 여 배포에 포함 된 사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="b133d-662">도구는 기본적으로 다음 \\ 위치에 배치 됩니다. 프로그램 파일 \\ Microsoft Lync Server 2013 \\ Reskit ".</span><span class="sxs-lookup"><span data-stu-id="b133d-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="b133d-663">사용자의 착신 전환 설정을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="b133d-664">사용자의 착신 전환 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="b133d-665">그룹 통화 받기</span><span class="sxs-lookup"><span data-stu-id="b133d-665">Group Call Pickup</span></span>

<span data-ttu-id="b133d-666">그룹 통화 픽업 기능을 사용 하려면 Lync Server의 추가 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="b133d-667">사용자에 게 pickup 그룹을 할당 하기 전에이 기능의 계획 및 배포 단계에 대 한 Call Pickup 제품 설명서 그룹을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b133d-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-668">예</span><span class="sxs-lookup"><span data-stu-id="b133d-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="b133d-669">현재 통화 처리 설정 표시</span><span class="sxs-lookup"><span data-stu-id="b133d-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="b133d-670">다음 명령은 사용자에 대 한 통화 처리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-671">다음은 <STRONG>/server</STRONG> 스위치를 사용 하 여 연결할 Lync server를 지정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="b133d-672">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="b133d-673">착신 전환 대상/응답 없음 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="b133d-674">이 예에서는 착신 전환/아니요 응답 대상과 링 지연을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="b133d-675">여기서/server 스위치는 제공 되지 않습니다. SEFAUtil에서 Lync Server의 자동 검색을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="b133d-676">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="b133d-677">착신 전환 즉시 사용</span><span class="sxs-lookup"><span data-stu-id="b133d-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="b133d-678">다음은 다른 사용자에 게 즉시 착신 전환 기능을 사용 하도록 설정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="b133d-679">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="b133d-680">착신 전환 즉시 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b133d-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="b133d-681">이 예에서는 착신 전환을 즉시 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="b133d-682">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="b133d-683">사용자를 대리인으로 추가 하 고 대리인에 게 동시 신호음 울림 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="b133d-684">다음은 사용자를 대리인으로 추가 하 고 대리인의 동시 신호음을 설정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="b133d-685">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="b133d-686">위임의 동시 벨 울림 규칙 변경</span><span class="sxs-lookup"><span data-stu-id="b133d-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="b133d-687">이 예에서는 이전 예제에서 설정한 동시 신호음 규칙을 지연 된 링 규칙으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="b133d-688">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="b133d-689">대리인 제거</span><span class="sxs-lookup"><span data-stu-id="b133d-689">Remove the Delegate</span></span>

<span data-ttu-id="b133d-690">이 예에서는 대리인을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-691">마지막 대리인이 제거 되 면 대리인의 벨 울림은 자동으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="b133d-692">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="b133d-693">대리인을 추가 하 고 대리인 규칙에 Call-Forward 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="b133d-694">다음은 대리인을 추가 하 고 착신 전환을 대리인 규칙에 설정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="b133d-695">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="b133d-696">동시 신호음 사용 및 대상 번호 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="b133d-697">이 예에서는 동시 신호음을 사용 하도록 설정 하 고 동시 벨 울림 대상 번호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-698">이미 동시에 신호음을 사용 하도록 설정 된 사용자의 동시 울림 대상 번호를 변경 하려면/enablesimulring 스위치를 사용 하 여 명령을 유지 하 고, 그렇지 않으면 대상 번호가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="b133d-699">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="b133d-700">동시 신호음 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b133d-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="b133d-701">이 예에서는 동시 신호음을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="b133d-702">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="b133d-703">Team-Call에 대 한 팀 구성원을 추가 하 고 Team-Call 구성원 그룹으로 동시 벨 울림 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="b133d-704">이 예에서는 사용자의 팀 호출 그룹에 팀 구성원을 추가 하 고 팀 호출 그룹에 동시에 신호음을 울리는 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-705">사용자의 팀 호출 그룹에 구성원을 추가 하면 자동으로 사용자의 동시 연결 해제 settigs가 팀 호출 그룹을 simulring으로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="b133d-706">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="b133d-707">Team-Call 그룹에서 구성원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="b133d-708">이 예에서는 사용자의 팀 호출 그룹 팀 구성원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-709">제거할 구성원이 팀 호출 그룹의 유일한 구성원이 면 팀 호출 그룹에 동시에 연결 하는 것이 자동으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="b133d-710">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="b133d-711">지연 된 링을 Team-Call 그룹으로 설정</span><span class="sxs-lookup"><span data-stu-id="b133d-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="b133d-712">이 예에서는 지연 된 링을 팀 통화 그룹 시간 설정으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="b133d-713">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="b133d-714">Team-Call 사용</span><span class="sxs-lookup"><span data-stu-id="b133d-714">Enable Team-Call</span></span>

<span data-ttu-id="b133d-715">이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-716">사용자의 팀 호출 그룹에 구성원이 없으면 팀 호출을 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="b133d-717">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="b133d-718">Team-Call 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b133d-718">Disable Team-Call</span></span>

<span data-ttu-id="b133d-719">이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="b133d-720">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="b133d-721">그룹 통화 픽업 사용 및 사용자에 게 Pickup 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="b133d-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="b133d-722">이 예에서는 사용자에 게 pickup 그룹을 할당 하 고 그룹 통화 픽업을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="b133d-723">**출력**</span><span class="sxs-lookup"><span data-stu-id="b133d-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="b133d-724">그룹 통화 픽업 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b133d-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="b133d-725">이 예에서는 지정 된 사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-726">사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 하면 사용자에 게 할당 된 그룹 번호가 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="b133d-727">이후에 해당 사용자에 대 한 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 스위치를 사용 하 여 그룹 번호를 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="b133d-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b133d-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-729">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-729">Description</span></span>

<span data-ttu-id="b133d-730">SYSPrep.ps1는 Windows Server 2008 운영 체제 컴퓨터에 다음 Lync Server 2013 필수 구성 요소를 설치 하는 Windows PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="b133d-731">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b133d-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="b133d-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="b133d-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="b133d-733">Windows Powershell 버전 3.0</span><span class="sxs-lookup"><span data-stu-id="b133d-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="b133d-734">Visual 2010 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="b133d-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="b133d-735">인터넷 정보 서버 업데이트</span><span class="sxs-lookup"><span data-stu-id="b133d-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="b133d-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b133d-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="b133d-737">Lync Server 2013 코어 파일</span><span class="sxs-lookup"><span data-stu-id="b133d-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="b133d-738">스크립트 이름은 Microsoft Windows 운영 체제에 대 한 시스템 준비 도구와 비슷하지만 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="b133d-739">이 스크립트는 Lync Server 2013에 필요한 필수 구성 요소만 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="b133d-740">이러한 필수 구성 요소를 설치한 후에는 Windows SYSPrep 도구를 사용 하 여 서버의 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-741">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-741">Requirements</span></span>

<span data-ttu-id="b133d-742">SYSPrep.ps1 스크립트를 실행 하기 전에 먼저 필수 구성 요소 파일을 Windows Server 2008 운영 체제 컴퓨터의 로컬 폴더 (예 **: D; \\ 설치)** 에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="b133d-743">이 폴더에는 Lync Server 2013 파일의 복사본 (특히Setup.exe)도 포함 해야 합니다 \*\* .\*\*</span><span class="sxs-lookup"><span data-stu-id="b133d-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="b133d-744">필수 구성 요소 파일은 다음 위치에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b133d-745">충족</span><span class="sxs-lookup"><span data-stu-id="b133d-745">Prerequisite</span></span></th>
<th><span data-ttu-id="b133d-746">위치</span><span class="sxs-lookup"><span data-stu-id="b133d-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b133d-747">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b133d-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b133d-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b133d-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b133d-749">Windows Powershell 버전 3.0</span><span class="sxs-lookup"><span data-stu-id="b133d-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b133d-750">Visual 2010 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="b133d-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b133d-751">인터넷 정보 서버 업데이트</span><span class="sxs-lookup"><span data-stu-id="b133d-751">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b133d-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b133d-752">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b133d-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="b133d-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="b133d-754">Lync Server 2013 미디어에서 복사</span><span class="sxs-lookup"><span data-stu-id="b133d-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="b133d-755">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b133d-755">Parameter</span></span>

<span data-ttu-id="b133d-756">**– Setupfolder** 매개 변수는 필수 구성 요소 파일의 디렉터리 위치를 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-757">예</span><span class="sxs-lookup"><span data-stu-id="b133d-757">Examples</span></span>

<span data-ttu-id="b133d-758">SYSPrep.ps1 스크립트를 실행 하 고 Lync Server 2013 필수 구성 요소를 설치 하려면 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="b133d-759">할당 되지 않은 번호 알림 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b133d-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="b133d-760">지정 되지 않은 번호 알림 마이그레이션 도구를 사용 하면 Lync 관리자가 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 원본 Lync Server 또는 풀에서 대상 Lync Server 또는 풀로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-761">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-761">Description</span></span>

<span data-ttu-id="b133d-762">할당 되지 않은 번호 알림 마이그레이션 도구는 원본 서버 또는 풀의 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 다른 서버나 풀로 이동 하는 Windows PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="b133d-763">할당 되지 않은 번호 알림 마이그레이션 스크립트를 실행 하면 다음 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="b133d-764">원본 서버 또는 풀에 호스트 된 알림 응용 프로그램의 할당 되지 않은 번호 알림에 사용 되는 모든 오디오 파일을 대상 서버 또는 풀의 파일 저장소로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b133d-765">오디오 파일은 대상 풀로 복사 된 후 원본 풀에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="b133d-766">원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 대해 구성 된 모든 할당 되지 않은 번호 알림을 대상 서버 또는 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="b133d-767">원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에서 지 원하는 모든 할당 되지 않은 번호 범위를 대상 서버 또는 풀에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="b133d-768">스크립트를 성공적으로 실행 한 후에는 원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 의해 처리 된 모든 할당 되지 않은 번호 범위가 대상 서버 또는 풀에서 동일한 구성으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-769">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-769">Output</span></span>

<span data-ttu-id="b133d-770">**CsAnnouncementConfiguration** 스크립트는 마이그레이션 작업의 성공 또는 실패를 실행 하는 Lync Management Shell 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="b133d-771">작업 실행이 오류로 인해 중단 되는 경우 대상으로 성공적으로 이동 된 지정 되지 않은 번호 범위는 운영 양식의 대상에 유지 되 고 마이그레이션될 수 없는 나머지 번호 범위는 운영 양식의 원본에도 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="b133d-772">나머지 구성을 완전히 마이그레이션하려면 오류를 해결 한 후 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b133d-773">용도</span><span class="sxs-lookup"><span data-stu-id="b133d-773">Purpose</span></span>

<span data-ttu-id="b133d-774">할당 되지 않은 번호 알림 마이그레이션 스크립트는 다음과 같은 세 가지 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="b133d-775">**새 버전의 Lync Server로 구성 설정 마이그레이션:** Contoso는 lync server 2013로 마이그레이션하고 마이그레이션 프로세스의 일부로, Lync server 관리자가 알림 응용 프로그램에서 서비스를 제공 하는 할당 되지 않은 번호 구성을 Lync Server 2010 배포에서 새 Lync Server 2013 배포로 이동 하 고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="b133d-776">구성 설정을 이동 하기 위해 Lync Server 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="b133d-777">**Lync server 2013에서 Lync server 2010로 배포 롤백:** 예기치 않은 요인으로 인해 Contoso는 새 Lync Server 2013 배포로 마이그레이션을 롤백해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="b133d-778">서비스 중단을 최소화 하기 위해 Lync Server 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 Lync server 2013 배포의 구성을 Lync Server 2010 배포로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="b133d-779">**Lync 배포 간에 데이터 이동:** Contoso는 한 풀의 모든 서버를 새 서버로 교체 하는 프로세스를 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="b133d-780">이러한 전략은 새 Lync Server 2013 풀을 배포 하 고, 이전의 모든 데이터를 새 풀로 이동한 다음, 이전 풀을 사용 중지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="b133d-781">새 풀이 배포 되 면 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 구성을 이전 풀에서 새 그룹으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-782">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-782">Requirements</span></span>

<span data-ttu-id="b133d-783">도구를 성공적으로 실행 하려면 다음과 같은 주요 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="b133d-784">Lync Server 2013 관리 셸이 설치 된 컴퓨터에서 스크립트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="b133d-785">알림 응용 프로그램을 원본 및 대상 Lync 서버 또는 풀에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="b133d-786">Move-CsAnnouncementConfiguration 스크립트</span><span class="sxs-lookup"><span data-stu-id="b133d-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="b133d-787">Move-CsAnnouncementConfiguration 스크립트를 사용 하려면 아래 표에 설명 된 매개 변수가 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="b133d-788">![CsAnnouncementConfiguration 매개 변수입니다.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration 매개 변수")</span><span class="sxs-lookup"><span data-stu-id="b133d-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-789">예</span><span class="sxs-lookup"><span data-stu-id="b133d-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="b133d-790">지정 되지 않은 번호 알림 구성을 Lync Server 2010 풀에서 Lync Server 2013 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="b133d-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="b133d-791">이 예제에서는 지정 되지 않은 번호 알림을 원본 풀 (Lync Server 2010)에서 대상 풀 (Lync Server 2013)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="b133d-792">지정 되지 않은 번호 알림 구성을 Lync Server 2013 풀에서 Lync Server 2010 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="b133d-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="b133d-793">이 예제에서는 지정 되지 않은 번호 알림을 원본 풀 (Lync Server 2013)에서 대상 풀 (Lync Server 2010)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="b133d-794">웹 회의 데이터</span><span class="sxs-lookup"><span data-stu-id="b133d-794">Web Conf Data</span></span>

<span data-ttu-id="b133d-795">웹 회의 데이터 도구를 사용 하면 Lync Server 2013 통신 소프트웨어 관리자가 이끌이의 웹 회의와 관련 된 데이터를 보다 강력 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="b133d-796">시나리오에는 타임 스탬프 조건을 기준으로 특정 사용자의 모임 데이터를 삭제 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b133d-797">설명</span><span class="sxs-lookup"><span data-stu-id="b133d-797">Description</span></span>

<span data-ttu-id="b133d-798">이 도구를 사용 하면 관리자가 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="b133d-799">단일 사용자와 연결 된 모든 웹 회의 데이터를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="b133d-800">단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="b133d-801">특정 날짜 보다 오래 된 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="b133d-802">사용자가 풀 간에 이동할 때 단일 사용자와 연결 된 모든 웹 회의 데이터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b133d-803">Lync Server 2010에 대 한 리소스 키트 도구는 단일 사용자와 연결 된 모든 웹 회의 데이터를 풀 간에 이동할 때 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="b133d-804">이 기능은 이제 <STRONG>MoveConferenceData</STRONG> 매개 변수로 인해이 도구에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="b133d-805">이 매개 변수에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">csuser</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b133d-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="b133d-806">이 도구는 비활성 상태인 모임에 대 한 모임 데이터만 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="b133d-807">활성 모임 (또는 세션의 모임)은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="b133d-808">이 도구는 대상 사용자와 같은 풀에 있는 컴퓨터에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="b133d-809">이 도구를 사용 하 여 해당 모임 콘텐츠 데이터를 관리 하는 사용자는 동일한 사용자 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b133d-810">출력</span><span class="sxs-lookup"><span data-stu-id="b133d-810">Output</span></span>

<span data-ttu-id="b133d-811">이 도구는 각 작업의 결과를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="b133d-812">쿼리가 수행 되 면이 도구는 해당 사용자가 이끌이 인 모든 비활성 모임 데이터 폴더의 목록을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="b133d-813">Delete를 수행 하는 경우이 도구는 해당 데이터가 삭제 될 모든 모임 데이터 폴더의 목록을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b133d-814">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b133d-814">Requirements</span></span>

<span data-ttu-id="b133d-815">이 도구는 이끌이를 현재 홈에 있는 동일한 풀에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="b133d-816">이 도구는 콘텐츠 파일 저장소에 대 한 액세스 권한으로 관리자 권한을 사용 하 여 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b133d-817">예</span><span class="sxs-lookup"><span data-stu-id="b133d-817">Examples</span></span>

<span data-ttu-id="b133d-818">다음 표에서는 예제에 사용 된 매개 변수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="b133d-819">![웹 회의 데이터 도구 매개 변수](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "웹 회의 데이터 도구 매개 변수")</span><span class="sxs-lookup"><span data-stu-id="b133d-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="b133d-820">위 예제에서는 쿼리 명령이 작동 하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="b133d-821">이러한 명령의 출력은이 도구의 영향을 받게 되는 모든 모임 콘텐츠 폴더의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="b133d-822">위의 예제는 delete 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="b133d-823">삭제 명령을 실행 하면 해당 사용자의 모든 비활성 모임 폴더가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b133d-824">요약</span><span class="sxs-lookup"><span data-stu-id="b133d-824">Summary</span></span>

<span data-ttu-id="b133d-825">이 도구는 전화 회의 데이터를 보다 세부적으로 제어 해야 하는 관리자에 게 유용한 리소스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b133d-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
