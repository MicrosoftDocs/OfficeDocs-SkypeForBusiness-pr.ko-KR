---
title: 'Lync Server 2013: 응답 그룹 구성 권한 및 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="3af6d-102">Lync Server 2013의 응답 그룹 구성 권한 및 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3af6d-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3af6d-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3af6d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3af6d-104">응답 그룹은 엔터프라이즈 음성 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="3af6d-105">이 항목에서는 응답 그룹을 구성 하 고 구성 작업을 수행 하는 데 필요한 관리 자격 증명과 사용 권한을 구성할 수 있도록 하기 위해 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="3af6d-106">이 섹션에서는 응답 그룹과 관련 된 계획 문서를 읽은 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="3af6d-107">자세한 내용은 계획 문서에서 [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="3af6d-108">구성 도구 및 관리 역할</span><span class="sxs-lookup"><span data-stu-id="3af6d-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="3af6d-109">다음 관리 도구를 사용 하 여 응답 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="3af6d-110">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="3af6d-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="3af6d-111">응답 그룹 구성 도구</span><span class="sxs-lookup"><span data-stu-id="3af6d-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="3af6d-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3af6d-112">Lync Server Management Shell</span></span>

<span data-ttu-id="3af6d-113">응답 그룹을 구성 하려면 다음 관리 역할 중 하나 이상의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3af6d-114"><strong>Active Directory 보안 그룹 (1)</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-115">워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="3af6d-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="3af6d-116">관리자 할당</span><span class="sxs-lookup"><span data-stu-id="3af6d-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="3af6d-117">에이전트 만들기/할당/큐</span><span class="sxs-lookup"><span data-stu-id="3af6d-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="3af6d-118">휴일 및 업무 시간 만들기/관리</span><span class="sxs-lookup"><span data-stu-id="3af6d-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="3af6d-119">워크플로 활성화/비활성화</span><span class="sxs-lookup"><span data-stu-id="3af6d-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="3af6d-120">워크플로 구성 (IVR 또는 헌트 그룹)</span><span class="sxs-lookup"><span data-stu-id="3af6d-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3af6d-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-122">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-122">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-123">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-123">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-124">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-124">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-125">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-125">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-126">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-126">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-127">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3af6d-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="3af6d-129">√ (2)</span><span class="sxs-lookup"><span data-stu-id="3af6d-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-130">√ (3)</span><span class="sxs-lookup"><span data-stu-id="3af6d-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="3af6d-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="3af6d-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="3af6d-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3af6d-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-135">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-135">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-136">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-136">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-137">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-137">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-138">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-138">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-139">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-139">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-140">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3af6d-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-142">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-142">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-143">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-143">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-144">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-144">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-145">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-145">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-146">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-146">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-147">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3af6d-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-149">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-149">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-150">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-150">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-151">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-151">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-152">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-152">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-153">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-153">√</span></span></p></td>
<td><p><span data-ttu-id="3af6d-154">√</span><span class="sxs-lookup"><span data-stu-id="3af6d-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3af6d-155"><strong>Csviewadministrator</strong></span><span class="sxs-lookup"><span data-stu-id="3af6d-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3af6d-156">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="3af6d-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="3af6d-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3af6d-162"><STRONG>(1)</STRONG> Active Directory 도메인 서비스 사용자 개체가 나열 된 active directory 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="3af6d-163">보안 그룹에 사용자를 추가 하는 적절 한 사용 권한이 있는 관리자 또는 기타 위임 된 Active Directory 그룹 구성원 (예: 관리자, 계정 운영자)이 사용자에 게 나열 된 보안 그룹 또는 그룹에 사용자 개체를 추가 해야 사용할 수 있습니다. 나열 된 함수를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="3af6d-164"><STRONG>(2)</STRONG> CsResponseGroupAdministrator가 Csresponsegroupadministrator에 할당 한 워크플로에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="3af6d-165"><STRONG>(3)</STRONG> 응답 그룹 관리자가 CsResponseGroupManager의 다른 구성원을 현재 관리자가 이미 관리 하는 워크플로에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="3af6d-166"><STRONG>(4)</STRONG> csviewonly 관리자는 동사 "Get" Lync Server Management Shell cmdlet만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="3af6d-167">응답 그룹 구성 필수 조건</span><span class="sxs-lookup"><span data-stu-id="3af6d-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="3af6d-168">응답 그룹에는 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="3af6d-169">응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="3af6d-169">Application service</span></span>

  - <span data-ttu-id="3af6d-170">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3af6d-170">Response Group application</span></span>

  - <span data-ttu-id="3af6d-171">언어 팩</span><span class="sxs-lookup"><span data-stu-id="3af6d-171">Language packs</span></span>

  - <span data-ttu-id="3af6d-172">파일 저장소 (오디오 파일 저장)</span><span class="sxs-lookup"><span data-stu-id="3af6d-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="3af6d-173">웹 서비스 (응답 그룹 구성 도구 및 에이전트의 로그인 및 로그 아웃 콘솔 포함)</span><span class="sxs-lookup"><span data-stu-id="3af6d-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="3af6d-174">이러한 구성 요소는 모두 엔터프라이즈 음성을 구축할 때 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="3af6d-175">응답 그룹을 구성 하기 전에 다음 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="3af6d-176">Lync Server 2013 및 Enterprise Voice에 대해 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="3af6d-177">연방 정보 처리 표준 (FIPS)을 준수 하도록 구성 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="3af6d-178">데이터베이스 데이터 정렬을 수정 하 여 대기열 이름과 에이전트 그룹 이름에 대해 Yi, Meng 및 Zang 문자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="3af6d-179">사용자 설정</span><span class="sxs-lookup"><span data-stu-id="3af6d-179">Enabling Users</span></span>

