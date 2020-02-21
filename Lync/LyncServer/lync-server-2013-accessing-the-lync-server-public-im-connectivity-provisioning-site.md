---
title: Lync Server 공용 IM 연결 프로 비전 사이트 액세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44692fd6267e23c98ecef1ca227cbde5289a44b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="91a01-102">Lync Server 2013에서 Lync Server 공용 IM 연결 프로 비전 사이트 액세스</span><span class="sxs-lookup"><span data-stu-id="91a01-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91a01-103">_**마지막으로 수정 된 항목:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="91a01-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="91a01-104">이전 PIC 프로 비전 방법과 비교 하 여 Lync-Skype 연결에 대 한 프로 비전 프로세스가 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="91a01-105">이 프로 비전 프로세스를 완료 하는 데 최대 30 일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="91a01-106">이 문서의 나머지 단계를 완료 하기 전에 먼저이 프로세스를 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="91a01-107">사용자 계정에 대해 Lync-Skype 프로 비전 프로세스가 완료 되 면 계정이 활성화 되 고 해당 사용자가 공용 IM 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="91a01-108">Lync Skype 연결을 프로 비전 하려면 다음 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="91a01-109">Microsoft 계약 번호</span><span class="sxs-lookup"><span data-stu-id="91a01-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="91a01-110">액세스에 지 서비스 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="91a01-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="91a01-111">SIP (세션 시작 프로토콜) 도메인</span><span class="sxs-lookup"><span data-stu-id="91a01-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="91a01-112">모든 추가 액세스에 지 서비스 Fqdn</span><span class="sxs-lookup"><span data-stu-id="91a01-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="91a01-113">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="91a01-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="91a01-114">4 월 2019 부터는 pic.lync.com 웹 사이트를 통해 Skype 페더레이션을 프로 비전 한 고객에 대 한 연락처 정보의 수집 및 보존이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="91a01-115">이렇게 변경 하면 pic.lync.com 프로 비전 시스템이 Microsoft 개인 정보 취급 방침을 준수 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="91a01-116">이 변경이 라이브 되 면 더 이상 보류 중인 프로 비전 변경 내용에 대 한 전자 메일 업데이트를 제공할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="91a01-117">PIC 프로 비전 변경 내용은 일반적으로 입력 후 24-48 시간 이내에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="91a01-118">프로 비전 요청을 제출한 후에도 계속 해 서 Skype 페더레이션 48 문제가 발생 하는 경우에는 Microsoft 기술 지원 서비스에 문의 하 여 추가 조사를 진행 하세요.</span><span class="sxs-lookup"><span data-stu-id="91a01-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91a01-119">이 변경의 일환으로 이전에 입력 한 모든 연락처 정보는 4 월 말까지 시스템에서 제거 됩니다 (2019).</span><span class="sxs-lookup"><span data-stu-id="91a01-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="91a01-120">Lync Skype 연결에 대 한 프로 비전 프로세스를 시작 하려면:</span><span class="sxs-lookup"><span data-stu-id="91a01-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="91a01-121">Microsoft Windows Live ID를 사용 <strong>https://pic.lync.com</strong>하 여 웹 사이트에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="91a01-122">Microsoft 사용권 계약 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="91a01-123">Lync Server에 대 한 제품 사용 권한을 읽고 동의 했는지 확인 하는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="91a01-124"><strong>프로 비전 요청 시작</strong> 페이지에서 적절 한 링크를 클릭 하 여 프로 비전 요청을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="91a01-125"><strong>프로 비전 정보 지정</strong> 페이지에서 <strong>액세스에 지 서비스 FQDN</strong>을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="91a01-126">예: <strong>sip.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="91a01-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="91a01-127">2017 년 7 월 1 일 이후 고객은 공용 IM 연결을 계속 사용 하기 위해 페더레이션 DNS SRV 레코드를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="91a01-128">하나 이상의 SIP 도메인 이름을 입력 한 다음 <strong>추가</strong>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="91a01-129">프로 비전 프로세스를 완료 하려면 하나 이상의 액세스에 지 서버 및 하나의 SIP 도메인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="91a01-130">SIP 도메인 및 액세스에 지 서버는 네트워크에서 활성, 작동 및 연결 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="91a01-131"><strong>공용 IM 서비스 공급자</strong>목록에서 <strong>Skype를</strong> 선택 하 고 <strong>다음</strong> 을 클릭 하 여 연락처 정보를 추가 하 고 프로 비전 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91a01-132">프로 비전 요청이 전송 된 후에는 계정이 정품 인증을 수행 하는 데 최대 30 일이 걸리고 공용 IM 연결을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="91a01-133">페더레이션 및 공용 IM 연결 사용 (PIC)</span><span class="sxs-lookup"><span data-stu-id="91a01-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="91a01-134">프로비저닝 요청을 제출한 후 lync Server 환경 및 Lync Skype 연결을 구성 하는 데 필요한 관리 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="91a01-135">이 섹션에서는 Lync Server 관리자가 Lync Server를 배포 하 고 외부 액세스를 구성한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="91a01-136">Lync Server에 대 한 외부 액세스를 구성 하는 방법에 대 한 자세한 내용은에서 "외부 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) 사용자 액세스 계획" 및 "외부 사용자 [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)액세스 배포"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91a01-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="91a01-137">Lync server 환경을 준비 하려면 lync Server 관리자는 다음 세 가지 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="91a01-138">1\.</span><span class="sxs-lookup"><span data-stu-id="91a01-138">1\.</span></span> <span data-ttu-id="91a01-139">페더레이션 및 PIC 구성</span><span class="sxs-lookup"><span data-stu-id="91a01-139">Configure Federation and PIC</span></span>

