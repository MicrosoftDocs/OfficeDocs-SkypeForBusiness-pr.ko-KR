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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="93488-102">Lync Server 2013의 2 단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="93488-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93488-103">_**마지막으로 수정한 주제:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="93488-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="93488-104">다음은 2 단계 인증을 지원 하도록 Microsoft Lync Server 2013 환경을 구성할 때의 배포 고려 사항 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="93488-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="93488-105">클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="93488-105">Client Support</span></span>

<span data-ttu-id="93488-106">Lync Server 2013의 Lync 2013 누적 업데이트: 7 2013 월 데스크톱 클라이언트와 모든 모바일 클라이언트는 현재 2 단계 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="93488-107">토폴로지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="93488-107">Topology Requirements</span></span>

<span data-ttu-id="93488-108">고객은 Lync Server 2013에 대 한 누적 업데이트와 함께 전용 Lync Server 2013을 사용 하 여 2 단계 인증을 배포 하는 것이 좋습니다: 7 2013 월 모서리, 디렉터 및 사용자 풀.</span><span class="sxs-lookup"><span data-stu-id="93488-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="93488-109">Lync 사용자에 게 수동 인증을 사용 하도록 설정 하려면 다음을 포함 하 여 다른 역할 및 서비스에 대해 다른 인증 방법을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93488-110">구성 형식</span><span class="sxs-lookup"><span data-stu-id="93488-110">Configuration Type</span></span></th>
<th><span data-ttu-id="93488-111">서비스 종류</span><span class="sxs-lookup"><span data-stu-id="93488-111">Service Type</span></span></th>
<th><span data-ttu-id="93488-112">서버 역할</span><span class="sxs-lookup"><span data-stu-id="93488-112">Server Role</span></span></th>
<th><span data-ttu-id="93488-113">사용할 수 없도록 설정 하는 인증 유형</span><span class="sxs-lookup"><span data-stu-id="93488-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93488-114">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="93488-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="93488-115">되었는지</span><span class="sxs-lookup"><span data-stu-id="93488-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="93488-116">Director</span><span class="sxs-lookup"><span data-stu-id="93488-116">Director</span></span></p></td>
<td><p><span data-ttu-id="93488-117">Kerberos, NTLM, 인증서</span><span class="sxs-lookup"><span data-stu-id="93488-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93488-118">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="93488-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="93488-119">되었는지</span><span class="sxs-lookup"><span data-stu-id="93488-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="93488-120">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="93488-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="93488-121">Kerberos, NTLM, 인증서</span><span class="sxs-lookup"><span data-stu-id="93488-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93488-122">가상본</span><span class="sxs-lookup"><span data-stu-id="93488-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="93488-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="93488-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="93488-124">쪽</span><span class="sxs-lookup"><span data-stu-id="93488-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="93488-125">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="93488-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93488-126">가상본</span><span class="sxs-lookup"><span data-stu-id="93488-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="93488-127">레지스터</span><span class="sxs-lookup"><span data-stu-id="93488-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="93488-128">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="93488-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="93488-129">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="93488-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93488-130">이러한 인증 유형을 서비스 수준에서 사용 하지 않도록 설정 하지 않는 한, 모든 다른 버전의 Lync 클라이언트는 배포 내에서 2 단계 인증을 사용 하도록 설정한 후에도 성공적으로 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="93488-131">Lync 서비스 검색</span><span class="sxs-lookup"><span data-stu-id="93488-131">Lync Service Discovery</span></span>

<span data-ttu-id="93488-132">내부 및/또는 외부 클라이언트가 Lync 서비스를 검색 하는 데 사용 하는 DNS 레코드는 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 서버로 확인 되도록 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="93488-133">이 구성을 사용 하는 경우, 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 풀의 사용자는 인증에 PIN을 입력 하는 데 필요 하지 않으며, 2 단계 인증을 사용 하도록 설정 된 Lync 풀의 사용자는 PIN을 입력 해야 합니다. rpc.</span><span class="sxs-lookup"><span data-stu-id="93488-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="93488-134">Exchange 인증</span><span class="sxs-lookup"><span data-stu-id="93488-134">Exchange Authentication</span></span>

<span data-ttu-id="93488-135">Microsoft Exchange에 대해 2 단계 인증을 배포한 고객은 Lync 클라이언트의 특정 기능을 사용할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="93488-136">이는 Lync 클라이언트가 Exchange 통합에 종속 된 기능에 대해 2 단계 인증을 지원 하지 않기 때문에 현재 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93488-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="93488-137">Lync 연락처</span><span class="sxs-lookup"><span data-stu-id="93488-137">Lync Contacts</span></span>

