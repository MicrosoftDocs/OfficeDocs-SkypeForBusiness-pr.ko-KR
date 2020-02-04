---
title: Lync Server 2013에서 XMPP 게이트웨이 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2910766dbb2147fa5d1c51235f10ab2e80826bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="8086e-102">Lync Server 2013에서 XMPP 게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="8086e-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8086e-103">_**마지막으로 수정한 주제:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="8086e-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="8086e-104">XMPP 게이트웨이를 마이그레이션하는 마지막 단계는 Lync Server 2013 Edge 서버에 대 한 인증서를 구성 하 고 Lync Server 2013 XMPP 게이트웨이를 배포 하 고 XMPP 게이트웨이에 대 한 DNS 레코드를 업데이트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="8086e-105">이 단계는 XMPP 게이트웨이의 중단 시간을 최소화 하기 위해 병렬로 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="8086e-106">이 단계를 수행 하기 전에 모든 사용자가 Microsoft Lync Server 2013 배포로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="8086e-107">XMPP federation는 survivable branch 기기에 속한 사용자에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="8086e-108">이는 현재 상태 정보를 보고 메신저 대화 메시지를 교환 하는 데 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="8086e-109">Lync Server 2013 Edge 서버에서 XMPP 게이트웨이 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="8086e-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="8086e-110">Edge 서버에서 배포 마법사의 **3 단계: 인증서 요청, 설치 또는 할당**에서 다음을 **다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="8086e-111">Edge 서버를 처음 배포 하는 경우에는가 다시 실행 되는 대신 실행이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="8086e-112">**사용 가능한 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="8086e-113">**인증서 요청** 페이지에서 **외부에 지 인증서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="8086e-114">**지연 또는 즉시 요청** 페이지에서 **지금 요청 준비, 나중에 보내기** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="8086e-115">**인증서 요청 파일** 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예: c:\\cert\_외부\_가장자리만).</span><span class="sxs-lookup"><span data-stu-id="8086e-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="8086e-116">**대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿 이외의 서식 파일을 사용 하려면 **선택한 인증 기관에 대체 인증서 서식 파일 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="8086e-117">**이름 및 보안 설정** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="8086e-118">**대화명**에 인증서의 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="8086e-119">비트 **길이**에서 비트 길이를 지정 합니다 (일반적으로 2048의 기본값).</span><span class="sxs-lookup"><span data-stu-id="8086e-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="8086e-120">**인증서 개인 키를 내보낼** 수 있도록 표시 확인란을 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="8086e-121">**조직 정보** 페이지에서 조직과 조직 구성 단위 이름 (예: 부서 또는 부서)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="8086e-122">**지역 정보** 페이지에서 위치 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="8086e-123">**제목 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채워지는 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-123">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="8086e-124">추가 주제 대체 이름이 필요한 경우 다음 두 단계에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-124">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="8086e-125">**Sip 도메인 설정의 san (주체 대체 이름** ) 페이지에서 도메인 확인란을 선택 하 여 sip를 추가 합니다. \<주제\> 대체 이름 목록에 항목을 sipdomain.</span><span class="sxs-lookup"><span data-stu-id="8086e-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="8086e-126">**추가 주제 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="8086e-127">XMPP 프록시를 설치 하면 기본적으로 도메인 이름 (예: contoso.com)이 SAN 항목에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-127">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="8086e-128">더 많은 항목이 필요한 경우이 단계에서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-128">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="8086e-129">**요청 요약** 페이지에서 요청을 생성 하는 데 사용할 인증서 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="8086e-130">명령 실행이 완료 되 면 로그를 **보거나**다음을 클릭 하 여 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="8086e-131">**인증서 요청 파일** 페이지에서 **마침을**클릭 하 여 인증서 마법사를 종료 하 고 **보기** 를 클릭 하 여 생성 된 CSR (인증서 서명 요청) 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="8086e-132">요청 파일을 복사 하 고 공용 인증 기관에 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="8086e-133">공개 인증서를 받고, 가져오고, 할당 한 후에는 Edge 서버 서비스를 중지 하 고 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-133">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="8086e-134">Lync Server 관리 콘솔에서 입력 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-134">You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="8086e-135">새 Lync Server 2013 XMPP 게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="8086e-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="8086e-136">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="8086e-137">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스** 를 클릭 한 다음 **Xmpp 페더레이션된 파트너**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="8086e-138">새 구성을 만들려면 **새로**만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="8086e-139">다음 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-139">Define the following settings:</span></span>

5.  <span data-ttu-id="8086e-140">**주 도메인**     (필수).</span><span class="sxs-lookup"><span data-stu-id="8086e-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="8086e-141">주 도메인은 XMPP 파트너의 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="8086e-142">예를 들어 XMPP 파트너 도메인 이름에 대해 **fabrikam.com** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="8086e-143">필수 입력 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-143">This is a required entry.</span></span>

6.  <span data-ttu-id="8086e-144">**설명**   이 특정 구성에 대 한 설명은 메모 또는 기타 식별 정보에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="8086e-145">이 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-145">This entry is optional.</span></span>