<span data-ttu-id="91a01-140">페더레이션은 Skype 사용자가 조직의 Lync 사용자와 통신할 수 있도록 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="91a01-141">공용/PIC (인스턴트 메시징 연결)는 페더레이션 클래스 이며 Lync 사용자가 Skype 사용자와 통신할 수 있도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="91a01-142">페더레이션 및 PIC는 아래와 같이 Lync Server 제어판을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="91a01-143">PIC 페더레이션은 Live Communications Server 2005 s p 1 또는 Office Communication Server 2007에서 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="91a01-144">PIC 페더레이션을 지 원하는 플랫폼에는 Lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 r 2가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="91a01-145">2\.</span><span class="sxs-lookup"><span data-stu-id="91a01-145">2\.</span></span> <span data-ttu-id="91a01-146">페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="91a01-147">Lync Server 제어판을 사용 하 여 관리자는 하나 이상의 외부 사용자 액세스 정책을 구성 하 여 Skype 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="91a01-148">3\.</span><span class="sxs-lookup"><span data-stu-id="91a01-148">3\.</span></span> <span data-ttu-id="91a01-149">Lync에 대 한 Skype PIC 공급자 설정 구성</span><span class="sxs-lookup"><span data-stu-id="91a01-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="91a01-150">Lync Server 관리 셸을 사용 하 여 관리자는 Lync 클라이언트 정책이 Skype를 추가 PIC 공급자로 표시 되도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="91a01-151">공용 IM 연결을 지원 하려면 공용 인스턴트 메시징 연결 (PIC) 서비스 공급자의 사용자가 조직의 IM 또는 전화 회의에 참가할 수 없습니다 (이 절차 앞부분의 2 단계).</span><span class="sxs-lookup"><span data-stu-id="91a01-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="91a01-152">페더레이션 및 PIC를 구성 하려면에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>"페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정 합니다."를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91a01-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="91a01-153">페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 하려면에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>"공용 사용자 액세스를 제어 하도록 정책 구성"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="91a01-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="91a01-154">Lync Server 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="91a01-155">다음의 두 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="91a01-156">현재 환경에 PIC 공급자가 아직 없는 상태에서 새 PIC 공급자를 만드는 경우 <STRONG>disable-cspublicprovider</STRONG> cmdlet을 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="91a01-157">Lync Server 2013 CU5 &amp; lync desktop Client in Office 2013 s p 1에 추가 된 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 타사 도메인을 식별 하 고이를 skype로 라우팅하기 위해 lync 사용자가 skype 대화 상대를 추가할 필요가 있는 상황을 개선 합니다 (예: 사용자 (contoso) @msn .com).</span><span class="sxs-lookup"><span data-stu-id="91a01-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="91a01-158">이러한 새 설정을 사용 하면 NameDecorationRoutingDomain (msn.com으로 설정 되어야 함)의 "Skype 연락처 추가" 대화 상자에 있는 주소 사용자 입력의 자동 서식이 NameDecorationExcludedDomainList에 있는 도메인을 포함 하지 않는 경우 ( 현재 msn.com, live.com, Hotmail.com, outlook.com)를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="91a01-159">Lync 클라이언트에서 이제 Skype를 PIC 공급자로 선택 하 고 Microsoft 계정을 지정 하 여 Skype 클라이언트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="91a01-160">또한 Microsoft 계정을 사용 하 여 병합 및 로그인 한 Skype 사용자는 연락처 요청을 Lync 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="91a01-161">Microsoft 계정에 대 한 자세한 내용은 [microsoft 계정 이란?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91a01-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="91a01-162">Lync에 클라이언트를 추가 하는 방법에 대 한 자세한 내용은 [최종 사용자로 Lync Server 2013에서 Lync Skype 연결 사용](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="91a01-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="91a01-163">호스팅된 공급자를 수정 하는 방법에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)"호스트 SIP 페더레이션 공급자 만들기 또는 편집"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="91a01-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="91a01-164">이렇게 하면 서버에서 수행 해야 하는 관리 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="91a01-165">이제 Lync Skype 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a01-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="91a01-166">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="91a01-166">Additional Resources</span></span>

[<span data-ttu-id="91a01-167">Lync Server 2013에서 최종 사용자로 Lync Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="91a01-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="91a01-168">Lync Server 2013의 Lync-Skype 연결을 위한 프로 비전 가이드</span><span class="sxs-lookup"><span data-stu-id="91a01-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