<span data-ttu-id="93488-138">통합 대화 상대 저장소 기능을 활용 하도록 구성 된 Lync 사용자는 2 단계 인증을 사용 하 여 로그인 한 후 해당 연락처를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="93488-139">2 단계 인증을 사용 하도록 설정 하기 전에 **CsUcsRollback** cmdlet을 사용 하 여 통합 된 연락처 저장소에서 기존 사용자 연락처를 제거 하 고 Lync Server 2013에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="93488-140">기술 검색</span><span class="sxs-lookup"><span data-stu-id="93488-140">Skill Search</span></span>

<span data-ttu-id="93488-141">Lync 환경에서 기술 검색 기능을 구성한 고객은 Lync가 2 단계 인증을 사용 하도록 설정 된 경우에는이 기능이 작동 하지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="93488-142">이것은 Microsoft SharePoint가 현재 2 단계 인증을 지원 하지 않기 때문에 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93488-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="93488-143">Lync 자격 증명</span><span class="sxs-lookup"><span data-stu-id="93488-143">Lync Credentials</span></span>

<span data-ttu-id="93488-144">2 단계 인증을 사용 하도록 구성 된 사용자에 게 영향을 줄 수 있는 저장 된 Lync 자격 증명 관련 몇 가지 배포 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="93488-145">저장 된 자격 증명 삭제</span><span class="sxs-lookup"><span data-stu-id="93488-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="93488-146">데스크톱 클라이언트 사용자는 2 단계 인증을 사용 하 여 처음으로 로그인 하기 전에 Lync 클라이언트에서 **내 로그인 정보 삭제** 옵션을 사용 하\\여\\%\\LOCALAPPDATA\\% Microsoft Office 15.0 Lync에서 해당 SIP 프로필 폴더를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="93488-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="93488-147">DisableNTCredentials</span></span>

<span data-ttu-id="93488-148">Kerberos 또는 NTLM 인증 방법을 사용 하면 사용자의 Windows 자격 증명이 인증에 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93488-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="93488-149">Kerberos 및/또는 NTLM이 인증을 사용 하도록 설정 되어 있는 일반적인 Lync Server 2013 배포에서는 사용자가 로그인 할 때마다 자격 증명을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="93488-150">사용자가 PIN을 입력 하 라는 메시지가 표시 되기 전에 실수로 자격 증명을 묻는 메시지가 표시 되는 경우, 그룹 정책을 통해 클라이언트 컴퓨터에 **DisableNTCredentials** 레지스트리 키가 실수로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="93488-151">자격 증명에 대 한 추가 메시지가 표시 되지 않도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 만들거나 Lync 관리 템플릿을 사용 하 여 그룹 정책을 사용 하 여 지정 된 풀의 모든 사용자에 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="93488-152">HKEY\_로컬\_컴퓨터\\소프트웨어\\정책\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="93488-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="93488-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="93488-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="93488-154">값: 0x0</span><span class="sxs-lookup"><span data-stu-id="93488-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="93488-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="93488-155">SavePassword</span></span>

<span data-ttu-id="93488-156">사용자가 처음으로 Lync에 로그인 하면 사용자에 게 암호를 저장 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93488-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="93488-157">이 옵션을 선택 하면 사용자의 클라이언트 인증서가 개인 인증서 저장소에 저장 되 고 사용자의 Windows 자격 증명은 로컬 컴퓨터의 자격 증명 관리자에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93488-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="93488-158">Lync가 2 단계 인증을 지원 하도록 구성 된 경우 **Savepassword** 레지스트리 설정을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="93488-159">사용자가 암호를 저장 하지 못하도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 변경 하거나 Lync 관리 서식 파일을 사용 하 여 그룹 정책을 사용 하 여 지정 된 풀의 모든 사용자에 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="93488-160">HKEY\_현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="93488-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="93488-161">REG\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="93488-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="93488-162">값: 0x0</span><span class="sxs-lookup"><span data-stu-id="93488-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="93488-163">AD FS 2.0 토큰 재생</span><span class="sxs-lookup"><span data-stu-id="93488-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="93488-164">AD FS 2.0는 동일한 토큰을 사용 하는 여러 토큰 요청이 검색 되 고 삭제 될 수 있는 토큰 재생 검색 이라는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="93488-165">이 기능을 사용 하는 경우 토큰 재생 감지는 동일한 토큰이 두 번 이상 사용 되지 않도록 하 여 WS-FEDERATION 수동 프로필 및 SAML WebSSO 프로필 둘 다의 인증 요청에 대 한 무결성을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="93488-166">이 기능을 사용 하려면 보안이 키오스크를 사용 하는 경우와 같이 매우 높은 관심사에 있는 상황에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93488-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="93488-167">토큰 재생 검색에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)AD FS 2.0의 보안 계획 및 배포에 대 한 모범 사례를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93488-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="93488-168">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="93488-168">External User Access</span></span>

<span data-ttu-id="93488-169">외부 네트워크에서 Lync의 2 단계 인증을 지원 하도록 AD FS 프록시 또는 리버스 프록시를 구성 하는 것은 이러한 항목에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93488-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