<span data-ttu-id="3af6d-180">응답 그룹을 구성 하는 첫 번째 단계는 에이전트 그룹을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="3af6d-181">에이전트 그룹을 만들려면 먼저 Lync Server 2013 및 Enterprise Voice에 대 한 응답 그룹의 에이전트로 사용할 사용자를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="3af6d-182">Lync Server 2013에 대 한 사용자 사용은 일반적으로 Enterprise Edition server 또는 Standard Edition server 배포의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="3af6d-183">Lync Server 2013 사용자를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 사용자 계정 비활성화 또는 다시 사용](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="3af6d-184">엔터프라이즈 음성에 대 한 사용자 사용은 일반적으로 엔터프라이즈 음성 배포의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="3af6d-185">자세한 내용은 [Lync Server 2013에서 엔터프라이즈 음성 사용자 사용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="3af6d-186">FIPS 요구 사항 준수</span><span class="sxs-lookup"><span data-stu-id="3af6d-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="3af6d-187">이 섹션은 조직이 FIPS (정보 처리 표준)를 준수 해야 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="3af6d-188">FIPS를 준수 하려면 웹 서비스를 설치한 후 다른 암호화 알고리즘을 사용 하도록 응용 프로그램 수준 Web.config 파일을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="3af6d-189">ASP.NET에서 3DES (삼중 데이터 암호화 표준) 알고리즘을 사용 하 여 뷰 상태 데이터를 처리 하도록 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="3af6d-190">응답 그룹 응용 프로그램의 경우이 요구 사항은 응답 그룹 구성 도구와 에이전트 로그인 및 로그 아웃 콘솔에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="3af6d-191">이 요구 사항에 대 한 자세한 내용은 Microsoft 기술 자료 문서 911722, "ASP.NET 1.1에서 ASP.NET 2.0으로 업그레이드 한 후 ViewState가 설정 된 ASP.NET 웹 페이지에 액세스할 때 오류 메시지가 표시 될 수 있습니다 [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)."를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="3af6d-192">Web.config 파일을 수정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="3af6d-193">메모장과 같은 텍스트 편집기에서 응용 프로그램 수준 Web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="3af6d-194">Web.config 파일에서 `<system.web>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="3af6d-195">`<system.web>` 섹션에 다음 `<machineKey>` 섹션을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="3af6d-196">Web.config 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="3af6d-197">명령 프롬프트에서 다음 명령을 실행 하 여 IIS (인터넷 정보 서비스) 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="3af6d-198">Yi, Meng 및 Zang 문자 지원</span><span class="sxs-lookup"><span data-stu-id="3af6d-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="3af6d-199">이 섹션은 조직에서 Yi, Meng 또는 Zang 문자를 지원 해야 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3af6d-200">Yi, Meng 및 Zang 문자에 대 한 정보와 배포에 중요할 수 있는 이유는 GB18030 문자 집합 <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>에 대 한 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="3af6d-201">Yi, Meng 또는 Zang 문자를 지원 하려면 Rgsconfig 데이터베이스에 대 한 데이터 정렬을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-201">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database.</span></span> <span data-ttu-id="3af6d-202">각 Rgsconfig 데이터베이스의 다음 테이블에서 **이름** 열의 데이터 정렬을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-202">Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="3af6d-203">dbo. AgentGroups</span><span class="sxs-lookup"><span data-stu-id="3af6d-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="3af6d-204">dbo. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="3af6d-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="3af6d-205">dbo. HolidaySets</span><span class="sxs-lookup"><span data-stu-id="3af6d-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="3af6d-206">dbo. 시키고</span><span class="sxs-lookup"><span data-stu-id="3af6d-206">dbo.Queues</span></span>

  - <span data-ttu-id="3af6d-207">dbo. 과정</span><span class="sxs-lookup"><span data-stu-id="3af6d-207">dbo.Workflows</span></span>

<span data-ttu-id="3af6d-208">SQL Server 2008 R2 및 SQL Server 2012의 경우 라틴어\_일반\_100 (악센트 구분) 데이터 정렬을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="3af6d-209">이 데이터 정렬을 사용 하는 경우 모든 개체 이름은 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="3af6d-210">Microsoft SQL Server Management Studio를 사용 하 여 데이터 정렬을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="3af6d-211">이 도구를 사용 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)"SQL Server Management Studio 사용"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="3af6d-212">데이터 정렬을 변경 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="3af6d-213">테이블을 다시 만들어야 하는 변경 내용을 허용 하도록 SQL Server Management Studio가 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="3af6d-214">자세한 내용은의 "저장 (허용 되지 않음) 대화 상자"를 [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="3af6d-215">열 데이터 정렬을 설정 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)"방법: 열 데이터 정렬 설정 (Visual Database Tools)"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3af6d-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="3af6d-216">Microsoft SQL Server Management Studio를 사용 하 여 Rgsconfig 데이터베이스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="3af6d-217">Rgsconfig 데이터베이스에서 변경할 테이블을 찾고 테이블을 마우스 오른쪽 단추로 클릭 한 다음 **디자인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="3af6d-218">**이름** 열의 데이터 정렬을 변경 하 고 테이블을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af6d-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

