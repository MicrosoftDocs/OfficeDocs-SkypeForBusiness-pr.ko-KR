---
title: 'Lync Server 2013: 보안 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8325f8b153a4f1927b4a37136c1cc68c7112168
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e794b-102">Lync Server 2013의 보안 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e794b-102">Security cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e794b-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e794b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e794b-104">Microsoft Lync Server 2013에 포함 된 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-104">The security cmdlets included in Microsoft Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="e794b-105">인증서 및 PIN(개인 식별 번호) 인증을 위한 cmdlet 등 인증 관리에 사용할 수 있는 다양한 cmdlet가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-105">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="e794b-106">또한 많은 cmdlet을 사용 하 여 새 RBAC (역할 기반 액세스 제어) 기능을 통해 Lync Server의 관리 제어를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-106">In addition, a number of cmdlets enable you to use the new role-based access control (RBAC) feature to delegate administrative control of Lync Server.</span></span>

<div>

## <a name="security-cmdlets"></a><span data-ttu-id="e794b-107">보안 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e794b-107">Security Cmdlets</span></span>

<span data-ttu-id="e794b-108">보안 설정에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-108">Many management tasks that apply to security settings can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="e794b-109">한 가지 주요 예외는 사용자 권한 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-109">One major exception is the user permission cmdlets.</span></span> <span data-ttu-id="e794b-110">그러나 모든 보안 관리 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-110">However, all security management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="e794b-111">다음은 보안 설정 관리에 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e794b-111">The following is a list of cmdlets that relate directly to managing security settings:</span></span>

<span data-ttu-id="e794b-112">**[Lync Server 2013의 인증서 및 인증 cmdlet](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e794b-112">**[Certificate and authentication cmdlets in Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-113">[Set-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-113">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-114">[Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-114">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-115">[Set-cscertificate을 제거 합니다.](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-115">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-116">[요청-Set-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-116">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-117">[Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-117">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-118">[Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-119">[Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-119">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-120">[Get-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-120">[Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-121">[잠금-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-121">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-122">[설정-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-122">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-123">[잠금 해제-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-123">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-124">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-124">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-125">[새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-125">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-126">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-127">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-128">[Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-129">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-130">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-132">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-132">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-133">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-133">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-134">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-134">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-135">[Get-cspinpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-135">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-136">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-136">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-138">[새-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-138">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-139">[CsProxyConfiguration 제거](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-140">[설정-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-141">[New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-141">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-142">[New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-142">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-143">[New-cssipdomain을 제거 합니다.](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-143">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-144">[New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-144">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span></span>

<span data-ttu-id="e794b-145">**[Lync Server 2013의 사용자 권한 및 사용 권한 cmdlet](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e794b-145">**[User rights and permissions cmdlets in Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-146">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-146">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-147">[새-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-147">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-148">[제거-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-148">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-149">[설정-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-149">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-150">[업데이트-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-150">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-152">[부여-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-152">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-153">[CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-153">[Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-154">[테스트-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-154">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e794b-155">[부여-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-155">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-156">[CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-156">[Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e794b-157">[테스트-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-157">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span></span>

<span data-ttu-id="e794b-158">**[Lync Server 2013의 상호 운용성 cmdlet](lync-server-2013-interoperability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e794b-158">**[Interoperability cmdlets in Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span></span>

  - <span data-ttu-id="e794b-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e794b-161">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-161">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-162">[새-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-162">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-163">[CsOAuthServer 제거](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-163">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-164">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-164">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e794b-165">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-165">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-166">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-166">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-167">[Get-cspartnerapplication을 제거 합니다.](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="e794b-168">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e794b-168">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e794b-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e794b-169">See Also</span></span>


[<span data-ttu-id="e794b-170">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="e794b-170">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

