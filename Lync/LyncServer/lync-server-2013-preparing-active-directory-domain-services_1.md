---
title: 'Lync Server 2013:  Active Directory 도메인 서비스 준비'
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
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="f3bd8-102">Lync Server 2013에서 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3bd8-103">_**마지막으로 수정한 주제:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="f3bd8-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="f3bd8-104">Lync Server 2013에서 Lync Server 배포 마법사를 사용 하 여 Active Directory 도메인 서비스를 준비 하거나 Lync Server 관리 셸 cmdlet을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="f3bd8-105">이 항목의 뒷부분에 설명 된 대로 도메인 컨트롤러에서 ldifde 명령줄 도구를 직접 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="f3bd8-106">Lync Server 배포 마법사가 각 Active Directory 준비 작업을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="f3bd8-107">배포 마법사는 Lync Server Management Shell cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="f3bd8-108">이 도구는 단일 도메인 및 단일 포리스트 토폴로지 또는 기타 유사한 토폴로지가 있는 환경에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3bd8-109">도메인 컨트롤러가 일부 운영 체제의 32 비트 버전을 실행 하는 포리스트나 도메인에 Lync Server를 배포할 수 있습니다 (자세한 내용은 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync server 2013에 대 한 Active Directory 인프라 요구 사항</A>참조).</span><span class="sxs-lookup"><span data-stu-id="f3bd8-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="f3bd8-110">그러나 배포 마법사와 지원 파일이 64 비트 전용 이므로 이러한 환경에서 Lync Server 배포 마법사를 사용 하 여 스키마, 포리스트 및 도메인 준비를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="f3bd8-111">대신, ldifde와 32 비트 도메인 컨트롤러의 연결 된 .ldf 파일을 사용 하 여 스키마, 포리스트 및 도메인을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="f3bd8-112">이 항목의 뒷부분에 있는 "Cmdlet 및 Ldifde 사용" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="f3bd8-113">Lync Server Management Shell cmdlet을 사용 하 여 작업을 원격으로 실행 하거나 복잡 한 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="f3bd8-114">Active Directory 준비 필수 조건</span><span class="sxs-lookup"><span data-stu-id="f3bd8-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="f3bd8-115">Windows Server 2012, Windows Server 2012 R2 또는 Windows Server 2008 R2 SP1 (64 비트)을 실행 하는 컴퓨터에서 Active Directory 준비 단계를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="f3bd8-116">Active Directory 준비에는 Lync Server Management Shell 및 OCSCore 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="f3bd8-117">Active Directory 준비 작업을 실행 하려면 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="f3bd8-118">Lync Server Core 구성 요소 (Ocx 점수. msi)</span><span class="sxs-lookup"><span data-stu-id="f3bd8-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3bd8-119">Active Directory 준비를 위해 Lync Server Management Shell을 사용할 계획 이라면 먼저 Lync Server 배포 마법사를 실행 하 여 핵심 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="f3bd8-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f3bd8-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3bd8-121">Windows Server 2012 및 Windows Server 2012 R2의 경우 서버 관리자를 사용 하 여 .NET Framework 4.5을 설치 하 고 정품 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="f3bd8-122">자세한 내용은 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013에 대 한 추가 소프트웨어 요구 사항</A>에서 "Microsoft .net Framework 4.5"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="f3bd8-123">Windows Server&nbsp;2008&nbsp;R2의 경우 Microsoft 웹 사이트에서 <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A> 을 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="f3bd8-124">RSAT (원격 서버 관리 도구)</span><span class="sxs-lookup"><span data-stu-id="f3bd8-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3bd8-125">도메인 컨트롤러가 아닌 구성원 서버에서 Active Directory 준비 단계를 실행 하는 경우 일부 RSAT 도구가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="f3bd8-126">서버 관리자의 AD DS 및 AD LDS 도구 노드에서 AD DS 스냅인 및 명령줄 도구와 Windows PowerShell 용 Active Directory 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="f3bd8-127">Microsoft Visual c + + 11 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="f3bd8-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3bd8-128">설치 프로그램이 컴퓨터에 아직 설치 되어 있지 않은 경우이 필수 구성 요소를 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="f3bd8-129">패키지는 사용자에 게 제공 되며 별도로 구입 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="f3bd8-130">Windows PowerShell 3.0 (64 비트)</span><span class="sxs-lookup"><span data-stu-id="f3bd8-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="f3bd8-131">Windows Server 2012 및 Windows Server 2012 R2의 경우 Windows PowerShell 3.0을 Lync Server 2013 설치에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="f3bd8-132">Windows Server 2008 R2의 경우 Windows PowerShell 3.0을 설치 하거나 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="f3bd8-133">자세한 내용은 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="f3bd8-134">관리자 권한 및 역할</span><span class="sxs-lookup"><span data-stu-id="f3bd8-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="f3bd8-135">다음 표에서는 각 Active Directory 준비 작업에 필요한 관리 권한 및 역할을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="f3bd8-136">Active Directory 준비에 필요한 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="f3bd8-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3bd8-137">절차</span><span class="sxs-lookup"><span data-stu-id="f3bd8-137">Procedure</span></span></th>
<th><span data-ttu-id="f3bd8-138">권한 또는 역할</span><span class="sxs-lookup"><span data-stu-id="f3bd8-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-139">스키마 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-140">포리스트 루트 도메인 및 스키마 마스터의 관리자 권한에 대 한 스키마 관리자 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="f3bd8-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bd8-141">포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-142">포리스트에 대 한 Enterprise Admins 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="f3bd8-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-143">도메인 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-144">지정 된 도메인에 대 한 엔터프라이즈 관리자 또는 Domain Admins 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="f3bd8-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="f3bd8-145">Active Directory 준비 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f3bd8-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="f3bd8-146">다음 표에서는 AD DS를 준비 하는 데 사용 되는 Lync Server Management Shell cmdlet을 Microsoft Office Communications Server 2007 R2에서 AD DS를 준비 하는 데 사용 되는 LcsCmd 명령으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="f3bd8-147">LcsCmd와 비교 되는 cmdlet</span><span class="sxs-lookup"><span data-stu-id="f3bd8-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3bd8-148">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f3bd8-148">Cmdlets</span></span></th>
<th><span data-ttu-id="f3bd8-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="f3bd8-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="f3bd8-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-151">Lcscmd/forest/action: SchemaPrep/SchemaType: 서버</span><span class="sxs-lookup"><span data-stu-id="f3bd8-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bd8-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="f3bd8-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="f3bd8-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="f3bd8-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-155">Lcscmd/forest/action: ForestPrep</span><span class="sxs-lookup"><span data-stu-id="f3bd8-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bd8-156">사용 안 함-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="f3bd8-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="f3bd8-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="f3bd8-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="f3bd8-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bd8-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="f3bd8-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-161">Lcscmd/domain/action: DomainPrep</span><span class="sxs-lookup"><span data-stu-id="f3bd8-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bd8-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="f3bd8-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-163">Lcscmd/domain/action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="f3bd8-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bd8-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="f3bd8-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="f3bd8-165">Lcscmd/domain/action: CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="f3bd8-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="f3bd8-166">Active Directory 요구 사항 잠금</span><span class="sxs-lookup"><span data-stu-id="f3bd8-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="f3bd8-167">권한 상속을 사용 하지 않거나 인증 된 사용자 권한을 조직에서 사용 하지 않도록 설정 해야 하는 경우 도메인 준비 중에 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="f3bd8-168">자세한 내용은 [Lync Server 2013에서 잠겨진 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="f3bd8-169">사용자 지정 컨테이너 사용 권한</span><span class="sxs-lookup"><span data-stu-id="f3bd8-169">Custom Container Permissions</span></span>

<span data-ttu-id="f3bd8-170">조직에서 세 가지 기본 제공 컨테이너 (즉, 사용자, 컴퓨터 및 도메인 컨트롤러) 대신 사용자 지정 컨테이너를 사용 하는 경우 인증 된 사용자 그룹에 대 한 사용자 지정 컨테이너에 대 한 읽기 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="f3bd8-171">도메인 준비에는 컨테이너에 대 한 읽기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="f3bd8-172">자세한 내용은 [Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="f3bd8-173">Cmdlet 및 Ldifde 사용</span><span class="sxs-lookup"><span data-stu-id="f3bd8-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="f3bd8-174">Lync Server 배포 마법사의 **스키마 준비** 단계와 **설치-CsAdServerSchema** cmdlet은 64 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="f3bd8-175">32 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 해야 하는 경우 구성원 서버에서 원격으로 **설치-CsAdServerSchema** cmdlet을 실행할 수 있습니다 (권장 되는 방법).</span><span class="sxs-lookup"><span data-stu-id="f3bd8-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="f3bd8-176">그러나 도메인 컨트롤러에서 직접 스키마 준비를 실행 해야 하는 경우에는 Ldifde 도구를 사용 하 여 스키마 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="f3bd8-177">Ldifde 도구에는 대부분의 Windows 운영 체제 버전이 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="f3bd8-178">Ldifde를 사용 하 여 스키마 파일을 가져오는 경우 이전 버전에서 마이그레이션하는 지 또는 새로 설치를 수행 하 든 관계 없이 네 개의 파일을 모두 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="f3bd8-179">다음 순서 대로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="f3bd8-180">ExternalSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="f3bd8-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="f3bd8-181">ServerSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="f3bd8-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="f3bd8-182">BackCompatSchema</span><span class="sxs-lookup"><span data-stu-id="f3bd8-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="f3bd8-183">VersionSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="f3bd8-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3bd8-184">4 .ldf 파일은 설치 미디어의 \Support\Schema 디렉터리 또는 다운로드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="f3bd8-185">Ldifde를 사용 하 여 스키마 마스터인 도메인 컨트롤러에 있는 네 개의 스키마 파일을 가져오려면 다음 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="f3bd8-186">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="f3bd8-187">다른 사용자로 로그인 한 경우에만 b 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="f3bd8-188">필요한 사용자 권한에 대 한 자세한 내용은이 항목의 앞부분에 있는 "관리자 권한 및 역할" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="f3bd8-189">Ldifde를 사용 하 여 스키마 마스터가 아닌 도메인 컨트롤러에서 네 개의 스키마 파일을 가져오려면 다음 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="f3bd8-190">Ldifde를 사용 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 237677, "LDIFDE를 사용 하 여 Active Directory로 디렉터리 개체 [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)가져오기 및 내보내기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bd8-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f3bd8-191">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f3bd8-191">In This Section</span></span>

  - [<span data-ttu-id="f3bd8-192">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="f3bd8-193">Lync Server 2013에 대한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="f3bd8-194">Lync Server 2013에 대한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="f3bd8-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

