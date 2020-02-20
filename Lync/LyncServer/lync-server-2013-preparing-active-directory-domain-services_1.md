---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="afd7c-102">Lync Server 2013에서 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd7c-103">_**마지막으로 수정 된 항목:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="afd7c-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="afd7c-104">Lync Server 2013에서는 Lync Server 배포 마법사를 사용 하 여 Active Directory 도메인 서비스를 준비 하거나 Lync Server 관리 셸 cmdlet을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="afd7c-105">또한 이 항목의 뒷부분에 설명된 대로 도메인 컨트롤러에서 ldifde.exe 명령줄 도구를 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="afd7c-106">Lync Server 배포 마법사가 각 Active Directory 준비 작업을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="afd7c-107">배포 마법사는 Lync Server 관리 셸 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="afd7c-108">이 도구는 단일 도메인 및 단일 포리스트 토폴로지 또는 이와 유사한 토폴로지 환경에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="afd7c-109">도메인 컨트롤러에서 32 비트 버전의 운영 체제를 실행 하는 포리스트 또는 도메인에 Lync Server를 배포할 수 있습니다 (자세한 내용은 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory 인프라 요구 사항 (Lync Server 2013의</A>경우).</span><span class="sxs-lookup"><span data-stu-id="afd7c-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="afd7c-110">그러나 배포 마법사와 지원 파일이 64 비트 전용 이므로 이러한 환경에서는 Lync Server 배포 마법사를 사용 하 여 스키마, 포리스트 및 도메인 준비를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="afd7c-111">대신, ldifde와 연결 된 .ldf 파일을 32 비트 도메인 컨트롤러에 사용 하 여 스키마, 포리스트 및 도메인을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="afd7c-112">이 항목의 뒷부분에 나오는 "Cmdlet 및 Ldifde 사용" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="afd7c-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="afd7c-113">Lync Server 관리 셸 cmdlet을 사용 하 여 원격으로 또는 좀 더 복잡 한 환경에 대해 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="afd7c-114">Active Directory 준비를 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="afd7c-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="afd7c-115">Windows Server 2012, Windows Server 2012 R2 또는 Windows Server 2008 R2 SP1 (64 비트)을 실행 하는 컴퓨터에서 Active Directory 준비 단계를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="afd7c-116">Active Directory 준비에는 Lync Server 관리 셸 및 OCSCore 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="afd7c-117">Active Directory 준비 작업을 실행하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="afd7c-118">Lync Server Core 구성 요소 (OCScore)</span><span class="sxs-lookup"><span data-stu-id="afd7c-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afd7c-119">Active Directory 준비를 위해 Lync Server 관리 셸을 사용 하려는 경우 먼저 Lync Server 배포 마법사를 실행 하 여 핵심 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="afd7c-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="afd7c-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afd7c-121">Windows Server 2012 및 Windows Server 2012 r 2의 경우 서버 관리자를 사용 하 여 .NET Framework 4.5을 설치 하 고 정품 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="afd7c-122">자세한 내용은 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013에 대 한 추가 소프트웨어 요구 사항</A>에서 "Microsoft .net Framework 4.5"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd7c-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="afd7c-123">Windows Server&nbsp;2008&nbsp;r 2의 경우 Microsoft 웹 사이트에서 <A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A> 를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="https://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="afd7c-124">RSAT(원격 서버 관리 도구)</span><span class="sxs-lookup"><span data-stu-id="afd7c-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afd7c-125">도메인 컨트롤러 대신 구성원 서버에서 Active Directory 준비 단계를 실행하려면 몇 가지 RSAT 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="afd7c-126">서버 관리자의 ad DS 및 AD LDS 도구 노드에서 AD DS 스냅인 및 명령줄 도구와 Windows PowerShell 용 Active Directory 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="afd7c-127">Microsoft Visual c + + 11 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="afd7c-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afd7c-p107">설치 시 이 필수 구성 요소를 설치할지 묻는 메시지가 나타납니다(컴퓨터에 이미 설치되지 않은 경우). 이 패키지는 자동으로 제공되므로 별도로 구입할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="afd7c-130">Windows PowerShell 3.0 (64 비트)</span><span class="sxs-lookup"><span data-stu-id="afd7c-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="afd7c-131">Windows Server 2012 및 Windows Server 2012 r 2의 경우 Lync Server 2013 설치에 Windows PowerShell 3.0이 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="afd7c-132">Windows Server 2008 r 2의 경우 Windows PowerShell 3.0을 설치 하거나 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="afd7c-133">자세한 내용은 [Windows PowerShell 3.0 For Lync Server 2013을](lync-server-2013-installing-windows-powershell-3-0.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="afd7c-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="afd7c-134">관리자 권한 및 역할</span><span class="sxs-lookup"><span data-stu-id="afd7c-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="afd7c-135">다음 표에서는 Active Directory 준비 작업에 필요한 관리자 권한 및 역할을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="afd7c-136">Active Directory 준비에 필요한 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="afd7c-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afd7c-137">절차</span><span class="sxs-lookup"><span data-stu-id="afd7c-137">Procedure</span></span></th>
<th><span data-ttu-id="afd7c-138">권한 또는 역할</span><span class="sxs-lookup"><span data-stu-id="afd7c-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-139">스키마 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="afd7c-140">Schema Admins 그룹의 구성원(포리스트 루트 도메인) 및 관리자 권한(스키마 마스터)</span><span class="sxs-lookup"><span data-stu-id="afd7c-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd7c-141">포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="afd7c-142">Enterprise Admins 그룹의 구성원(포리스트)</span><span class="sxs-lookup"><span data-stu-id="afd7c-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-143">도메인 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="afd7c-144">Enterprise Admins 또는 Domain Admins 그룹의 구성원(지정된 도메인)</span><span class="sxs-lookup"><span data-stu-id="afd7c-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="afd7c-145">Active Directory 준비 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="afd7c-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="afd7c-146">다음 표에서는 AD ds를 준비 하는 데 사용 되는 Lync Server 관리 셸 cmdlet과 Microsoft Office Communications Server 2007 r 2에서 AD DS를 준비 하는 데 사용 되는 LcsCmd 명령에 대해 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="afd7c-147">Cmdlet와 LcsCmd 비교</span><span class="sxs-lookup"><span data-stu-id="afd7c-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afd7c-148">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="afd7c-148">Cmdlets</span></span></th>
<th><span data-ttu-id="afd7c-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="afd7c-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-150">설치-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="afd7c-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="afd7c-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="afd7c-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd7c-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="afd7c-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="afd7c-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="afd7c-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="afd7c-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="afd7c-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="afd7c-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd7c-156">사용 안 함-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="afd7c-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="afd7c-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="afd7c-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="afd7c-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="afd7c-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="afd7c-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd7c-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="afd7c-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="afd7c-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="afd7c-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd7c-162">사용 안 함-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="afd7c-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="afd7c-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="afd7c-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd7c-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="afd7c-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="afd7c-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="afd7c-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="afd7c-166">잠긴 Active Directory 요구 사항</span><span class="sxs-lookup"><span data-stu-id="afd7c-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="afd7c-167">조직에서 권한 상속이 비활성화되어 있거나 인증된 사용자 권한을 비활성화해야 하는 경우 도메인 준비 작업 중에 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="afd7c-168">자세한 내용은 [Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd7c-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="afd7c-169">사용자 지정 컨테이너 권한</span><span class="sxs-lookup"><span data-stu-id="afd7c-169">Custom Container Permissions</span></span>

<span data-ttu-id="afd7c-170">조직에서 세 가지 기본 제공 컨테이너(사용자, 컴퓨터 및 도메인 컨트롤러) 대신 사용자 지정 컨테이너를 사용하는 경우 Authenticated Users 그룹에 대해 사용자 지정 컨테이너에 대한 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="afd7c-171">컨테이너에 대한 읽기 권한은 도메인을 준비하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="afd7c-172">자세한 내용은 [Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="afd7c-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="afd7c-173">Cmdlet 및 Ldifde.exe 사용</span><span class="sxs-lookup"><span data-stu-id="afd7c-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="afd7c-174">Lync Server 배포 마법사의 **스키마 준비** 단계와 **Install-csadserverschema** cmdlet은 64 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="afd7c-175">32비트 운영 체제를 실행하는 도메인 컨트롤러에서 Active Directory 스키마를 확장해야 하는 경우 구성원 서버에서 원격으로 **Install-CsAdServerSchema** cmdlet를 실행할 수 있습니다(권장 방법).</span><span class="sxs-lookup"><span data-stu-id="afd7c-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="afd7c-176">그러나 도메인 컨트롤러에서 스키마 준비를 직접 실행해야 하는 경우에는 Ldifde.exe 도구를 사용하여 스키마 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="afd7c-177">Ldifde.exe 도구는 대부분의 Windows 운영 체제 버전에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="afd7c-p112">Ldifde.exe를 사용하여 스키마 파일을 가져오는 경우 이전 버전에서 마이그레이션 중인지 또는 새로 설치하는 중인지에 관계없이 네 개 파일을 모두 가져와야 합니다. 가져와야 하는 파일의 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="afd7c-180">ExternalSchema .ldf</span><span class="sxs-lookup"><span data-stu-id="afd7c-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="afd7c-181">ServerSchema .ldf</span><span class="sxs-lookup"><span data-stu-id="afd7c-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="afd7c-182">Backcompatschema.ldf-이전</span><span class="sxs-lookup"><span data-stu-id="afd7c-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="afd7c-183">VersionSchema .ldf</span><span class="sxs-lookup"><span data-stu-id="afd7c-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afd7c-184">이 네 개의 .ldf 파일은 설치 미디어 또는 다운로드의 \Support\Schema 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="afd7c-185">Ldifde.exe를 사용하여 스키마 마스터인 도메인 컨트롤러에서 스키마 파일 네 개를 가져오려면 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="afd7c-186">예:</span><span class="sxs-lookup"><span data-stu-id="afd7c-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="afd7c-p113">b 매개 변수는 다른 사용자로 로그인한 경우에만 사용합니다. 필요한 사용자 권한에 대한 자세한 내용은 이 항목의 앞부분에 있는 "관리자 권한 및 역할" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="afd7c-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="afd7c-189">Ldifde.exe를 사용하여 스키마 마스터가 아닌 도메인 컨트롤러에서 스키마 파일 네 개를 가져오려면 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="afd7c-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="afd7c-190">Ldifde를 사용 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 237677, "LDIFDE를 사용 하 여 Active Directory로 디렉터리 개체 [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)가져오기 및 내보내기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd7c-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afd7c-191">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="afd7c-191">In This Section</span></span>

  - [<span data-ttu-id="afd7c-192">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="afd7c-193">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="afd7c-194">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="afd7c-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