7.  <span data-ttu-id="8086e-146">**추가 도메인**   추가 도메인은 허용 되는 xmpp 통신의 일부로 포함 되어야 하는 xmpp 파트너의 도메인에 속하는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="8086e-147">예를 들어 주 도메인이 **fabrikam.com**인 경우에는 fabrikam.com 아래에 있는 다른 모든 도메인이 xmpp를 통해 통신 하도록 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="8086e-148">**파트너 종류**    **파트너 유형은** 필수 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="8086e-149">추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="8086e-150">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-150">You can select from:</span></span>
    
      - <span data-ttu-id="8086e-151">**페더레이션된**    **페더레이션** 파트너 종류는 Lync Server 배포와 xmpp 파트너 간 신뢰의 상위 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="8086e-152">이 파트너 유형은 같은 기업 내에서 XMPP 서버와 페더레이션 하거나 비즈니스 관계가 설정 된 위치에서 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="8086e-153">페더레이션 파트너의 XMPP 연락처는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="8086e-154">Lync 사용자에 게 명시적으로 승인 되지 않은 Lync 대화 상대를 추가 하 고 현재 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="8086e-155">Lync 사용자가 대화 상대 목록에 메시지를 추가 했는지 여부에 관계 없이 Lync 연락처로 메신저 대화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="8086e-156">Lync 사용자의 상태 메모를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="8086e-157">**공용 확인**   된 **공개 인증 파트너는** 해당 사용자의 id를 확인 하는 데 신뢰할 수 있는 공용 xmpp 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="8086e-158">공공 확인 된 네트워크의 XMPP 연락처는 lync 사용자의 로그인을 추가 하 여 해당 대화 상대의 현재 상태를 확인 하 고 인스턴트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="8086e-159">공공 확인 된 네트워크의 XMPP 연락처는 Lync 사용자의 상태 메모를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="8086e-160">이 설정은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="8086e-161">**공용**확인 되지 않은 공용 확인 되지 않은 파트너는 해당 사용자의 id를 확인 하기 위해 신뢰할 수 없는 공용 xmpp 공급자입니다. \*\*\*\*    </span><span class="sxs-lookup"><span data-stu-id="8086e-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="8086e-162">Lync 사용자가 연락처 목록에 추가 하는 것을 명시적으로 부여 하지 않는 한 공개 확인 되지 않은 네트워크의 XMPP 사용자가 Lync 사용자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="8086e-163">XMPP 공용 확인 되지 않은 네트워크의 사용자에 게는 Lync 사용자의 상태 노트가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="8086e-164">이 설정은 Google 대화와 같은 공공 XMPP 공급자를 사용 하는 모든 페더레이션에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="8086e-165">**연결 형식:** 다양 한 규칙 및 dialback 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="8086e-166">**Tls 협상**   은 tls 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="8086e-167">XMPP 서비스는 TLS를 요구 하거나 TLS 옵션을 만들거나 해당 TLS가 지원 되지 않는 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="8086e-168">선택 항목을 선택 하면 필수적으로 협상을 결정할 수 있도록 XMPP 서비스에 대 한 요구 사항이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="8086e-169">SASL, TLS 및 Dialback 협상 (유효 하지 않은 알려진 오류 구성 포함)에 대 한 가능한 모든 설정 및 세부 정보를 보려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8086e-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-170">\*\*\*\*   Xmpp 서비스에는 TLS 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-171">**선택적**   으로 xmpp 서비스는 TLS가 필수적으로 협상 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-172">**지원 되지 않음**   xmpp 서비스는 TLS를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="8086e-173">**Sasl negotiation**   는 sasl 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="8086e-174">XMPP 서비스에는 SASL이 필요 하거나, SASL을 선택적으로 만들거나, SASL이 지원 되지 않는 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="8086e-175">선택 항목을 선택 하면 파트너 XMPP 서비스에 대 한 필수-협상 결정을 위한 요구 사항이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-176">\*\*\*\*   Xmpp 서비스에는 SASL 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-177">**선택적**   으로 xmpp 서비스는 SASL이 필수적으로 협상 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-178">**지원 되지 않음**   xmpp 서비스는 SASL을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="8086e-179">**서버 dialback 협상 지원** 지원 서버 dialback 협상 프로세스는 DNS (domain name system) 및 권한 있는 서버를 사용 하 여 요청이 유효한 XMPP 파트너 로부터 제공 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="8086e-180">이렇게 하려면 원래 서버에서 생성 된 dialback 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 받는 서버를 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="8086e-181">원래 서버는 XML 스트림의 키를 결과 DNS 조회로 보내고 받는 서버를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="8086e-182">XML 스트림을 통해 키를 수신 하면 받는 서버는 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="8086e-183">권한이 있는 서버는 키가 유효 하거나 유효 하지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="8086e-184">유효 하지 않은 경우 받는 서버는 원래 서버에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="8086e-185">키가 유효 하면 받는 서버는 id 및 키가 유효 하 고 대화를 시작할 수 있음을 원래 서버에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="8086e-186">**Dialback 협상**에는 다음과 같은 두 가지 유효한 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-187">**True**   원본 서버에서 요청을 받아야 하는 경우 xmpp 서버는 Dialback 협상을 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8086e-188">**False**   xmpp 서버는 Dialback 협상을 사용 하도록 구성 되지 않으며 원래 서버에서 요청을 수신 해야 하는 경우 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="8086e-189">**커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="8086e-190">Lync Server 2013 XMPP 게이트웨이에 대 한 DNS 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="8086e-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="8086e-191">XMPP 페더레이션을 위해 DNS를 구성 하려면 외부 DNS:\_xmpp-server에 다음 SRV 레코드를 추가 합니다. \_tcp. \<도메인 이름\> SRV 레코드가 EDGE 서버의 액세스 가장자리 FQDN으로 확인 되며 포트 값은 5269입니다.</span><span class="sxs-lookup"><span data-stu-id="8086e-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

