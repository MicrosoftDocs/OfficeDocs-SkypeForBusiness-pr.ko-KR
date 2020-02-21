---
title: Lync Server 2013:2 단계 인증 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0738cb282ad2f1f375e89526fcdd1569a6707ad0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="1ae49-102">Lync Server 2013의 2 단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="1ae49-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae49-103">_**마지막으로 수정 된 항목:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="1ae49-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="1ae49-104">다음은 2 단계 인증을 지원 하기 위해 Microsoft Lync Server 2013 환경을 구성할 때의 배포 고려 사항 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="1ae49-105">클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="1ae49-105">Client Support</span></span>

<span data-ttu-id="1ae49-106">Lync Server 2013에 대 한 Lync 2013 누적 업데이트: 7 월 2013 데스크톱 클라이언트 및 모든 모바일 클라이언트는 현재 2 단계 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="1ae49-107">토폴로지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ae49-107">Topology Requirements</span></span>

<span data-ttu-id="1ae49-108">고객은 Lync Server 2013에 대 한 누적 업데이트와 함께 전용 Lync Server 2013을 사용 하 여 2 단계 인증을 배포 하는 것이 좋습니다 (2013 년 7 월, 디렉터 및 사용자 풀).</span><span class="sxs-lookup"><span data-stu-id="1ae49-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="1ae49-109">Lync 사용자에 대해 수동 인증을 사용 하도록 설정 하려면 다음을 비롯 한 다른 역할 및 서비스에 대해 다른 인증 방법을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ae49-110">구성 유형</span><span class="sxs-lookup"><span data-stu-id="1ae49-110">Configuration Type</span></span></th>
<th><span data-ttu-id="1ae49-111">서비스 종류</span><span class="sxs-lookup"><span data-stu-id="1ae49-111">Service Type</span></span></th>
<th><span data-ttu-id="1ae49-112">서버 역할</span><span class="sxs-lookup"><span data-stu-id="1ae49-112">Server Role</span></span></th>
<th><span data-ttu-id="1ae49-113">사용 하지 않도록 설정할 인증 유형</span><span class="sxs-lookup"><span data-stu-id="1ae49-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae49-114">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="1ae49-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1ae49-115">System.webserver</span><span class="sxs-lookup"><span data-stu-id="1ae49-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1ae49-116">영화</span><span class="sxs-lookup"><span data-stu-id="1ae49-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1ae49-117">Kerberos, NTLM 및 인증서</span><span class="sxs-lookup"><span data-stu-id="1ae49-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae49-118">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="1ae49-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1ae49-119">System.webserver</span><span class="sxs-lookup"><span data-stu-id="1ae49-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1ae49-120">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="1ae49-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="1ae49-121">Kerberos, NTLM 및 인증서</span><span class="sxs-lookup"><span data-stu-id="1ae49-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae49-122">프록시와</span><span class="sxs-lookup"><span data-stu-id="1ae49-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1ae49-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="1ae49-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="1ae49-124">면</span><span class="sxs-lookup"><span data-stu-id="1ae49-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="1ae49-125">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="1ae49-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae49-126">프록시와</span><span class="sxs-lookup"><span data-stu-id="1ae49-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1ae49-127">등록자</span><span class="sxs-lookup"><span data-stu-id="1ae49-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="1ae49-128">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="1ae49-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="1ae49-129">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="1ae49-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1ae49-130">서비스 수준에서 이러한 인증 유형을 사용 하지 않도록 설정 하지 않으면 배포 내에서 2 단계 인증을 사용 하는 경우 다른 모든 버전의 Lync 클라이언트에서 성공적으로 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="1ae49-131">Lync 서비스 검색</span><span class="sxs-lookup"><span data-stu-id="1ae49-131">Lync Service Discovery</span></span>

<span data-ttu-id="1ae49-132">내부 및/또는 외부 클라이언트가 Lync services를 검색 하는 데 사용 하는 DNS 레코드는 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 서버로 확인 되도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="1ae49-133">이 구성을 사용 하는 경우 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 풀의 사용자는 인증에 PIN을 입력 하지 않아도 되 고, 2 단계 인증을 사용 하는 Lync 풀의 사용자는 PIN을 입력 해야 합니다. 받고.</span><span class="sxs-lookup"><span data-stu-id="1ae49-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="1ae49-134">Exchange 인증</span><span class="sxs-lookup"><span data-stu-id="1ae49-134">Exchange Authentication</span></span>

<span data-ttu-id="1ae49-135">Microsoft Exchange에 대해 2 단계 인증을 배포한 고객은 Lync 클라이언트의 특정 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="1ae49-136">이는 Lync 클라이언트가 Exchange 통합에 의존 하는 기능에 대해 2 단계 인증을 지원 하지 않으므로 현재 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="1ae49-137">Lync 대화 상대</span><span class="sxs-lookup"><span data-stu-id="1ae49-137">Lync Contacts</span></span>

