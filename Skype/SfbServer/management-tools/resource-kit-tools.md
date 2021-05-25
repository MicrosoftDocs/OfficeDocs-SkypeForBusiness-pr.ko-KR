---
title: 비즈니스용 Skype 서버 2015 Resource Kit 도구 설명서
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 이 문서에서는 각 도구의 용도와 사용 예를 포함하여 비즈니스용 Skype 서버 2015 Resource Kit의 도구에 대해 설명합니다. 비즈니스용 Skype 서버 2015 Resource Kit를 사용하면 2015년을 배포하고 관리하는 IT 관리자가 일상적인 작업을 비즈니스용 Skype 서버 있습니다. 예를 들어 Web Conf 데이터 도구를 사용하면 온라인 모임 중에 사용자가 업로드한 데이터를 쉽게 제어할 수 있습니다. SEFAUtil 도구를 사용하여 사용자에 대해 위임 전화 전달 및 응답을 설정할 수 있습니다. IT 관리자는 이러한 도구를 사용하여 2015의 2015를 보다 비즈니스용 Skype 서버 것이 중요합니다.
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629047"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="3e0c5-107">비즈니스용 Skype 서버 2015 Resource Kit 도구 설명서</span><span class="sxs-lookup"><span data-stu-id="3e0c5-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="3e0c5-108">이 문서에서는 각 도구의 용도와 사용 예를 포함하여 비즈니스용 Skype 서버 2015 Resource Kit의 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-108">This article describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="3e0c5-109">비즈니스용 Skype 서버 2015 Resource Kit를 사용하면 2015년을 배포하고 관리하는 IT 관리자가 일상적인 작업을 비즈니스용 Skype 서버 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="3e0c5-110">예를 들어 **Web Conf 데이터** 도구를 사용하면 온라인 모임 중에 사용자가 업로드한 데이터를 쉽게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3e0c5-111">**SEFAUtil 도구를** 사용하여 사용자에 대해 위임 전화 전달 및 응답을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3e0c5-112">IT 관리자는 이러한 도구를 사용하여 2015의 2015를 보다 비즈니스용 Skype 서버 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3e0c5-113">리소스 키트 도구 설치</span><span class="sxs-lookup"><span data-stu-id="3e0c5-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3e0c5-114">비즈니스용 Skype 서버 2015 리소스 키트를 설치하려면 다운로드 [센터에서](https://www.microsoft.com/download/details.aspx?id=52631)OCSReskit.msi다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="3e0c5-115">간단한 **OCSResKit.msi** 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="3e0c5-116">이 .msi **%Program Files%\비즈니스용 Skype 서버 2015\ResKit** 경로에 모든 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="3e0c5-117">자체 포함 실행 파일인 도구는 이 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="3e0c5-118">또한 지원 파일이 있는 도구는 자체 하위 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="3e0c5-119">지원되는 환경</span><span class="sxs-lookup"><span data-stu-id="3e0c5-119">Supported Environments</span></span>

<span data-ttu-id="3e0c5-120">비즈니스용 Skype 서버 2015 Resource Kit는 비즈니스용 Skype 서버 2015에 필요한 사양을 충족하는 서버에 설치해야 합니다(일반적으로 비즈니스용 Skype 서버 2015 실행에 사용).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3e0c5-121">리소스 키트 도구 개요</span><span class="sxs-lookup"><span data-stu-id="3e0c5-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3e0c5-122">다음은 비즈니스용 Skype 서버 2015 Resource Kit에서 제공하는 도구 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3e0c5-123">다음 섹션에서는 요구 사항 및 예제 사용법을 포함하여 각 도구에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="3e0c5-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3e0c5-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="3e0c5-125">대역폭 정책 서비스 모니터</span><span class="sxs-lookup"><span data-stu-id="3e0c5-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="3e0c5-126">대역폭 사용률 분석기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="3e0c5-127">통화 파기계</span><span class="sxs-lookup"><span data-stu-id="3e0c5-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="3e0c5-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3e0c5-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="3e0c5-129">서비스 Storage 가져오기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="3e0c5-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3e0c5-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="3e0c5-131">사용자 콘솔 룩업</span><span class="sxs-lookup"><span data-stu-id="3e0c5-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="3e0c5-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3e0c5-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="3e0c5-133">네트워크 구성 뷰어</span><span class="sxs-lookup"><span data-stu-id="3e0c5-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="3e0c5-134">응답 그룹 에이전트 Live</span><span class="sxs-lookup"><span data-stu-id="3e0c5-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="3e0c5-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3e0c5-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="3e0c5-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3e0c5-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="3e0c5-137">미지정 번호 공지 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3e0c5-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="3e0c5-138">웹 Conf 데이터</span><span class="sxs-lookup"><span data-stu-id="3e0c5-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="3e0c5-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3e0c5-139">ABSConfig</span></span>
<span data-ttu-id="3e0c5-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="3e0c5-141">ABSConfig(주소 기록 서비스 구성 도구)는 관리자가 2015년 8월의 주소 비즈니스용 Skype 서버 사용자 지정하는 데 도움이 되는 관리 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="3e0c5-142">또한 이 도구를 사용하면 비즈니스용 Skype 서버 2015 관리자가 기본 주소 기록 서비스 설정을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-143">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-143">Description</span></span>

<span data-ttu-id="3e0c5-144">ABSConfig는 관리자가 주소 지정 서비스와 관련된 Active Directory 도메인 서비스 특성을 구성할 수 있도록 하는 그래픽 사용자 인터페이스 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="3e0c5-145">도구의 주요 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="3e0c5-146">관리자가 Active Directory 도메인 서비스의 특성을 2015 또는 2015의 특성에 매핑할 비즈니스용 Skype 서버 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="3e0c5-147">관리자가 주소장 서비스 파일에 포함하거나 제외할 Active Directory 도메인 서비스 특성을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="3e0c5-148">관리자가 복원할 수 있도록 기본 주소장 서비스 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-148">To enable administrators to restore,  default Address Book Service settings.</span></span>

<span data-ttu-id="3e0c5-149">ABSConfig 도구는 이 파일을 사용하여 시작할 ABSConfig.exe 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="3e0c5-150">도구가 특성 구성 **탭으로 열립니다.** 이 표에는 Active Directory 도메인 서비스 특성을 비즈니스용 Skype 서버 2015의 특성 필드에 매핑하고 특정 특성 필터에 따라 주소 기록 서비스 파일에 포함하거나 제외할 사용자를 지정하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3e0c5-151">또한 주소장 파일에 포함될 전화 번호 값을 사용자 지정할 수 있는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3e0c5-152">기본값 **복원 옵션을 사용하면** 관리자가 주소 책 서비스 설정을 기본값으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0c5-153">AD 특성을 다른 OC 필드 이름에 다시 매핑하면 주소 책 파일 다운로드에만 작동하며 주소 책 웹 쿼리에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-154">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-154">Output</span></span>

<span data-ttu-id="3e0c5-155">ABSConfig는 주소 책 서비스 구성을 데이터베이스에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="3e0c5-156">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-156">Purpose</span></span>

<span data-ttu-id="3e0c5-157">ABSConfig는 2015 주소 비즈니스용 Skype 서버 쉽고 빠르게 사용자 지정할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="3e0c5-159">컴퓨터</span><span class="sxs-lookup"><span data-stu-id="3e0c5-159">Computer</span></span>

<span data-ttu-id="3e0c5-160">ABSConfig는 2015가 설치된 도메인에 가입된 컴퓨터에서만 비즈니스용 Skype 서버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="3e0c5-161">비즈니스용 Skype 서버 2015의 경우 Enterprise Edition 설정하는 동안 주소 Front-End 서버의 모든 서버에서 이 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front-End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="3e0c5-162">네트워크</span><span class="sxs-lookup"><span data-stu-id="3e0c5-162">Network</span></span>

<span data-ttu-id="3e0c5-163">컴퓨터가 데이터베이스 풀 및 백 엔드 Front-End 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-163">The computer should be able to connect to the Front-End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="3e0c5-164">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="3e0c5-164">Software</span></span>

<span data-ttu-id="3e0c5-165">ABSConfig 도구를 실행하기 전에 다음 소프트웨어 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="3e0c5-166">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="3e0c5-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="3e0c5-167">사용자</span><span class="sxs-lookup"><span data-stu-id="3e0c5-167">Users</span></span>

<span data-ttu-id="3e0c5-168">비즈니스용 Skype 서버 배포를 업데이트하는 데 필요한 권한이 있는 관리자</span><span class="sxs-lookup"><span data-stu-id="3e0c5-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-169">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-169">Examples</span></span>

<span data-ttu-id="3e0c5-170">ABSConfig는 명령 프롬프트에ABSConfig.exe **입력하여** 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="3e0c5-171">아래는 ABSConfig 도구 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-171">Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe 도구입니다.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="3e0c5-173">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-173">Summary</span></span>

<span data-ttu-id="3e0c5-174">ABSConfig 도구를 사용하면 관리자에게 2015년 주소 비즈니스용 Skype 서버 쉽고 빠르게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3e0c5-175">대역폭 정책 서비스 모니터</span><span class="sxs-lookup"><span data-stu-id="3e0c5-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="3e0c5-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="3e0c5-177">대역폭 정책 서비스 모니터 도구는 관리자가 다음 목록을 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="3e0c5-178">토폴로지에서 구성된 모든 비즈니스용 Skype 서버 2015 대역폭 정책 서비스(인증 및 핵심)</span><span class="sxs-lookup"><span data-stu-id="3e0c5-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="3e0c5-179">각 서비스가 다른 대역폭 정책 서비스 및 에지 서버에 대해 설정하는 연결</span><span class="sxs-lookup"><span data-stu-id="3e0c5-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="3e0c5-180">네트워크 구성 문서에 구성된 모든 링크 및 각 대역폭 정책 서비스에서 보고한 실시간 대역폭 사용량</span><span class="sxs-lookup"><span data-stu-id="3e0c5-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-181">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-181">Description</span></span>

<span data-ttu-id="3e0c5-182">대역폭 정책 서비스 모니터 도구는 GUI 기반 응용 프로그램으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="3e0c5-183">관리자는 이 도구를 실행하여 도구를 PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="3e0c5-184">도구가 시작되면 토폴로지에서 대역폭 정책 서비스 목록을 검색하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="3e0c5-185">초기 업데이트가 완료되면 창 왼쪽 창에 속한 클러스터로 그룹화되는 서비스 목록이 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="3e0c5-186">관리자가 특정 대역폭 정책 서비스를 선택하면 오른쪽 창에 해당 특정 서비스에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="3e0c5-187">이 창에는 정보를 표시하는 두 개의 기본 탭도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="3e0c5-188">컴퓨터 정보 탭</span><span class="sxs-lookup"><span data-stu-id="3e0c5-188">Machine Info Tab</span></span>

<span data-ttu-id="3e0c5-189">컴퓨터 **정보 탭에는** 선택한 대역폭 정책 서비스의 세부 정보와 선택한 대역폭 정책 서비스에서 다른 서비스에 대해 설정한 모든 연결의 목록과 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="3e0c5-190">토폴로지 정보 탭</span><span class="sxs-lookup"><span data-stu-id="3e0c5-190">Topology Info Tab</span></span>

<span data-ttu-id="3e0c5-191">**토폴로지 정보** 탭에는 네트워크 구성 설정에 구성된 모든 링크의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="3e0c5-192">각 링크에 대해 오디오 및 비디오 대역폭 용량이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="3e0c5-193">또한 현재 사용 중인 대역폭이 Kbps로 표시되고 용량의 백분율로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="3e0c5-194">이 도구는 색 코딩을 사용하여 사용률이 용량에 가까운 링크를 강조합니다. 이를 통해 관리자는 이러한 링크를 빠르게 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="3e0c5-195">대역폭 정책 서비스 모니터 도구가 구성된 대역폭 정책 서비스에 연결할 때 오류가 발생하면  컴퓨터 정보  및 토폴로지 정보 탭의 정보가 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="3e0c5-196">그러나 도구가 처음에는 연결되지만 나중에 서비스에 대한 연결이 끊어지는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="3e0c5-197">이러한 경우 관리자에게는 기한이 지난 정보가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="3e0c5-198">관리자가 특정  대역폭 정책 서비스에 대해 데이터를 마지막으로 업데이트한 시기를 관리자가 볼 수 있도록 각 탭에 마지막으로 업데이트된 타임스탬프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-199">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-199">Output</span></span>

<span data-ttu-id="3e0c5-200">명령줄 출력이 없습니다. 프로그램 출력은 기본 GUI(그래픽 사용자 인터페이스)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-201">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-201">Purpose</span></span>

<span data-ttu-id="3e0c5-202">대역폭 정책 서비스 모니터 도구의 목적은 관리자가 토폴로지에서 정의된 각 대역폭 정책 서비스의 상태를 표시하도록 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="3e0c5-203">또한 관리자는 네트워크 구성 문서에 정의된 모든 링크에 대한 실시간 대역폭 사용량을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-204">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-204">Requirements</span></span>

<span data-ttu-id="3e0c5-205">대역폭 정책 서비스 모니터 도구는 네트워크 토폴로지의 일부인 컴퓨터에서 비즈니스용 Skype 서버 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="3e0c5-206">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-206">Summary</span></span>

<span data-ttu-id="3e0c5-207">대역폭 정책 서비스 모니터 도구는 토폴로지의 모든 대역폭 정책 서비스의 상태를 검사할 수 있도록 관리자에게 유용한 리소스가 될 수 있으며, 보다 중요한 점은 네트워크 구성 설정에 정의된 링크에 대한 실시간 대역폭 사용률을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3e0c5-208">대역폭 사용률 분석기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="3e0c5-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-209"><a name="bua"> </a></span></span>

<span data-ttu-id="3e0c5-210">대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크에서 UC 끝점에 의해 대역폭 소비의 다양한 보기에 대한 보고서를 만드는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3e0c5-211">이러한 보고서를 사용하여 현재 대역폭 소비 패턴을 이해하고 대역폭 용량 계획을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-212">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-212">Description</span></span>

<span data-ttu-id="3e0c5-213">대역폭 사용률 분석기는 GUI 기반 응용 프로그램으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="3e0c5-214">이 도구는 네트워크 전체에서 오디오 사용률에 대한 보고서를 생성하며 용량 계획에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="3e0c5-215">또한 다양한 링크에 할당된 대역폭 용량도 같은 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-216">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-216">Output</span></span>

<span data-ttu-id="3e0c5-217">대역폭 사용률 분석기는 시스템에 구성된 모든 WAN 링크에 대한 대역폭 용량 및 오디오 사용률의 그래픽 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-217">Bandwidth Utilization Analyzer provides graphical plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-218">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-218">Purpose</span></span>

<span data-ttu-id="3e0c5-219">음성 및 비디오 배포에서는 엔터프라이즈 네트워크를 통해 미디어 트래픽의 대역폭 사용률 추세를 모니터링하고 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="3e0c5-220">대역폭 사용률 분석기 도구를 사용하면 관리자가 이를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="3e0c5-221">이 도구는 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-221">This tool does the following:</span></span>

- <span data-ttu-id="3e0c5-222">네트워크를 통해 오디오 사용률에 대한 특정 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="3e0c5-223">다양한 링크에 할당된 대역폭 용량에 대한 보다 효과적인 용량 계획 및 이행에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3e0c5-224">대역폭 사용률 분석기는 대역폭 용량 및 사용률 보고서의 그래픽 그림을 생성할 수 있습니다. 이러한 두 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="3e0c5-225">엔터프라이즈 네트워크의 모든 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="3e0c5-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="3e0c5-226">선택한 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="3e0c5-227">링크 용량을 초과하는 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="3e0c5-228">프로비전된 대역폭을 활용하지 않은 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="3e0c5-229">중요한 수준에 도달한 WAN 링크(WAN 링크 대역폭 용량의 90%보다 큰 대역폭 사용률)를 통해 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="3e0c5-230">WAN 링크 유형(네트워크 사이트 링크, 사이트 내의 링크) 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="3e0c5-231">네트워크 지역별로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="3e0c5-232">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3e0c5-232">Applications</span></span>

<span data-ttu-id="3e0c5-233">대역폭 사용률 분석기에는 다음과 같은 두 가지 응용 프로그램(도구)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="3e0c5-234">**WanLinkLogCollector.exe** 이 도구를 사용하면 사용자가 필요한 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="3e0c5-235">**BandwidthUtilizationAnalyzer.xlsm** 스프레드시트 Microsoft Excel 보고서가 자동으로 WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3e0c5-236">이 응용 프로그램을 사용하면 이 문서의 부분에 나와 있는 것 처럼 보고서에 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3e0c5-237">대역폭 사용률 분석기 사용 단계</span><span class="sxs-lookup"><span data-stu-id="3e0c5-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3e0c5-238">대역폭 사용률 분석기를 사용하는 경우 다음 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="3e0c5-239">로그 수집: 로그를 사용하여 WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="3e0c5-239">Collect logs, which are performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="3e0c5-240">m을 사용하여 수행되는 보고서 BandwidthUtilizationAnalyzer.xls사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-240">Customize reports, which are performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3e0c5-241">최종 사용자가 BandwidthUtilizationAnalyzer.xlsm을 수동으로 시작하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3e0c5-242">대역폭 사용률 분석기 시작</span><span class="sxs-lookup"><span data-stu-id="3e0c5-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3e0c5-243">명령 프롬프트에서 WanLinkLogCollector.exe 탐색기를 사용하여 Windows.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="3e0c5-244">**사용 WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="3e0c5-245">다음 세 단계에 따라 다음 세 가지 단계를 WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="3e0c5-246">**시간 표시 막대 기록** 보고서 생성에 필요한 시간 표시 막대 제공</span><span class="sxs-lookup"><span data-stu-id="3e0c5-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="3e0c5-247">**파일렉터리 지정** 파일 위치 정보 제공</span><span class="sxs-lookup"><span data-stu-id="3e0c5-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="3e0c5-248">**로그 수집 및 보고서 뷰어 시작** 명령을 실행하여 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="3e0c5-249">1단계 - 타임라인 기록</span><span class="sxs-lookup"><span data-stu-id="3e0c5-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3e0c5-250">시간 표시 막대를 로깅하면 도구 사용자가 아래 그림과 같이 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="3e0c5-251">**시작 날짜** 보고서가 생성될 시간 표시 막대의 시작 날짜입니다. 예: 2010년 8월 1일</span><span class="sxs-lookup"><span data-stu-id="3e0c5-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="3e0c5-252">**종료 날짜** 보고서가 생성될 시간 표시 막대의 종료 날짜입니다. 예: 2010년 9월 30일</span><span class="sxs-lookup"><span data-stu-id="3e0c5-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![대역폭 사용률 A의 시작 및 종료 날짜](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3e0c5-254">2단계 - 파일렉터리 지정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3e0c5-255">다음과 같은 파일렉터리가 표시된 경우 사용자가 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="3e0c5-256">**서버 로그 파일 위치** 대역폭 정책 서버 로그가 저장되는 폴더 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3e0c5-257">일반적으로 FE \<fileserver\> \\ \<\PDP 중 선택할 \> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="3e0c5-258">**임시 파일 저장소 위치** 보고서를 생성하는 동안 중간 파일이 저장되는 임시 파일 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![대역폭 사용률 Anal의 파일렉터리](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="3e0c5-260">도구 사용자에게 서버 로그 및 임시 파일 저장소 폴더에 대한 파일 액세스 권한이 충분한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3e0c5-261">3단계 - 로그 수집 및 보고서 뷰어 시작</span><span class="sxs-lookup"><span data-stu-id="3e0c5-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3e0c5-262">로그를 수집하고 보고서 뷰어를 시작하려면 아래와 같이 **실행을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="3e0c5-263">이 단계에서는 필요한 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-263">This step collects the required data.</span></span>

![대역폭 사용률 분석에서 데이터 수집](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="3e0c5-265">입력 유효성 검사가 성공하면 아래에 표시된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Bandwidth Utili에서 수집된 알림을 기록합니다.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="3e0c5-267">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-267">Click **OK**.</span></span> <span data-ttu-id="3e0c5-268">BandwidthUtilizationAnalyzer.xlsm이 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="3e0c5-269">메시지 상자의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="3e0c5-270">자세한 내용은 다음 BandwidthUtilizationAnalyzer.xls **m** 사용을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="3e0c5-271">m BandwidthUtilizationAnalyzer.xls사용</span><span class="sxs-lookup"><span data-stu-id="3e0c5-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="3e0c5-272">m BandwidthUtilizationAnalyzer.xls시작하면 아래와 같이 **새로 고침을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="3e0c5-274">파일 폴더가 열리면 consolidated.csv 상자에 지정된 위치에서 파일 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="3e0c5-275">또한 **C:\Temp 로 위치를 표시하기도 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-275">It also shows the location as **C:\Temp**.</span></span>

     ![BandwidthUtilizationAnalyzer에서 폴더 열기](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="3e0c5-277">**가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-277">Click **Import**.</span></span>

4. <span data-ttu-id="3e0c5-278">그래픽 그림이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="3e0c5-279">백그라운드에서 작업 포인터가 사라질 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![보고서 보기에서 필터 적용](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3e0c5-281">보고서 보기에 필터 적용</span><span class="sxs-lookup"><span data-stu-id="3e0c5-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="3e0c5-282">아래와 같이 보고서 보기에 적용할 수 있는 필터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![보고서 보기에서 필터 적용](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="3e0c5-284">**이름** WAN 링크로 필터링합니다(필터가 그래프의 오른쪽에 있습니다).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-284">**Name** Filter by WAN links (the filter is on the right side of the graph).</span></span> <span data-ttu-id="3e0c5-285">이 연결 형식은 다음과 같습니다. 세로(파랑) 상자를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-285">The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="3e0c5-286">**S 사이트** 네트워크 사이트에서 네트워크 지역으로의 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="3e0c5-286">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="3e0c5-287">**IS Inter-Site** 두 네트워크 사이트 간의 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="3e0c5-287">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="3e0c5-288">**R 지역 간** 두 네트워크 지역 간의 WAN 링크</span><span class="sxs-lookup"><span data-stu-id="3e0c5-288">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="3e0c5-289">**제한 초과** 대역폭 사용률이 대역폭 용량보다 큰 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-289">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="3e0c5-290">**중요 수준** 대역폭 사용률이 대역폭 용량보다 90% 이상인 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-290">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="3e0c5-291">**사용률이 언더 활용** 대역폭 사용률이 대역폭 용량의 25% 미만인 WAN 링크로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-291">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="3e0c5-292">**링크 유형** 다음 WAN 링크 유형을 사용하여 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-292">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="3e0c5-293">**네트워크 사이트** 유형</span><span class="sxs-lookup"><span data-stu-id="3e0c5-293">**Network site** type</span></span>

   - <span data-ttu-id="3e0c5-294">**사이트 간** 유형</span><span class="sxs-lookup"><span data-stu-id="3e0c5-294">**Inter-site** type</span></span>

   - <span data-ttu-id="3e0c5-295">**지역 간 링크** 유형</span><span class="sxs-lookup"><span data-stu-id="3e0c5-295">**Inter-Region link** type</span></span>

6. <span data-ttu-id="3e0c5-296">**지역** 네트워크 지역별로 필터링</span><span class="sxs-lookup"><span data-stu-id="3e0c5-296">**Region** Filter by network region</span></span>

<span data-ttu-id="3e0c5-297">다음 그림에서는 앞에서 설명한 필터를 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-297">The following figures show the previously described filters.</span></span>

<span data-ttu-id="3e0c5-298">이름으로 **필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-298">Filter by **Name**.</span></span> <span data-ttu-id="3e0c5-299">그래프에 표시해야 하는 링크 목록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-299">Select the list of links that need to be displayed in the graph.</span></span>

![BandwidthUtilizationAnalyzer의 이름으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="3e0c5-301">제한 **초과로 필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-301">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="3e0c5-302">**True를** 선택하여 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-302">Select **True** to enforce the filter.</span></span>

![제한 초과로 필터링](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="3e0c5-304">위험 **수준으로 필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-304">Filter by **Critical levels**.</span></span> <span data-ttu-id="3e0c5-305">**True를** 선택하여 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-305">Select **True** to enforce the filter.</span></span>

![위험 수준으로 필터링](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="3e0c5-307">**사용률이 언더로 필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-307">Filter by **Under utilized**.</span></span> <span data-ttu-id="3e0c5-308">**True를** 선택하여 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-308">Select **True** to enforce the filter.</span></span>

![사용률이 언더로 필터링](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="3e0c5-310">링크 **유형으로 필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-310">Filter by **Link Type**.</span></span> <span data-ttu-id="3e0c5-311">표시해야 하는 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-311">Select the type or types that need to be displayed.</span></span>

![링크 유형별로 필터링](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="3e0c5-313">지역별로 **필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-313">Filter by **Region**.</span></span> <span data-ttu-id="3e0c5-314">링크를 표시해야 하는 지역 목록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-314">Select a list of regions whose links need to be displayed.</span></span>

![지역별로 필터링](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="3e0c5-316">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-316">Requirements</span></span>

- <span data-ttu-id="3e0c5-317">3..NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e0c5-317">The .NET Framework 3.5</span></span>

- <span data-ttu-id="3e0c5-318">Microsoft Excel 2010 또는 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3e0c5-318">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="3e0c5-319">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-319">Summary</span></span>

<span data-ttu-id="3e0c5-320">대역폭 사용률 분석기는 네트워크를 통해 UC 트래픽에 대한 오디오 대역폭 사용률을 그리기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-320">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="3e0c5-321">이 도구를 사용하여 네트워크의 비디오 대역폭 사용률도 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-321">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="3e0c5-322">통화 파기계</span><span class="sxs-lookup"><span data-stu-id="3e0c5-322">Call Parkometer</span></span>
<span data-ttu-id="3e0c5-323"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-323"><a name="callpark"> </a></span></span>

<span data-ttu-id="3e0c5-324">Call Parkometer는 통화 파크 궤도 데이터베이스에 쉽게 액세스할 수 있도록 하는 명령줄 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-324">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-325">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-325">Description</span></span>

<span data-ttu-id="3e0c5-326">통화 파크로미터는 현재 사용 중인 통화를 추적하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-326">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3e0c5-327">또한 궤도 및 CPS(통화 파기 서버) 사용에 대한 통계도 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-327">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3e0c5-328">이 명령줄 도구는 로컬 또는 원격으로 연결된 컴퓨터에서 CPS SQL Server 데이터베이스에 대한 읽기 및 쓰기 액세스를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-328">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="3e0c5-329">모든 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-329">All options are mutually exclusive.</span></span> <span data-ttu-id="3e0c5-330">명령줄 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-330">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="3e0c5-331">**-o** 매개 변수 - 이 풀에 대해 구성된 모든 궤도 범위를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-331">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="3e0c5-332">**-n** 매개 변수 - 이 풀에서 현재 사용되는 모든 궤도 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-332">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="3e0c5-333">표시되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-333">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3e0c5-334">파기 및 파커의 SIP URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-334">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="3e0c5-335">통화가 진행된 CPS의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-335">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="3e0c5-336">통화가 파기된 시간의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-336">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="3e0c5-337">**-f** 매개 변수 - 풀의 현재 무료 궤도 수를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-337">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="3e0c5-338">**-r \<n\>** 매개 변수 -는 마지막에 \<n\> 사용된 통화를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-338">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3e0c5-339">표시되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-339">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3e0c5-340">Parkee SIP URI.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-340">Parkee SIP URI.</span></span>

  - <span data-ttu-id="3e0c5-341">Parker SIP URI.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-341">Parker SIP URI.</span></span>

  - <span data-ttu-id="3e0c5-342">통화가 진행된 CPS의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-342">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="3e0c5-343">통화를 검색하거나 삭제한 시간의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-343">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="3e0c5-344">**-t \<n\>** 매개 변수 - 할당된 번호의 임의성을 표시하기 위해 데이터베이스에서 궤도의 보존을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-344">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-345">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-345">Output</span></span>

<span data-ttu-id="3e0c5-346">명령 프롬프트에 지정된 입력 매개 변수에 따라 통화 파킹된계에 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-346">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="3e0c5-347">이 풀에 대해 구성된 모든 궤도 범위</span><span class="sxs-lookup"><span data-stu-id="3e0c5-347">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="3e0c5-348">현재 통화가 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-348">Currently parked calls</span></span>

- <span data-ttu-id="3e0c5-349">무료(사용 가능한) 궤도 수</span><span class="sxs-lookup"><span data-stu-id="3e0c5-349">Number of free (available) orbits</span></span>

- <span data-ttu-id="3e0c5-350">최근에 통화가 보행된 경우</span><span class="sxs-lookup"><span data-stu-id="3e0c5-350">Recently parked calls</span></span>

- <span data-ttu-id="3e0c5-351">유니폼 및 임의 궤도 값 테스트용 예약된 궤도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-351">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-352">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-352">Purpose</span></span>

<span data-ttu-id="3e0c5-353">CPS 도구의 목적은 CPS 데이터베이스에 대한 명령줄 액세스를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-353">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="3e0c5-354">관리자는 CPS 사용을 보고 풀에 할당된 궤도 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-354">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-355">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-355">Requirements</span></span>

<span data-ttu-id="3e0c5-356">CPS를 실행하는 동일한 컴퓨터에서 이 도구를 실행하면 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-356">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3e0c5-357">이 도구를 원격 컴퓨터에서 실행하면 SQL Server 2015에서 사용하는 비즈니스용 Skype 서버 데이터베이스를 원격 액세스를 허용하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-357">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="3e0c5-358">풀의 서버에 연결하려면 SQL Server 연결 문자열을 사용하여 통화 파기계를 구성해야 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-358">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="3e0c5-359">이 SQL Server 연결 문자열은 의 구성 **파일에 정의되어parkometer.exe.config.** 이 디렉터리는 서버가 있는 동일한 디렉터리에 parkometer.exe 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-359">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3e0c5-360">다음 XML 파일은 파일 형식의 parkometer.exe.config. 구성해야 하는 매개 변수는 사용자 이름(예: mydomain\Administrator), 암호(예: mypassword) 및 호스트 이름(예: myserver)입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-360">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="3e0c5-361">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-361">Examples</span></span>

<span data-ttu-id="3e0c5-362">배포된 선불 범위: -o 매개 변수는 표시된 것 같이 이 풀에 대해 구성된 모든 궤도 범위를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-362">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![통화 파기계의 파기 범위입니다.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="3e0c5-364">현재 보류된 통화: -n 매개 변수는 표시된 것 같이 이 풀에서 현재 사용된 모든 파행 통화를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-364">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Call Parkometer의 현재 파크된 통화입니다.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="3e0c5-366">무료 궤도 수: -f 매개 변수는 표시된 것 같이 풀의 현재 무료 궤도 수를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-366">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Call Parkometer의 무료 궤도입니다.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="3e0c5-368">최근에 사용된 통화: -r 매개 변수에 표시된 마지막에 사용된 \<n\> \<n\> 통화가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-368">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![통화 파기계의 최근 통화 수입니다.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="3e0c5-370">테스트 궤도 예약: -t 매개 변수는 다음과 같이 데이터베이스에서 궤도 \<n\> 예약을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Call Parkometer에서 파주 궤도 예약을 테스트합니다.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="3e0c5-372">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-372">Summary</span></span>

<span data-ttu-id="3e0c5-373">Call Parkometer는 통화 파크 서버에 대한 자세한 정보를 제공하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-373">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="3e0c5-374">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3e0c5-374">DBAnalyze</span></span>
<span data-ttu-id="3e0c5-375"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-375"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-376">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-376">Description</span></span>

<span data-ttu-id="3e0c5-377">DBAnalyze는 관리자가 2015 데이터베이스의 분석 보고서를 수집하는 데 도움이 되는 비즈니스용 Skype 서버 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-377">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="3e0c5-378">DBAnalyze에는 진단, 사용자 데이터, 회의, MUS 및 디스크 조각화 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-378">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="3e0c5-379">**진단 모드** 테이블에 대한 정보(레코드 수, 조각화, 데이터 크기 및 로그 파일 크기, 마지막 백업 시간, Microsoft Office Communications Server를 실행하는 서버 간 연락처 배포, 평균 사용 권한 수, 연락처, 컨테이너, 구독, 게시, 사용자당 끝점, 부적절한 홈 사용자, 라우팅할 수 없는 사용자, 사용자당 구성되는 평균 회의 수, 예약된 회의, 활성 회의 및 데이터베이스 버전.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-379">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e0c5-380">진단 모드를 실행하면 서버 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-380">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="3e0c5-381">**사용자 데이터 모드** 지정된 사용자 또는 해당 사용자가 연락처 및 사용 권한 목록에 있는 사용자에 대한 연락처, 컨테이너, 구독, 게시, 사용 권한 및 연락처 그룹 데이터를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-381">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3e0c5-382">또한 이 모드는 사용자가 구성하거나 초대하는 회의에 대한 요약 데이터를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-382">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="3e0c5-383">**회의 모드** 회의의 모든 일정 시간 세부 정보, 초대 대상자 목록, 회의에 허용되는 미디어 유형 목록, 활성 MUS(다중 포인트 제어 단위), 활성 참가자 목록 및 각 참가자의 신호 상태를 포함하여 특정 회의에 대한 자세한 데이터를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-383">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="3e0c5-384">**모임 ID 디코드** **/pstnid** 스위치에 의해 지정되지만 자세한 정보를 위해 백 엔드에 연결되지 않는 PSTN(Public Switched Telephone Network) 모임 ID를 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-384">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="3e0c5-385">**회의 해결** **/pstnid** 스위치에 지정된 PSTN 모임 ID를 디코딩하고 ID로 표시된 회의에 대한 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-385">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="3e0c5-386">**MUS 모드** 풀의 각 MCU에 대한 ID, 미디어 유형, URL, 하트비트 상태, 회의 부하 및 참가자 부하를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-386">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="3e0c5-387">**디스크 조각화 모드** 모든 디스크의 조각화 상태를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-387">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="3e0c5-388">이 도구를 사용하여 다양한 문제를 진단하거나 관리자의 용량 계획을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-388">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="3e0c5-389">예를 들어 서버 A에 있는 대부분의 사용자가 서버 B에 있는 사용자를 연락처로 선택하는 경우 관리자는 서버 A의 사용자를 서버 B로 이동하여 서버 간 트래픽을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-389">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-390">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-390">Output</span></span>

<span data-ttu-id="3e0c5-391">이 도구는 2015 데이터베이스의 미리 비즈니스용 Skype 서버 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-391">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="3e0c5-392">**경로**: %ProgramFiles%\비즈니스용 Skype 서버 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="3e0c5-392">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-393">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-393">Purpose</span></span>

<span data-ttu-id="3e0c5-394">설치 Dbanalyze.exe 로컬 폴더에 복사한 다음 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-394">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3e0c5-395">이 도구를 사용하려면 명령줄에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-395">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="3e0c5-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 명령줄 옵션에 대한 설명은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![명령줄 옵션의 Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="3e0c5-398">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-398">Requirements</span></span>

 <span data-ttu-id="3e0c5-399">**컴퓨터** DBAnalyze는 2015가 설치된 도메인에 가입된 컴퓨터에서만 비즈니스용 Skype 서버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-399">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="3e0c5-400">**네트워크** 컴퓨터가 백 엔드 데이터베이스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-400">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="3e0c5-401"> DBAnalyze를 비즈니스용 Skype 서버 2015 소프트웨어 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-401">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="3e0c5-402">**사용자** 아래 표에는 2015 데이터베이스 액세스에 필요한 권한이 있는 관리자가 비즈니스용 Skype 서버 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-402">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![사용 권한 테이블의 Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="3e0c5-404">**/report:disk** 모드에는 로컬 관리자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-404">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-405">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-405">Examples</span></span>

<span data-ttu-id="3e0c5-406">다음은 유효한 Dbanalyze.exe 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-406">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="3e0c5-407">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-407">Summary</span></span>

<span data-ttu-id="3e0c5-408">DBAnalyzer는 관리자에게 2015 데이터베이스를 빠르고 비즈니스용 Skype 서버 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-408">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="3e0c5-409">서비스 Storage 가져오기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-409">Import Storage Service Data</span></span>
<span data-ttu-id="3e0c5-410"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-410"><a name="Issd"> </a></span></span>

<span data-ttu-id="3e0c5-411">ImportStorageServiceData 리소스 키트 도구를 사용하면 LYSS(Storage Service)에서 플러시된 큐 및 끝점 데이터를 다시 Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-411">The ImportStorageServiceData resource kit tool allows for reimporting Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-412">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-412">Description</span></span>

<span data-ttu-id="3e0c5-413">Storage 서비스에서 플러시된 데이터는 큐 항목 상태 또는 데이터베이스 크기에 따라 자동(주기적)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-413">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3e0c5-414">풀 장애 조치(failover) cmdlet 또는 풀 장애 조치(failover) cmdlet이 호출하는 StorageServiceFullFlush cmdlet의 수동 호출로 인해 이 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-414">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3e0c5-415">프런트 엔드의 LYSS(Storage Service) 데이터베이스 크기가 정상 수준보다 크면 데이터가 더 많이 내보내질 수 있기 때문에 데이터를 다시 전송하지 않는 것이 이상적입니다. 또한 오류로 인해 Storage 서비스 큐가 커질 수 있는 모든 문제를 먼저 해결해야 합니다(예: Exchange 끝점 오류, 네트워크 문제 또는 기타 문제).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-415">Note that data should ideally not be reimported if any of the Storage Service (LYSS ) database sizes on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems that could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="3e0c5-416">**시나리오 1:** 풀 장애 조치(failover) 중에 각 프런트 엔드에 대해 저장소 서비스에서 파일이 플러시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-416">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3e0c5-417">장애 조치(failover)가 완료되면 도구를 실행하여 데이터를 다시 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-417">After failover is completed, the tool should be run to reimport the data.</span></span>

 <span data-ttu-id="3e0c5-418">**시나리오 2:** 데이터가 매일 자동으로 플러시되거나 Storage 서비스 데이터베이스가 특정 크기 임계값을 초과하는 경우(예: 60%, 80%, 90% 전체)에 대한 응답으로 데이터가 플러시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-418">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds (for example 60%, 80%, 90% full).</span></span> <span data-ttu-id="3e0c5-419">이 자동 플러시된 데이터는 관리자가 정기적으로 다시 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-419">This automatically flushed data should be reimported routinely by the administrator.</span></span> <span data-ttu-id="3e0c5-420">위의 상황에서는 모니터링 SCOM 팩이 배포되지 않은 경우 비즈니스용 Skype 서버 Storage 서비스에서 플러시되는 데이터와 관련된 Storage 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-420">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3e0c5-421">32075(전체 플러시 작업이 시작), 32076(전체 플러시가 완료되었습니다), 32082(유지 관리 수준 플러시 시작), 32083(유지 관리 수준 플러시 완료), 32089(데이터베이스 채우기 때문에 플러시가 발생)</span><span class="sxs-lookup"><span data-stu-id="3e0c5-421">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3e0c5-422">이러한 이벤트 ID는 RTM 릴리스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-422">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3e0c5-423">관리자가 이러한 이벤트를 볼 때 플러시된 파일이 있는 것입니다. 이 데이터는 이 도구를 사용하여 정기적으로 다시 가져와야 합니다(예: 주 1회).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-423">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="3e0c5-424">온라인 서비스 릴리스의 경우 비즈니스용 Skype 서버 상태 모니터링 SCOM 팩이 배포된 경우 관리자가 플러시된 데이터를 다시 Storage 서비스로 다시 보내야 하는 새로운 경고가 Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-424">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts that may be raised which ask the administrator to reimport the flushed data back into Storage Service.</span></span> <span data-ttu-id="3e0c5-425">경고를 트리거한 서버의 이벤트 로그에 Front-End 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-425">There will be a corresponding event in the event log on the Front-End server that triggered the alert.</span></span> <span data-ttu-id="3e0c5-426">이 이벤트는 플러시된 데이터 파일이 있는 상위 경로와 경고 조건을 충족하는 파일의 수에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-426">The event will give a description of the Parent path under which the flushed data files are located, and how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3e0c5-427">경고 조건은 적어도 Y일이 지난 특정 상위 경로 아래에 X 이상의 파일이 있는 것입니다. 여기서 X와 Y는 StorageService 내에 미리 설정되지만 APPCONFIG 파일을 변경하여 다시 정의할 수 있습니다. 상태 경고를 트리거할 수 있는 이벤트의 두 가지 예는 다음과 같습니다. 차이점은 부모 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-427">The alert criteria is that there are X or more files under the particular parent path that are at least Y days old (where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events that can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3e0c5-428">한 가지 가능성은 웹 서비스 파일 공유에 있는 반면 다른 하나는 각 프런트 엔드의 로컬 응용 프로그램 데이터 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-428">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3e0c5-429">(예: c:\ProgramData\Microsoft\비즈니스용 Skype 서버 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-429">(for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span></span> <span data-ttu-id="3e0c5-430">그런 다음 관리자가 이 Reskit 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-430">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="3e0c5-431">이 도구는 도구가 실행되는 프런트 엔드가 데이터를 소유하지 않은 경우 실행 중인 프런트 엔드 및 기타 프런트 엔드에서 CPU 및 IO 부하를 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-431">This tool will increase CPU and IO load on the front end it is running on, and other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3e0c5-432">프런트 엔드가 CPU 및 IO 부하가 과도하지 않은 경우(예: 사용량이 많은 시간 외) 이 도구를 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-432">We recommend running this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3e0c5-433">둘째, 이 도구는 데이터 파일을 하나 가져오는 데 2~3분 정도 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-433">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3e0c5-434">도구가 실행되는 기간을 예측할 때 이 사실에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-434">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="3e0c5-435">도구에서 생성된 verbose 로그 파일은 기본적으로 파일 저장소에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-435">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3e0c5-436">로그 파일이 10MB 이상일 수 있기 때문에 보고된 오류가 없는 경우 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-436">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![예제 Storage 서버 이벤트 로그 이벤트입니다.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="3e0c5-438">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-438">Requirements</span></span>

<span data-ttu-id="3e0c5-439">비즈니스용 Skype 서버 2015 Resource Kit 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-439">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="3e0c5-440">이 도구는 도메인에 가입된 컴퓨터에 비즈니스용 Skype 서버 관리 비즈니스용 Skype 서버 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-440">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="3e0c5-441">이 도구는 관리 셸의 cmdlet을 사용하여 풀의 모든 Front-End 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-441">The tool uses a cmdlet from the management shell to identify all the Front-End servers in the pool.</span></span> <span data-ttu-id="3e0c5-442">둘째, **RtcLocal** 데이터베이스가 설치된 풀의 컴퓨터로부터 도구를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-442">Secondly, the tool must be executed from a machine in the pool that has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3e0c5-443">이 데이터베이스는 도구에서 풀에 대한 WEBSERVICE 파일 공유의 위치를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-443">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="3e0c5-444">또한 각 Front-End 서버는 먼저 각 Front-End 서버와 도구가 실행되는 컴퓨터의 **Enable-PSRemoting을** 사용하여 Windows PowerShell Remoting을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-444">Additionally, before using the tool, each Front-End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front-End server, and the machine that the tool is executed from.</span></span> <span data-ttu-id="3e0c5-445">그렇지 않으면 Windows PowerShell 원격 액세스 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-445">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3e0c5-446">Windows PowerShell 리모트는 완료된 후 Front-End 모든 서버의 모든 서버에서 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-446">Windows PowerShell Remoting can be turned off on all Front-End servers in the pool after it is finished.</span></span> <span data-ttu-id="3e0c5-447">마지막으로 도구를 호출하는 계정 또는 자격 증명에는 이 도구를 실행하고 있는 풀의 웹 서비스 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-447">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3e0c5-448">그렇지 않으면 IO 사용 권한 오류로 도구가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-448">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0c5-449">이 Windows Server 2012 Windows PowerShell Remoting은 기본적으로 사용되지만 Windows Server 2008 운영 체제에서는 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-449">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-450">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-450">Examples</span></span>

```console
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
```

## <a name="lcssync"></a><span data-ttu-id="3e0c5-451">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3e0c5-451">LCSSync</span></span>
<span data-ttu-id="3e0c5-452"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-452"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="3e0c5-453">LCSSync 도구를 사용하면 다중 포리스트 환경에 비즈니스용 Skype 서버 2015 통신 소프트웨어를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-453">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3e0c5-454">이 도구는 Active Directory 도메인 서비스 연락처 개체로 서로 다른 사용자 포리스트의 사용자 및 그룹을 2015 또는 2015가 설치된 중앙 비즈니스용 Skype 서버 동기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-454">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-455">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-455">Description</span></span>

 <span data-ttu-id="3e0c5-456">LCSSync는 중앙 포리스트의 동기화된 Active Directory 도메인 서비스 연락처 개체를 사용하여 사용자가 동기화된 Active Directory 도메인 서비스 연락처 개체를 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-456">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="3e0c5-457">단일 로그인을 제공하려면 기본 사용자 계정이 2015년 10월에 대한 중앙 포리스트의 Active Directory 도메인 서비스 연락처 개체에 비즈니스용 Skype 서버 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-457">To provide single sign in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="3e0c5-458">이 도구는 해당 매핑을 수행하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-458">This tool helps perform that mapping.</span></span> <span data-ttu-id="3e0c5-459">이 도구는 Microsoft Identity Integration Server에서 관리 에이전트를 만들기 위한 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-459">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="3e0c5-460">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-460">Summary</span></span>

<span data-ttu-id="3e0c5-461">LCSSync 도구를 사용하면 다중 포리스트 환경에 비즈니스용 Skype 서버 2015를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-461">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="3e0c5-462">사용자 콘솔 룩업</span><span class="sxs-lookup"><span data-stu-id="3e0c5-462">Lookup User Console</span></span>
<span data-ttu-id="3e0c5-463"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-463"><a name="LUC"> </a></span></span>

<span data-ttu-id="3e0c5-464">LookupUserConsole 도구는 특정 사용자에 대한 비즈니스용 Skype 서버 라우팅 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-464">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="3e0c5-465">이 정보는 배포 및 라우팅 문제를진단하는 데 개인을 지원하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-465">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-466">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-466">Description</span></span>

 <span data-ttu-id="3e0c5-467">이 LookupUserConsole.exe 실행하면 SIP 주소를 수락하고 해당 주소와 관련된 내부 비즈니스용 Skype 서버 정보를 표시하려고 하는 명령 프롬프트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-467">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="3e0c5-468">**exit를** 입력하여 LookupUserConsole 도구를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-468">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-469">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-469">Requirements</span></span>

<span data-ttu-id="3e0c5-470">비즈니스용 Skype 서버 2015 Resource Kit를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-470">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3e0c5-471">이 도구는 도메인에 가입된 컴퓨터에 비즈니스용 Skype 서버 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-471">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-472">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-472">Examples</span></span>

<span data-ttu-id="3e0c5-473">C:\Program Files\비즈니스용 Skype 서버 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="3e0c5-473">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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
```

## <a name="msturnping"></a><span data-ttu-id="3e0c5-474">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3e0c5-474">MsTurnPing</span></span>
<span data-ttu-id="3e0c5-475"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-475"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="3e0c5-476">MSTurnPing 도구를 사용하면 비즈니스용 Skype 서버 2015 통신 소프트웨어의 관리자가 오디오/비디오 에지, 오디오/비디오 인증 서비스를 실행하는 서버 및 토폴로지에서 대역폭 정책 서비스를 실행하는 서버의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-477">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-477">Description</span></span>

<span data-ttu-id="3e0c5-478">MSTurnPing 도구를 사용하면 비즈니스용 Skype 서버 2015 통신 소프트웨어의 관리자가 오디오/비디오 에지, 오디오/비디오 인증 서비스를 실행하는 서버 및 토폴로지에서 대역폭 정책 서비스를 실행하는 서버의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-478">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="3e0c5-479">관리자는 이 도구를 사용하여 다음 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-479">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="3e0c5-480">A/V 에지 서버 테스트: 이 도구는 다음을 수행하여 토폴로지의 모든 A/V 에지 서버에 대해 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-480">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="3e0c5-481">오디오/비즈니스용 Skype 서버 인증 서비스가 시작되어 적절한 자격 증명을 발급할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3e0c5-481">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3e0c5-482">오디오/비즈니스용 Skype 서버 에지 서비스가 시작되어 외부 에지의 리소스를 할당할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3e0c5-482">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="3e0c5-483">대역폭 정책 서비스 테스트: 이 도구는 토폴로지에서 대역폭 정책 서비스를 실행하는 모든 서버에 대해 다음을 수행하여 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-483">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="3e0c5-484">비즈니스용 Skype 서버 대역폭 정책 서비스(인증)가 시작되어 적절한 자격 증명을 발급할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3e0c5-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3e0c5-485">비즈니스용 Skype 서버 대역폭 정책 서비스(핵심)가 시작되어 대역폭 검사를 성공적으로 수행할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3e0c5-485">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="3e0c5-486">이 도구는 토폴로지의 일부이자 로컬 저장소가 설치된 컴퓨터에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-486">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-487">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-487">Output</span></span>

<span data-ttu-id="3e0c5-488">이 도구는 각 작업의 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-488">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="3e0c5-489">**AudioVideoEdgeServer** 테스트가 수행되는 경우 도구 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-489">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3e0c5-490">토폴로지에서 비즈니스용 Skype 서버/비디오 인증 서비스를 제공하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="3e0c5-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="3e0c5-491">토폴로지에서 비즈니스용 Skype 서버 2015 오디오/비디오 에지 서비스를 제공하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="3e0c5-491">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="3e0c5-492">**BandwidthPolicyServer** 테스트를 수행하면 도구 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-492">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3e0c5-493">토폴로지에서 비즈니스용 Skype 서버 2015 대역폭 정책 서비스(인증)를 제공하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="3e0c5-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="3e0c5-494">토폴로지에서 비즈니스용 Skype 서버 2015 대역폭 정책 서비스(Core)를 제공하는 컴퓨터의 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="3e0c5-494">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-495">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-495">Requirements</span></span>

- <span data-ttu-id="3e0c5-496">이 도구는 토폴로지에 있으며 로컬 저장소가 있는 컴퓨터에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-496">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="3e0c5-497">로컬 저장소에 액세스할 수 있는 관리자 권한으로 도구를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-497">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-498">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-498">Examples</span></span>

<span data-ttu-id="3e0c5-499">다음은 도구 입력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-499">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="3e0c5-500">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-500">Summary</span></span>

<span data-ttu-id="3e0c5-501">이 도구는 오디오/비디오 및 대역폭 정책 서비스를 비즈니스용 Skype 서버 서버의 상태를 확인하려는 2015 관리자에게 유용한 리소스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-501">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="3e0c5-502">네트워크 구성 뷰어</span><span class="sxs-lookup"><span data-stu-id="3e0c5-502">Network Configuration Viewer</span></span>
<span data-ttu-id="3e0c5-503"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-503"><a name="NCV"> </a></span></span>

<span data-ttu-id="3e0c5-504">네트워크 구성 뷰어는 비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자가 지정된 대역폭 용량에 따라 음성 또는 화상 통화와 같은 실시간 통신 세션을 허용하도록 프로비전된 엔터프라이즈의 CAC(통화 허용 제어) 네트워크 토폴로지 보기에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-504">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3e0c5-505">비즈니스용 Skype 서버 2015 관리자는 2015와 함께 설치되는 대역폭 정책 서비스에서 적용하는 CAC 정책을 비즈니스용 Skype 서버 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-505">Skype for Business Server 2015 administrators defines CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-506">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-506">Description</span></span>

<span data-ttu-id="3e0c5-507">네트워크 구성 뷰어(NetworkConfigurationViewer.exe)를 사용하면 관리자가 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="3e0c5-508">비즈니스용 Skype 서버 2015 배포에서 그래픽 형식으로 CAC 네트워크 토폴로지 로드 및 보기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-508">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="3e0c5-509">대역폭 정책 서버 로그 파일에서 그래픽 형식으로 CAC 네트워크 토폴로지 로드 및 보기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-509">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="3e0c5-510">CAC 네트워크 토폴로지 저장 및 디스크에 XML 형식으로 저장</span><span class="sxs-lookup"><span data-stu-id="3e0c5-510">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="3e0c5-511">CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-511">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="3e0c5-512">CAC 네트워크 토폴로지 구성 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-512">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="3e0c5-513">트리 보기 스타일로 CAC 네트워크 토폴로지 보기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-513">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="3e0c5-514">CAC 네트워크 토폴로지 링크에 대한 사용자 지정 커넥터(예: 사이트-지역, 지역-지역 및 사이트-사이트 링크)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-514">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="3e0c5-515">CAC 네트워크 토폴로지 사이트 정보, 지역 정보 및 프로비전된 대역폭 정책 및 네트워크 링크를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-515">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-516">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-516">Purpose</span></span>

<span data-ttu-id="3e0c5-517">그래픽 인터페이스에서 엔터프라이즈 CAC 네트워크 토폴로지 링크를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-517">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-518">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-518">Examples</span></span>

 <span data-ttu-id="3e0c5-519">**비즈니스용 Skype 서버 2015** 배포에서 그래픽 형식으로 CAC 네트워크 토폴로지 로드 및 보기: 비즈니스용 Skype 서버 2015 관리자는 아래 그림과 같이 네트워크 구성 다운로드 옵션을 사용하여 비즈니스용 Skype 서버 2015 컴퓨터에서 CAC 네트워크 토폴로지 구성을 로드하고 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3e0c5-519">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3e0c5-520">이 도구는 비즈니스용 Skype 서버 구성 저장소에 연결되지 않은 컴퓨터에 배포된 경우 이러한 구성을 다운로드하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-520">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![네트워크 구성 다운로드](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="3e0c5-522">대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지 로드 및 **보기:** 비즈니스용 Skype 서버 2015 대역폭 정책 서버는 CAC 네트워크 토폴로지가 비즈니스용 Skype 서버 2015 파일 공유 위치의 로깅 메커니즘의 일부로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-522">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers saves the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="3e0c5-523">비즈니스용 Skype 서버 2015 관리자는 아래와 같이 네트워크 구성 열기 옵션을  사용하여 이러한 파일을 그래픽 형식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-523">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![대역폭 정책 서버 로그 파일 열기](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="3e0c5-525">CAC 네트워크 토폴로지 저장 및 저장: 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 네트워크 구성 복사본 저장 옵션을 사용하여 CAC 네트워크 토폴로지 구성 파일을 XML 형식으로 저장할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3e0c5-525">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3e0c5-526">저장된 구성 파일은 그래픽 보기를 위해 오프라인으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-526">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![네트워크 구성을 XML 파일로 저장](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="3e0c5-528">JPG 또는 BMP 형식으로 CAC 네트워크 토폴로지 다이어그램 저장 및 저장: 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 네트워크 구성 저장 옵션을 그림으로 사용하여  CAC 네트워크 토폴로지 구성을 JPG 및 BMP 파일 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-528">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![네트워크 구성을 그림으로 저장](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="3e0c5-530"><strong>CAC</strong>네트워크 토폴로지 구성 데이터 보기: 비즈니스용 Skype 서버 2015 관리자는 아래 표시된 네트워크 구성 데이터 보기 옵션을 사용하여 네트워크 지역, 네트워크 사이트, 대역폭 프로필 및 사이트 서브넷 IP 주소와 같은 관련 네트워크 구성 데이터를 텍스트 형식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-530"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![네트워크 구성 데이터 보기](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="3e0c5-532">트리 보기 스타일로 CAC 네트워크 토폴로지 **보기:** 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 도구 창의 왼쪽에 있는 제어판을 사용하여 관련 네트워크 구성 데이터를 그래픽 트리 보기 스타일로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-532">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![트리 보기에서 네트워크 구성 데이터 보기](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="3e0c5-534">**CAC** 네트워크 토폴로지 링크(예: 사이트-지역, 지역-지역 및 사이트-사이트 링크)에 대한 사용자 지정 커넥터 정의: 비즈니스용 Skype 서버 2015 관리자는 아래 표시된 설정 옵션을 사용하여 CAC 네트워크 구성 WAN 링크에 대한 사용자 지정 그래픽 커넥터를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-534">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3e0c5-535">이렇게 하면 네트워크 구성에 프로비전되는 다양한 유형의 네트워크 링크를 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-535">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![도구](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="3e0c5-537">**CAC 네트워크** 토폴로지 사이트 정보, 지역 정보 및 프로비전된 대역폭 정책 보기: 비즈니스용 Skype 서버 2015 관리자는 아래 표시된 옵션을 사용하여 관련 CAC 네트워크 지역 정보, 사이트 정보 및 CAC 대역폭 프로비전 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-537">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3e0c5-538">예를 들어 네트워크 지역 **또는** 네트워크 사이트 개체에서 정보를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-538">(For example, click **Info** in a network region or network site object.)</span></span>

![네트워크에 대한 사용자 지정 커넥터 정의](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="3e0c5-540">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-540">Summary</span></span>

<span data-ttu-id="3e0c5-541">이 도구는 배포에 대한 CAC 네트워크 비즈니스용 Skype 서버 그래픽 형식으로 보고자 하는 2015 관리자에게 유용한 리소스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-541">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="3e0c5-542">응답 그룹 에이전트 Live</span><span class="sxs-lookup"><span data-stu-id="3e0c5-542">Response Group Agent Live</span></span>
<span data-ttu-id="3e0c5-543"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-543"><a name="RGAL"> </a></span></span>

<span data-ttu-id="3e0c5-544">응답 그룹 응용 프로그램을 사용하면 에이전트가 기본 제공 웹 서비스를 사용하여 유용한 실시간 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-544">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3e0c5-545">안타깝게도 이 데이터의 그래픽 보기는 응용 프로그램 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-545">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3e0c5-546">응답 그룹 에이전트 Live Resource Kit 도구는 이 정보에 액세스할 수 있는 간단하고 그래픽적인 방법을 제공하여 다른 에이전트의 존재와 같은 실시간 비즈니스용 Skype 소프트웨어 정보로 개선하여 이 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-546">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-547">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-547">Description</span></span>

<span data-ttu-id="3e0c5-548">응답 그룹 에이전트 Live는 Windows 에이전트에 로그인 및 로그인 기능과 일부 실시간 정보(예: 그룹 구성원 및 현재 통화 수)를 제공하는 Windows 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-548">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3e0c5-549">이 페이지는 에이전트 그룹 페이지의 고급 버전(에이전트 그룹 페이지에서 액세스할 수 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-549">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-550">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-550">Purpose</span></span>

<span data-ttu-id="3e0c5-551">응답 그룹 응용 프로그램은 들어오는 호출을 큐에 대기한 다음 에이전트 그룹으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-551">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="3e0c5-552">서비스 호출에 대한 정보를 결정하기 위해 에이전트는 사용 가능한 다른 에이전트 및 각 큐에서 대기 중인 통화 수와 같은 에이전트 그룹에 대한 실시간 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-552">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="3e0c5-553">처음에 응답 그룹 서비스를 통해서만 액세스할 수 있는 이 정보는 응답 그룹 에이전트 Live에서 직관적인 방식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-553">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="3e0c5-554">기능</span><span class="sxs-lookup"><span data-stu-id="3e0c5-554">Features</span></span>

<span data-ttu-id="3e0c5-555">응답 그룹 에이전트 라이브 도구는 응답 그룹 서비스 및 2015 비즈니스용 Skype 서버 SDK를 사용하여 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-555">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="3e0c5-556">응답 그룹 에이전트는 응답 그룹 서비스에서 사용할 수 있는 정보 및 기능(예: 그룹 구성원, 다른 에이전트의 현재 상태 및 대기 전화 수)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-556">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="3e0c5-557">아래 그림에서는 응답 그룹 에이전트 Live의 기본 인터페이스를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-557">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![응답 그룹 에이전트 라이브 도구입니다.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="3e0c5-559">응답 그룹 에이전트 Live의 에이전트는 다음과 같은 세 가지 주요 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-559">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="3e0c5-560">**로그인/아웃:** 에이전트 그룹 페이지(비즈니스용 Skype 서버 2015에서 액세스할 수 있는)와는 다른 응답 그룹 에이전트 Live를 사용하면 에이전트만 한에 모든 에이전트 그룹에 로그인하거나 그룹에서 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-560">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign in or out of all agent groups at once.</span></span> <span data-ttu-id="3e0c5-561">이 응용 프로그램은 에이전트가 로그인 또는 아웃할 수 있는 세 가지 빠른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-561">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="3e0c5-562">응용 프로그램 내에서 로그인/아웃(녹색 및 빨간색) 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-562">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="3e0c5-563">시스템 트레이 아이콘을 마우스 오른쪽 단추로 클릭하고 로그인 또는 로그인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-563">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="3e0c5-564">구성 가능한 바로 가기 키 사용</span><span class="sxs-lookup"><span data-stu-id="3e0c5-564">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="3e0c5-565">**그룹 구성원 자격:** 에이전트 그룹을 선택하면 응답 그룹 에이전트 Live의 오른쪽 창에 이 그룹의 에이전트 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-565">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3e0c5-566">비즈니스용 Skype 서버 2015가 이 응용 프로그램과 동일한 컴퓨터에서 실행 중인 경우 현재 상태 정보 및 연락처 카드가 응답 그룹 에이전트 Live에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-566">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3e0c5-567">에이전트는 IM을 보내거나 다른 에이전트에게 직접 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-567">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="3e0c5-568">**실시간 통계:** 응답 그룹 에이전트 Live는 모든 에이전트 그룹에 대한 실시간 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-568">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="3e0c5-569">업데이트 빈도는 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-569">The update frequency is one minute.</span></span> <span data-ttu-id="3e0c5-570">응답 그룹이 전화를 걸면 현재 대기 중인 통화 수를 사용하여 그룹 이름 옆에 시각적 표시기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-570">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="3e0c5-571">그룹 위에 포인터를 비우면 대기 시간이 가장 긴 시간도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-571">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-572">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-572">Requirements</span></span>

<span data-ttu-id="3e0c5-573">응답 그룹 에이전트 Live를 사용하려면 .NET Framework 4.0이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-573">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3e0c5-574">또한 현재 상태 및 연락처 카드 기능을 활용하려면 비즈니스용 Skype 설치해야 합니다(실행 중).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-574">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="3e0c5-575">구성</span><span class="sxs-lookup"><span data-stu-id="3e0c5-575">Configuration</span></span>

<span data-ttu-id="3e0c5-576">응답 그룹 에이전트 Live는 응용 프로그램의 옵션 대화 상자를 사용하여 개별 기본 설정으로 사용자 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-576">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="3e0c5-577">또한 관리자가 기본 호스트 주소의 defaultHostAddress 속성을 직접 편집하여 기본 호스트 주소를 정의할 RGAgentLive.exe.config 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-577">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="3e0c5-578">아래 그림에서는 에이전트가 호스트 주소 및 바로 가기 키를 구성하는 데 사용할 수 있는 옵션 대화 상자를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-578">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="3e0c5-579">이 대화 상자는 주 인터페이스의 오른쪽 위에 있는 옵션 단추를 클릭하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-579">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![응답 그룹 에이전트 라이브 옵션 대화 상자입니다.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="3e0c5-581">응답 그룹 에이전트 Live 구성에서 다음과 같은 세 가지 설정을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-581">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="3e0c5-582">호스트 주소: 일반적으로 에이전트의 홈 풀에 속하는 웹 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-582">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="3e0c5-583">정확한 응답 그룹 서비스 주소는 호스트 다음에 올바른 경로를 추가하여 이 정보에서 백그라운드에서 자동으로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-583">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="3e0c5-584">바로 가기: 로그인/아웃하기 위한 정확한 바로 가기를 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-584">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="3e0c5-585">유일한 제한은 두 바로 가기 모두 "Windows 로고" 키와 함께 다른 키가 포함되어야 하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-585">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="3e0c5-586">시작 Windows: 응용 프로그램을 자동으로 시작하도록 구성할 수 Windows.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-586">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-587">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-587">Examples</span></span>

<span data-ttu-id="3e0c5-588">아래 그림에서는 오른쪽 창에서 연락처를 마우스 오른쪽 단추로 클릭하여 다른 에이전트에게 IM을 호출하거나 보내는 방법을 보여 주는 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-588">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![전화 걸기 또는 IM 보내기](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="3e0c5-590">아래 그림에서는 응답 그룹 에이전트 Live에서 큐의 현재 통화 수와 이러한 모든 수신 전화 중에서 대기 시간이 가장 긴 시간을 표시하는 방법을 보여 주는 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-590">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![큐 정보 보기](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="3e0c5-592">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-592">Summary</span></span>

<span data-ttu-id="3e0c5-593">빠른 로그인 및 로그인, 그룹 구성원 자격 및 기본 실시간 통계는 응답 그룹 서비스에서 응용 프로그램 외부에서만 사용할 수 있는 흥미로운 응답 그룹 에이전트 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-593">Fast sign in and sign out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3e0c5-594">응답 그룹 에이전트 Live Resource Kit 도구를 사용하여 비즈니스용 Skype 서버 2015 관리자는 에이전트에 보다 빠르고 그래픽적인 방식으로 작업을 수행할 수 있는 Windows 응용 프로그램을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-594">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="3e0c5-595">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3e0c5-595">SEFAUtil</span></span>
<span data-ttu-id="3e0c5-596"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-596"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="3e0c5-597">SEFAUtil(보조 확장 기능 활성화)은 비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자 및 지원팀 에이전트가 비즈니스용 Skype 서버 2015 사용자를 대신하여 위임 벨 울림, 통화 전달, 동시 전화 울림, 팀 통화 설정 및 그룹 통화 pickup을 구성할 수 있도록 하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-597">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3e0c5-598">또한 관리자는 이 도구를 사용하여 특정 사용자에 대해 게시된 통화 라우팅 설정을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-598">The tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="3e0c5-599">관리자는 SEFAUtil 도구를 사용하여 사용자를 대신하여 통화 전달 또는 동시 전화 울림을 사용하거나 사용하지 않도록 설정/수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-599">The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3e0c5-600">관리자는 대상(SIP URI 형식)을 지정하거나 사용자가 이미 게시한 대상을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-600">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3e0c5-601">또한 관리자는 이 도구를 사용하여 사용자를 대신하여 대리인 또는 팀 통화 그룹 구성원을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-601">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.</span></span> <span data-ttu-id="3e0c5-602">이 도구는 Microsoft UCMA(Unified Communications Managed API) 3.0을 사용하여 작성된 도구로, 관리자가 SEFAUtil용 중앙 관리 저장소에서 신뢰할 수 있는 응용 프로그램을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-602">This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="3e0c5-603">SEFAUtil(보조 내선 기능 활성화)을 사용하면 비즈니스용 Skype 서버 2015 관리자 및 헬프데스크 에이전트가 비즈니스용 Skype 서버 2015 사용자를 대신하여 위임 벨 울림, 통화 전달, 동시 전화 울림, 팀 통화 설정 및 그룹 통화 pickup을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-603">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3e0c5-604">또한 관리자는 이 도구를 사용하여 특정 사용자에 대해 게시된 통화 라우팅 설정을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-604">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-605">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-605">Description</span></span>

<span data-ttu-id="3e0c5-606">현재 버전의 SEFAUtil은 명령줄 도구일 뿐입니다. 그래픽 사용자 인터페이스는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-606">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3e0c5-607">이 도구는 Microsoft UCMA(Unified Communications Managed API) 3.0을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-607">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3e0c5-608">이 도구의 기능을 통해 관리자 및 헬프데스크 에이전트가 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-608">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="3e0c5-609">사용자에 대한 모든 통화 라우팅 설정 보기(통화 전달, 위임, 동시 전화 울림, 팀 통화 및 그룹 통화 Pickup 포함)</span><span class="sxs-lookup"><span data-stu-id="3e0c5-609">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call, and group call pickup)</span></span>

- <span data-ttu-id="3e0c5-610">통화 전달 설정 사용/사용 안 하도록 설정(대상 및 응답 없음 Timer 포함)</span><span class="sxs-lookup"><span data-stu-id="3e0c5-610">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="3e0c5-611">즉시 전달 즉시 구성 사용/사용 안 하도록 설정/수정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-611">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="3e0c5-612">위임 설정 사용/사용 안 하도록 설정/수정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-612">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="3e0c5-613">팀 통화 그룹 설정 사용/사용 안 하도록 설정/수정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-613">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e0c5-614">비즈니스용 Skype 서버 2015 SEFAUtil 도구의 새로운 도구</span><span class="sxs-lookup"><span data-stu-id="3e0c5-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3e0c5-615">동시 벨 울림 설정 사용/사용 안 하도록 설정/수정(대상 포함)</span><span class="sxs-lookup"><span data-stu-id="3e0c5-615">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e0c5-616">비즈니스용 Skype 서버 2015 SEFAUtil 도구의 새로운 도구</span><span class="sxs-lookup"><span data-stu-id="3e0c5-616">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3e0c5-617">그룹 통화 Pickup 설정 사용/사용 안 하도록 설정/수정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-617">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3e0c5-618">비즈니스용 Skype 서버 2015 SEFAUtil 도구의 새로운 도구</span><span class="sxs-lookup"><span data-stu-id="3e0c5-618">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="3e0c5-619">이 도구에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-619">This tool has the following limitations:</span></span>

- <span data-ttu-id="3e0c5-620">비즈니스용 Skype 서버 풀에 있는 사용자에 한해 지원</span><span class="sxs-lookup"><span data-stu-id="3e0c5-620">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="3e0c5-621">여러 사용자의 통화 라우팅 설정 일괄 편집은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-621">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-622">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-622">Output</span></span>

<span data-ttu-id="3e0c5-623">이 도구의 현재 버전은 명령 프롬프트 창에만 출력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-623">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="3e0c5-624">자세한 내용은 이 문서의 부분에 있는 예제 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-624">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-625">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-625">Purpose</span></span>

<span data-ttu-id="3e0c5-626">다음은 이 도구를 사용할 수 있는 몇 가지 주요 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-626">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="3e0c5-627">Bob은 임원으로, 전화 통신을 비즈니스용 Skype 서버 이동한 바 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-627">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="3e0c5-628">기존 PBX 시스템에 위임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-628">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3e0c5-629">비즈니스용 Skype 서버 2015로 이동하는 경우 관리자는 Bob의 라우팅에 기존 위임 구성을 반영하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-629">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="3e0c5-630">Alice는 출장 중이라 고객 중 한 명으로부터 중요한 전화를 걸고 있을 것으로 기대하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-630">Alice is traveling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="3e0c5-631">그러나 이 부사장은 호텔에 있으며 컴퓨터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-631">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="3e0c5-632">헬프데스크에 전화를 걸고 자신의 업무 번호로 걸려 올 모든 전화를 휴대폰 번호로 전달해 줄 수 있도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-632">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="3e0c5-633">지원 담당자가 대신 구성을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-633">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="3e0c5-634">조지민 의 직장 번호로 전화를 걸면 직장에 갈 때마다 모바일 음성메일로 이동됩니다. 그러나 대부분의 다른 위치에서는 제대로 작동하고 있는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-634">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="3e0c5-635">헬프데스크 기술자는 Joe의 라우팅 구성을 볼 수 있으며 Joe의 휴대폰에 동시 벨 울림이 구성되어 있는지를 발견합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-635">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="3e0c5-636">이 기술자는 Joe에게 사무실의 모바일 적용 범위에 대해 질문하고 동시 전화 울림 규칙이 통화의 네트워크 범위가 불량한 경우 통화가 Joe의 모바일 음성메일로 이동하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-636">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="3e0c5-637">Mike는 Contoso의 신입 사원으로, 비즈니스용 Skype 서버 2015를 사용하도록 설정한 경우 모든 구성원이 팀 통화에 대해 구성된 새 팀에 합류하게 됩니다. 관리자는 자신의 팀 통화 그룹 설정을 설정하여 모든 새 팀 구성원을 포함할 수 있으며, 또한 관리자는 Mike를 팀의 각 구성원에 대한 팀 통화 그룹 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-637">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="3e0c5-638">Contoso의 인적 자원 부서의 고객 서비스 관행은 첫 번째 통화 이후 모든 발신자에 대해 개인 서비스를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-638">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3e0c5-639">부서의 모든 구성원이 서로 매우 가까이 있는 경우 팀 통화를 통해 모든 전화가 동시에 울리게 하는 것은 팀에 지장입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-639">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is disruptive for the team.</span></span> <span data-ttu-id="3e0c5-640">팀 구성원을 방해하지 않고 최상의 서비스를 제공하기 위해 비즈니스용 Skype 서버 2015 관리자는 그룹 통화 선택 기능을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-640">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3e0c5-641">관리자는 모든 부서 구성원을 Pickup 그룹에 추가하고 해당 부서에 Pickup 그룹 번호를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-641">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3e0c5-642">Samantha가 책상에 서지 못하면 Joe는 전화를 울리며 책상에서 전화를 계속 습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-642">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-643">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-643">Requirements</span></span>

<span data-ttu-id="3e0c5-644">SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-644">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="3e0c5-645">UCMA 3.0은 해당 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-645">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="3e0c5-646">이 도구를 실행하려면 해당 풀에 SEFAUtil 응용 프로그램 ID가 있는 새 신뢰할 수 있는 응용 프로그램을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-646">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="3e0c5-647">SEFAUtil 도구에 대한 신뢰할 수 있는 새 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-647">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="3e0c5-648">SEFAUTil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-648">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3e0c5-649">필요한 경우 다음 cmdlet을 사용하여 비즈니스용 Skype 서버 관리 셸을 통해 풀을 새 신뢰할 수 있는 응용 프로그램 풀로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-649">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="3e0c5-650">SEFAUtil 도구를 실행할 컴퓨터에 UCMA 3.0을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-650">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="3e0c5-651">신뢰할 수 있는 응용 프로그램은 SEFAUtil 도구에 대한 토폴로지에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-651">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3e0c5-652">SEFAUtil을 새 신뢰할 수 있는 응용 프로그램으로 정의하기 위해 비즈니스용 Skype 서버 관리 셸을 사용하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-652">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="3e0c5-653">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-653">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3e0c5-654">풀 FQDN: SEFAUtil 응용 프로그램을 호스팅할 서버 또는 풀의 FQDN(일반적으로 비즈니스용 Skype 프런트 엔드 서버 > 풀).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-654">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="3e0c5-655">풀 등록자 FQDN: 이 응용 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-655">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="3e0c5-656">풀 사이트: 이 풀이 있는 사이트의 사이트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-656">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="3e0c5-657">토폴로지 변경 내용을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="3e0c5-658">다음 cmdlet을 실행하여 비즈니스용 Skype 서버 관리 셸을 통해 토폴로지 변경을 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-658">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="3e0c5-659">필요한 경우 SEFAUtil 도구를 실행하기 위해 사용할 서버에 비즈니스용 Skype 서버 2015 Resource Kit Tools를 설치합니다(서버는 신뢰할 수 있는 응용 프로그램 풀의 일부임).</span><span class="sxs-lookup"><span data-stu-id="3e0c5-659">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="3e0c5-660">SEFAUtil이 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3e0c5-661">이렇게하려면 관리자 권한으로 Windows 명령 프롬프트에서 도구를 실행하여 배포에 있는 사용자의 통화 전달 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3e0c5-662">기본적으로 도구는 "...\Program Files\비즈니스용 Skype 서버 2015\Reskit"에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-662">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="3e0c5-663">사용자의 통화 전달 설정을 표시하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-663">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="3e0c5-664">사용자의 통화 전달 설정이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-664">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="3e0c5-665">그룹 통화 받기</span><span class="sxs-lookup"><span data-stu-id="3e0c5-665">Group Call Pickup</span></span>

<span data-ttu-id="3e0c5-666">그룹 통화 선택 기능을 완전히 사용하도록 설정하려면 비즈니스용 Skype 서버 2015에서 추가 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-666">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="3e0c5-667">사용자에게 Pickup 그룹을 할당하기 전에 그룹 통화 선택 제품 설명서에서 이 기능의 계획 및 배포 단계를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-668">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-668">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="3e0c5-669">현재 통화 처리 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3e0c5-670">다음 명령은 사용자에 대한 호출 처리를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-670">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="3e0c5-671">이 예제에서는 **/server** 스위치를 사용하여 연결할 비즈니스용 Skype 서버 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-671">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="3e0c5-672">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-672">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3e0c5-673">전화 전달/응답 없음 대상 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3e0c5-674">이 예에서는 전화 전달/응답 없음 대상 및 링 지연을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3e0c5-675">여기서는 /server 스위치가 제공되지 않습니다. SEFAUtil은 2015에서 자동 비즈니스용 Skype 서버 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="3e0c5-676">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3e0c5-677">즉시 통화 전달 사용</span><span class="sxs-lookup"><span data-stu-id="3e0c5-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3e0c5-678">이 예에서는 다른 사용자에게 즉시 전달을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-678">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="3e0c5-679">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3e0c5-680">즉시 전달을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3e0c5-681">이 예에서는 즉시 통화 전달을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-681">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="3e0c5-682">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3e0c5-683">사용자를 대리인으로 추가하고 대리자 동시 전화 울림 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3e0c5-684">이 예제에서는 사용자를 대리인으로 추가하고 대리자 동시 전화 울림을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="3e0c5-685">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3e0c5-686">대리인의 동시 전화 울림 규칙 변경</span><span class="sxs-lookup"><span data-stu-id="3e0c5-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3e0c5-687">이 예제에서는 이전 예제에서 설정한 동시 벨 울림 규칙을 지연된 벨 울림 규칙으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="3e0c5-688">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-688">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="3e0c5-689">대리인 제거</span><span class="sxs-lookup"><span data-stu-id="3e0c5-689">Remove the Delegate</span></span>

<span data-ttu-id="3e0c5-690">이 예제에서는 대리자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-690">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0c5-691">마지막 대리자가 제거되면 대리자 벨 울림이 자동으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="3e0c5-692">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3e0c5-693">대리인 추가 및 대리인 Call-Forward 규칙 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3e0c5-694">이 예제에서는 대리자를 추가하고 대리자 규칙에 대한 전달을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="3e0c5-695">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-695">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3e0c5-696">동시 벨 울림 사용 및 대상 번호 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3e0c5-697">이 예제에서는 동시 벨 울림을 설정하고 동시 벨 울림 대상 번호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="3e0c5-698">동시 벨 울림을 이미 사용하도록 설정한 사용자의 동시 벨 울림 대상 번호를 변경하기 위해 /enablesimulring 스위치를 사용하여 명령을 유지해야 합니다. 그렇지 않으면 대상 번호가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="3e0c5-699">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3e0c5-700">동시 벨 울림 사용 안</span><span class="sxs-lookup"><span data-stu-id="3e0c5-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3e0c5-701">이 예제에서는 동시 벨 울림을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-701">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="3e0c5-702">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-702">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3e0c5-703">Team-Call 팀 구성원을 추가하고 Team-Call 구성원 그룹에 동시 벨 울림 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3e0c5-704">이 예에서는 사용자의 팀 통화 그룹에 팀 구성원을 추가하고 팀 통화 그룹에 동시 벨 울림을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3e0c5-705">사용자의 팀 통화 그룹에 구성원을 추가하면 사용자의 동시 벨 울림 집합이 자동으로 전환되어 팀 통화 그룹의 동시 벨이 울리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simultaneous ring his team-call group.</span></span>

 <span data-ttu-id="3e0c5-706">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-706">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3e0c5-707">그룹에서 구성원 Team-Call 제거</span><span class="sxs-lookup"><span data-stu-id="3e0c5-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3e0c5-708">이 예에서는 사용자의 팀 통화 그룹의 팀 구성원을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-708">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3e0c5-709">제거되는 구성원이 팀 통화 그룹의 유일한 구성원인 경우 팀 통화 그룹에 동시에 벨 울림이 자동으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="3e0c5-710">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3e0c5-711">지연된 링을 Team-Call 그룹으로 설정</span><span class="sxs-lookup"><span data-stu-id="3e0c5-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3e0c5-712">이 예에서는 지연된 링을 팀 통화 그룹 시간 설정으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-712">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="3e0c5-713">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-713">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="3e0c5-714">사용자 Team-Call</span><span class="sxs-lookup"><span data-stu-id="3e0c5-714">Enable Team-Call</span></span>

<span data-ttu-id="3e0c5-715">이 예에서는 주어진 사용자에 대해 팀 통화를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-715">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3e0c5-716">사용자의 팀 통화 그룹에 구성원이 없는 경우 팀 통화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-716">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="3e0c5-717">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-717">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="3e0c5-718">사용 안 Team-Call</span><span class="sxs-lookup"><span data-stu-id="3e0c5-718">Disable Team-Call</span></span>

<span data-ttu-id="3e0c5-719">이 예에서는 주어진 사용자에 대해 팀 통화를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-719">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="3e0c5-720">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3e0c5-721">그룹 통화 Pickup을 사용하도록 설정하고 사용자에게 Pickup 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="3e0c5-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3e0c5-722">이 예에서는 사용자에게 Pickup 그룹을 할당하고 Group Call Pickup을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="3e0c5-723">**출력**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-723">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="3e0c5-724">그룹 통화 Pickup 사용 안</span><span class="sxs-lookup"><span data-stu-id="3e0c5-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="3e0c5-725">이 예에서는 주어진 사용자에 대해 그룹 통화 Pickup을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-725">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="3e0c5-726">사용자에 대해 그룹 통화 Pickup을 사용하지 않도록 설정하면 사용자에게 할당된 그룹 번호가 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="3e0c5-727">이후에 해당 사용자에 대해 그룹 통화 Pickup을 다시 사용하도록 설정하려면 /enablegrouppickup 스위치를 사용하여 그룹 번호를 다시 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="3e0c5-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3e0c5-728">SYSPrep.ps1</span></span>
<span data-ttu-id="3e0c5-729"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-729"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-730">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-730">Description</span></span>

<span data-ttu-id="3e0c5-731">SYSPrep.ps1 Windows PowerShell Server 2008 운영 체제 컴퓨터에 다음 비즈니스용 Skype 서버 2015 사전 Windows 설치하는 Windows 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="3e0c5-732">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3e0c5-732">Microsoft .NET Framework 4.5</span></span>

- <span data-ttu-id="3e0c5-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3e0c5-733">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="3e0c5-734">Windows PowerShell 버전 3.0</span><span class="sxs-lookup"><span data-stu-id="3e0c5-734">Windows PowerShell version 3.0</span></span>

- <span data-ttu-id="3e0c5-735">Visual C++ 2010 재배포</span><span class="sxs-lookup"><span data-stu-id="3e0c5-735">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="3e0c5-736">인터넷 정보 서버 업데이트</span><span class="sxs-lookup"><span data-stu-id="3e0c5-736">Internet Information Server Updates</span></span>

- <span data-ttu-id="3e0c5-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3e0c5-737">Windows Identity Foundation</span></span>

- <span data-ttu-id="3e0c5-738">비즈니스용 Skype 서버 2015 Core 파일</span><span class="sxs-lookup"><span data-stu-id="3e0c5-738">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="3e0c5-739">스크립트 이름은 Microsoft Windows 운영 체제용 시스템 준비 도구와 유사하기는 하지만 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3e0c5-740">이 스크립트는 2015에 필요한 필수 비즈니스용 Skype 서버 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-740">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="3e0c5-741">이러한 선행 Windows SYSPrep 도구를 사용하여 서버 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-742">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-742">Requirements</span></span>

<span data-ttu-id="3e0c5-743">SYSPrep.ps1 스크립트를 실행하기 전에 **d:\Setup과** 같은 Windows Server 2008 운영 체제 컴퓨터의 로컬 폴더에 선행 작업을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="3e0c5-744">이 폴더에는 특히 2015 비즈니스용 Skype 서버 파일의 복사본이 **포함되어야Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-744">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3e0c5-745">선행 준비 파일은 다음 위치에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-745">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="3e0c5-746">**필수 구성 요소**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-746">**Prerequisite**</span></span>                                | <span data-ttu-id="3e0c5-747">**위치**</span><span class="sxs-lookup"><span data-stu-id="3e0c5-747">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="3e0c5-748">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3e0c5-748">Microsoft .NET Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="3e0c5-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3e0c5-749">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="3e0c5-750">Windows PowerShell 버전 3.0</span><span class="sxs-lookup"><span data-stu-id="3e0c5-750">Windows PowerShell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="3e0c5-751">Visual C++ 2010 재배포</span><span class="sxs-lookup"><span data-stu-id="3e0c5-751">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="3e0c5-752">인터넷 정보 서버 업데이트</span><span class="sxs-lookup"><span data-stu-id="3e0c5-752">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="3e0c5-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3e0c5-753">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="3e0c5-754">비즈니스용 Skype 서버 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3e0c5-754">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="3e0c5-755">2015 비즈니스용 Skype 서버 복사</span><span class="sxs-lookup"><span data-stu-id="3e0c5-755">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="3e0c5-756">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e0c5-756">Parameter</span></span>

<span data-ttu-id="3e0c5-757">**-SetupFolder** 매개 변수는 사전 필요 파일의 디렉터리 위치를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-757">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-758">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-758">Examples</span></span>

<span data-ttu-id="3e0c5-759">SYSPrep.ps1 스크립트를 실행하고 비즈니스용 Skype 서버 2015 선행 작업을 설치하려면 관리자 권한 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-759">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3e0c5-760">미지정 번호 공지 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3e0c5-760">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="3e0c5-761"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-761"><a name="UNAM"> </a></span></span>

<span data-ttu-id="3e0c5-762">비즈니스용 Skype 서버 2015 관리자는 미지정 번호 공지 마이그레이션 도구를 사용하여 공지사항 응용 프로그램에서 제공하는 미지정 번호 구성을 원본 비즈니스용 Skype 서버 또는 풀에서 대상 비즈니스용 Skype 서버 또는 풀로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-762">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-763">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-763">Description</span></span>

<span data-ttu-id="3e0c5-764">미지정 번호 공지사항 마이그레이션 도구는 Windows PowerShell 서버 또는 풀의 공지 사항을 통해 서비스되는 미지정 번호 구성을 다른 서버 또는 풀로 이동하는 Windows PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-764">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="3e0c5-765">이 작업을 실행하면 Unassigned Number Announcements 마이그레이션 스크립트가 다음 작업을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-765">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="3e0c5-766">원본 서버 또는 풀에 호스트된 공지사항 응용 프로그램의 미지정 번호 공지에 사용되는 모든 오디오 파일을 대상 서버 또는 풀의 파일 저장소로 Move all the audio files to the source server or pool.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-766">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e0c5-767">오디오 파일이 대상 풀에 복사되면 원본 풀에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-767">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="3e0c5-768">원본 서버 또는 풀에서 호스팅되는 공지사항 응용 프로그램에 대해 구성된 모든 미지정 번호 공지 사항을 대상 서버 또는 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-768">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="3e0c5-769">원본 서버 또는 풀에서 호스팅되는 공지사항 응용 프로그램에서 서비스하는 모든 미지정 번호 범위를 대상 서버 또는 풀에 다시 재할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-769">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="3e0c5-770">스크립트를 성공적으로 실행하고 나면 원본 서버 또는 풀에서 호스팅되는 공지사항 응용 프로그램에서 서비스한 모든 미지정 번호 범위가 대상 서버 또는 풀에 의해 동일한 구성으로 서비스됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-770">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-771">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-771">Output</span></span>

<span data-ttu-id="3e0c5-772">**Move-CsAnnouncementConfiguration** 스크립트는 비즈니스용 Skype 서버 관리 셸 창에서 마이그레이션 작업의 성공 또는 실패를 실행한 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-772">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="3e0c5-773">오류로 인해 작업 실행이 중단된 경우 대상으로 성공적으로 이동된 미지정 번호 범위는 작업 양식의 대상에 유지되고 마이그레이션할 나머지 미지정 번호 범위는 작업 양식뿐만 아니라 원본에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-773">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="3e0c5-774">나머지 구성을 완전히 마이그레이션하려면 오류를 해결한 후 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-774">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="3e0c5-775">용도</span><span class="sxs-lookup"><span data-stu-id="3e0c5-775">Purpose</span></span>

<span data-ttu-id="3e0c5-776">다음 세 가지 시나리오에서는 미지정 번호 공지 사항 마이그레이션 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-776">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="3e0c5-777">새 버전의 구성 설정으로 구성 설정을 **비즈니스용 Skype 서버.** Contoso는 비즈니스용 Skype 서버 2015로 마이그레이션하는 중이고 마이그레이션 프로세스의 일부로 비즈니스용 Skype 서버 관리자가 Lync Server 2013 배포에서 새 비즈니스용 Skype 서버 2015 배포로 지정되지 않은 번호 구성을 이동하려는 경우를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-777">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3e0c5-778">구성 설정을 이동하기 위해 비즈니스용 Skype 서버 번호 공지 마이그레이션 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-778">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="3e0c5-779">**비즈니스용 Skype 서버 2015에서 Lync Server 2013으로 배포 롤백:** Contoso는 예기치 않은 요인으로 인해 마이그레이션을 새 비즈니스용 Skype 서버 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-779">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3e0c5-780">서비스 중단을 최소화하기 위해 비즈니스용 Skype 서버 관리자는 지정되지 않은 번호 공지 마이그레이션 도구를 사용하여 비즈니스용 Skype 서버 2015 배포에서 Lync Server 2013 배포로 구성을 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-780">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="3e0c5-781">**배포 간에 데이터 이동:** Contoso는 한 풀의 모든 서버를 새 서버로 바꾸는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-781">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3e0c5-782">이러한 전략은 새 비즈니스용 Skype 서버 2015 풀을 배포하고 이전 풀의 모든 데이터를 새 풀로 이동한 다음 이전 풀을 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-782">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3e0c5-783">새 풀이 배포되면 Unassigned Number Announcements 마이그레이션 도구를 사용하여 구성을 이전 풀에서 새 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-783">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="3e0c5-784">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-784">Requirements</span></span>

<span data-ttu-id="3e0c5-785">다음은 도구를 성공적으로 실행하기 위해 필요한 주요 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-785">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="3e0c5-786">이 스크립트는 관리 셸이 설치된 컴퓨터에서 비즈니스용 Skype 서버 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-786">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="3e0c5-787">발표 응용 프로그램은 서버 또는 풀의 원본 및 대상 비즈니스용 Skype 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-787">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3e0c5-788">Move-CsAnnouncementConfiguration 스크립트</span><span class="sxs-lookup"><span data-stu-id="3e0c5-788">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3e0c5-789">Move-CsAnnouncementConfiguration 스크립트를 사용하려면 아래 표에 설명된 두 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-789">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration 매개 변수를 사용합니다.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="3e0c5-791">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-791">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="3e0c5-792">Lync Server 2013 풀에서 2015 풀로 미지정 번호 비즈니스용 Skype 서버 이동</span><span class="sxs-lookup"><span data-stu-id="3e0c5-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="3e0c5-793">이 예에서는 원본 풀(Lync Server 2013)에서 대상 풀(비즈니스용 Skype 서버 2015)로 미지정 번호 공지 사항을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3e0c5-794">비즈니스용 Skype 서버 2015 풀에서 Lync Server 2013 풀로 미지정 번호 공지 구성 이동</span><span class="sxs-lookup"><span data-stu-id="3e0c5-794">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3e0c5-795">이 예에서는 원본 풀(비즈니스용 Skype 서버 2015)에서 대상 풀(Lync Server 2013)로 미지정 번호 공지 사항을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-795">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="3e0c5-796">웹 Conf 데이터</span><span class="sxs-lookup"><span data-stu-id="3e0c5-796">Web Conf Data</span></span>
<span data-ttu-id="3e0c5-797"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="3e0c5-797"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="3e0c5-798">웹 구성 데이터 도구를 사용하면 비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자가 이끌이의 웹 회의와 연결된 데이터를 보다 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-798">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="3e0c5-799">시나리오에는 타임스탬프 조건에 따라 특정 사용자의 모임 데이터를 삭제하는 능력이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-799">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="3e0c5-800">설명</span><span class="sxs-lookup"><span data-stu-id="3e0c5-800">Description</span></span>

<span data-ttu-id="3e0c5-801">이 도구를 사용하면 관리자가 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-801">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="3e0c5-802">단일 사용자와 연결된 모든 웹 회의 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-802">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="3e0c5-803">단일 사용자와 연결된 모든 웹 회의 데이터를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-803">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="3e0c5-804">특정 날짜보다 오래된 단일 사용자와 연결된 모든 웹 회의 데이터를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-804">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="3e0c5-805">한 풀에서 다른 풀로 이동할 때 단일 사용자와 연결된 모든 웹 회의 데이터를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-805">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e0c5-806">Lync Server 2010용 리소스 키트 도구는 사용자가 한 풀에서 다른 풀로 이동할 때 단일 사용자와 연결된 모든 웹 회의 데이터를 이동할 수 있도록 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-806">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3e0c5-807">이 기능은 이제 **MoveConferenceData** 매개 변수를 위해 이 도구에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-807">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="3e0c5-808">이 매개 변수에 대한 자세한 내용은 [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-808">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet.</span></span>

<span data-ttu-id="3e0c5-809">이 도구는 비활성 상태인 모임에 대한 모임 데이터만 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-809">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="3e0c5-810">활성 모임(또는 세션의 모임)은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-810">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="3e0c5-811">이 도구는 대상 사용자와 동일한 풀에 있는 컴퓨터에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-811">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="3e0c5-812">이 도구로 모임 콘텐츠 데이터를 관리하는 사용자는 동일한 사용자 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-812">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="3e0c5-813">출력</span><span class="sxs-lookup"><span data-stu-id="3e0c5-813">Output</span></span>

<span data-ttu-id="3e0c5-814">이 도구는 각 작업의 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-814">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="3e0c5-815">쿼리가 수행되는 경우 도구는 해당 사용자가 이끌이로 있는 모든 비활성 모임 데이터 폴더 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-815">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="3e0c5-816">삭제를 수행하면 해당 데이터가 삭제될 모든 모임 데이터 폴더의 목록이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-816">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="3e0c5-817">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e0c5-817">Requirements</span></span>

<span data-ttu-id="3e0c5-818">이 도구는 이끌이가 현재 있는 풀에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-818">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="3e0c5-819">이 도구는 콘텐츠 파일 저장소에 액세스할 수 있는 관리자 권한을 사용하여 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-819">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="3e0c5-820">예제</span><span class="sxs-lookup"><span data-stu-id="3e0c5-820">Examples</span></span>

<span data-ttu-id="3e0c5-821">다음 표에서는 예제에서 사용되는 매개 변수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-821">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf 데이터 도구 매개 변수입니다.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="3e0c5-823">위의 예제에서는 쿼리 명령이 어떻게 작동할지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-823">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="3e0c5-824">이러한 명령의 출력은 이 도구의 영향을 받는 모든 모임 콘텐츠 폴더의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-824">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="3e0c5-825">위의 명령은 삭제 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-825">The preceding is an example of a delete command.</span></span> <span data-ttu-id="3e0c5-826">삭제 명령은 이 사용자에서 모든 비활성 모임 폴더를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-826">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="3e0c5-827">요약</span><span class="sxs-lookup"><span data-stu-id="3e0c5-827">Summary</span></span>

<span data-ttu-id="3e0c5-828">이 도구는 회의 모임 데이터를 보다 정확하게 제어해야 하는 관리자에게 유용한 리소스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0c5-828">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