<span data-ttu-id="1ae49-138">통합 연락처 저장소 기능을 활용 하도록 구성 된 Lync 사용자는 2 단계 인증을 사용 하 여 로그인 한 후 해당 연락처를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="1ae49-139">2 단계 인증을 사용 하도록 설정 하기 전에 **invoke-csucsrollback** cmdlet을 사용 하 여 통합 연락처 저장소에서 기존 사용자 연락처를 제거한 후 Lync Server 2013에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="1ae49-140">기술 검색</span><span class="sxs-lookup"><span data-stu-id="1ae49-140">Skill Search</span></span>

<span data-ttu-id="1ae49-141">Lync 환경에서 기술 검색 기능을 구성한 고객은 Lync가 2 단계 인증을 사용 하도록 설정 된 경우이 기능이 작동 하지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="1ae49-142">이는 Microsoft SharePoint에서 현재 2 단계 인증을 지원 하지 않으므로 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="1ae49-143">Lync 자격 증명</span><span class="sxs-lookup"><span data-stu-id="1ae49-143">Lync Credentials</span></span>

<span data-ttu-id="1ae49-144">2 단계 인증을 사용 하도록 구성 된 사용자에 게 영향을 줄 수 있는 저장 된 Lync 자격 증명과 관련 한 몇 가지 배포 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="1ae49-145">저장 된 자격 증명 삭제</span><span class="sxs-lookup"><span data-stu-id="1ae49-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="1ae49-146">데스크톱 클라이언트 사용자는 2 단계 인증을 사용 하 여 처음으로 서명을 시도 하기 전에 Lync 클라이언트에서 **내 로그인 정보 삭제** 옵션을 사용\\하\\고\\%\\localappdata% Microsoft Office 15.0 Lync에서 SIP 프로필 폴더를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="1ae49-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="1ae49-147">DisableNTCredentials</span></span>

<span data-ttu-id="1ae49-148">Kerberos 또는 NTLM 인증 방법을 사용 하는 경우 인증을 위해 사용자의 Windows 자격 증명이 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="1ae49-149">Kerberos 및/또는 NTLM이 인증을 사용 하도록 설정 된 일반적인 Lync Server 2013 배포에서는 사용자가 로그인 할 때마다 자격 증명을 입력 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="1ae49-150">사용자에 게 PIN을 입력 하 라는 메시지가 표시 되기 전에 실수로 자격 증명을 묻는 메시지가 표시 되는 경우에는 그룹 정책을 통해 클라이언트 컴퓨터에서 **DisableNTCredentials** 레지스트리 키가 실수로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="1ae49-151">자격 증명에 대 한 추가 확인을 방지 하려면 로컬 워크스테이션에 다음 레지스트리 항목을 만들거나, 그룹 정책을 사용 하 여 지정 된 풀에 대 한 모든 사용자에 게 Lync 관리 템플릿을 사용 하 여 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1ae49-152">HKEY\_로컬\_컴퓨터\\소프트웨어\\정책\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="1ae49-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1ae49-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="1ae49-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="1ae49-154">값: 0x0</span><span class="sxs-lookup"><span data-stu-id="1ae49-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="1ae49-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="1ae49-155">SavePassword</span></span>

<span data-ttu-id="1ae49-156">사용자가 처음 Lync에 로그인 할 때 사용자에 게 암호를 저장 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="1ae49-157">이 옵션을 선택 하면 사용자의 클라이언트 인증서를 개인 인증서 저장소에 저장 하 고 사용자의 Windows 자격 증명을 로컬 컴퓨터의 자격 증명 관리자에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="1ae49-158">Lync가 2 단계 인증을 지원 하도록 구성 된 경우에는 **Savepassword** 레지스트리 설정을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="1ae49-159">사용자가 암호를 저장 하지 못하도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 변경 하거나, 그룹 정책을 사용 하 여 지정 된 풀에 대 한 모든 사용자에 게 Lync 관리 템플릿을 사용 하 여 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1ae49-160">HKEY\_현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="1ae49-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1ae49-161">REG\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="1ae49-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="1ae49-162">값: 0x0</span><span class="sxs-lookup"><span data-stu-id="1ae49-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="1ae49-163">AD FS 2.0 토큰 재생</span><span class="sxs-lookup"><span data-stu-id="1ae49-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="1ae49-164">AD FS 2.0는 동일한 토큰을 사용 하는 여러 토큰 요청을 검색 한 다음 삭제할 수 있는 토큰 재생 검색 이라는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="1ae49-165">이 기능을 사용 하도록 설정 하면 토큰 재생 검색 기능이 WS-FEDERATION 수동 프로필과 SAML Websso) 프로필 둘 다에서 인증 요청의 무결성을 보호 하 여 동일한 토큰을 두 번 이상 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="1ae49-166">이 기능은 보안을 사용 하는 경우 키오스크를 사용할 때와 같이 보안이 매우 중요 한 상황에서 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="1ae49-167">토큰 재생 검색에 대 한 자세한 내용은 Secure FS 2.0의 보안 계획 및 배포 모범 사례를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span><span class="sxs-lookup"><span data-stu-id="1ae49-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="1ae49-168">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="1ae49-168">External User Access</span></span>

<span data-ttu-id="1ae49-169">외부 네트워크에서 Lync 2 단계 인증을 지원 하도록 AD FS 프록시 또는 역방향 프록시를 구성 하는 것은 이러한 항목에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae49-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

