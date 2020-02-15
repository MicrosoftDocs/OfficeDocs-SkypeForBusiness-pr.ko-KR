---
title: Lync Server 2013에서 XMPP 게이트웨이 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5735c9e4786548ce7b12ab82327ffc72c27873bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="04d4a-102">Lync Server 2013에서 XMPP 게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="04d4a-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04d4a-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="04d4a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="04d4a-104">XMPP(eXtensible Messaging and Presence Protocol) 페더레이션 파트너 지원을 위한 정책을 구성하는 경우 SIP(Session Initiation Protocol) 서비스 공급자(예: Windows Live)나 SIP 페더레이션된 도메인의 사용자가 아닌 XMPP 페더레이션된 도메인의 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="04d4a-105">사용자가 연락처를 추가하고 통신하도록 허용할 각 XMPP 페더레이션된 도메인에 대해 XMPP 페더레이션 파트너를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="04d4a-106">정책이 적용 되 면 XMPP 게이트웨이 인증서 구성, Lync Server 2013 XMPP 게이트웨이 배포, XMPP 게이트웨이의 DNS 레코드 업데이트 등이 추가 작업에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="04d4a-107">Lync Server 2013 에지 서버에서 XMPP 게이트웨이 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="04d4a-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="04d4a-108">에지 서버의 배포 마법사에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="04d4a-109">처음으로 에지 서버를 배포하는 경우 "다시 실행" 대신 "실행"이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="04d4a-110">**사용할 수 있는 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="04d4a-111">**인증서 요청** 페이지에서 **외부 에지 인증서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="04d4a-112">**지연 또는 즉시 요청** 페이지에서 **지금 요청을 준비하고 나중에 보냅니다** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="04d4a-113">**인증서 요청 파일** 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예를 들어, c:\\cert\_외부\_에 있는 .cer).</span><span class="sxs-lookup"><span data-stu-id="04d4a-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="04d4a-114">**대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 **선택한 인증 기관에 대체 인증서 템플릿 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="04d4a-115">**이름 및 보안 설정** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="04d4a-116">**이름**에 인증서 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="04d4a-117">**비트 길이**에서 비트 길이를 지정합니다(일반적으로 기본값은 2048).</span><span class="sxs-lookup"><span data-stu-id="04d4a-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="04d4a-118">**인증서의 개인 키를 내보낼 수 있는 것으로 표시** 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="04d4a-119">**조직 정보** 페이지에 조직 및 조직 구성 단위의 이름(예: 사업부 또는 부서)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="04d4a-120">**지역 정보** 페이지에서 위치 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="04d4a-p102">**주체 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다. 추가 주체 대체 이름이 필요한 경우 다음 두 단계에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="04d4a-123">**주체 대체 이름 (san)에 대 한 Sip 도메인 설정** 페이지에서 sip를 추가 하려면 도메인 확인란을 선택 합니다. \<주체\> 대체 이름 목록에 microsoft.rtc.management.xds.sipdomain object 항목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="04d4a-124">**추가 주체 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="04d4a-p103">XMPP 프록시가 설치된 경우 기본적으로 도메인 이름(예: contoso.com)이 SAN 항목에 채워집니다. 더 많은 항목이 필요한 경우 이 단계에서 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-p103">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="04d4a-127">**요청 요약** 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="04d4a-128">명령 실행이 완료되면 **로그 보기**를 수행하거나 **다음**을 클릭하여 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="04d4a-129">**인증서 요청 파일** 페이지에서 보기를 클릭하여 생성된 CSR(인증서 서명 요청) 파일을 보거나 **마침**을 클릭하여 인증서 마법사를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="04d4a-130">요청 파일을 복사한 다음 공용 인증 기관에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="04d4a-p104">공용 인증서를 받아 가져오고 할당한 후 에지 서버 서비스를 중지한 다음 다시 시작해야 합니다. 이는 Lync Server 관리 콘솔에서 다음을 입력해서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-p104">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="04d4a-133">새로운 Lync Server 2013 XMPP 게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="04d4a-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="04d4a-134">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="04d4a-135">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **XMPP 페더레이션 파트너**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="04d4a-136">새 구성을 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="04d4a-137">다음 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-137">Define the following settings:</span></span>

5.  <span data-ttu-id="04d4a-138">**주 도메인**     (필수)</span><span class="sxs-lookup"><span data-stu-id="04d4a-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="04d4a-139">주 도메인은 XMPP 파트너의 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="04d4a-140">예를 들어 XMPP 파트너 도메인 이름에는 **fabrikam.com** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="04d4a-141">필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-141">This is a required entry.</span></span>

6.  <span data-ttu-id="04d4a-142">**설명**   이 특정 구성에 대 한 참고 사항 또는 기타 식별 정보에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="04d4a-143">이 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-143">This entry is optional.</span></span>

7.  <span data-ttu-id="04d4a-144">**추가 도메인**   추가 도메인은 허용 되는 xmpp 통신의 일부로 포함 되어야 하는 xmpp 파트너의 도메인에 속하는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="04d4a-145">예를 들어 주 도메인이 **fabrikam.com**인 경우에는 xmpp를 사용 하 여 통신 하는 fabrikam.com 아래의 다른 모든 도메인을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="04d4a-146">**파트너 유형**    **파트너 유형은** 필수 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="04d4a-147">추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="04d4a-148">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-148">You can select from:</span></span>
    
      - <span data-ttu-id="04d4a-149">**페더레이션** **페더레이션** 파트너 유형은 Lync Server 배포와 xmpp 파트너 간의 높은 신뢰 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="04d4a-150">이 파트너 유형은 같은 엔터프라이즈 내의 XMPP 서버와 페더레이션 하거나 설정 된 비즈니스 관계가 있는 위치에 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="04d4a-151">페더레이션 파트너의 XMPP 연락처는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="04d4a-152">Lync 사용자로부터의 명시적 권한 부여 없이 Lync 대화 상대를 추가하고 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="04d4a-153">Lync 사용자가 자신의 대화 상대 목록에 추가했는지 여부와 상관없이 Lync 대화 상대에게 메신저 대화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="04d4a-154">Lync 사용자의 상태 메모를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="04d4a-155">**공용 확인**  **공용 확인** 된 파트너는 해당 사용자의 id를 확인 하기 위해 신뢰할 수 있는 공용 xmpp 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="04d4a-156">공용 확인 된 네트워크의 XMPP 연락처는 lync 사용자 로부터 온 권한 부여 없이 Lync 대화 상대를 추가 하 고 현재 상태를 확인 하 고 인스턴트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="04d4a-157">XMPP 연락처 공용 확인 네트워크에는 Lync 사용자의 상태 노트가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="04d4a-158">이 설정은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="04d4a-p111">**확인되지 않은 공공 파트너** **확인되지 않은 공공 파트너**는 사용자 ID를 확인하도록 신뢰되지 않는 공용 XMPP 공급자입니다. 확인되지 않은 공공 파트너 네트워크의 XMPP 사용자는 Lync 사용자가 자신을 대화 상대 목록에 추가하도록 명시적으로 권한을 부여한 경우가 아니면 Lync 사용자와 통신할 수 없습니다. 확인되지 않은 공공 파트너 네트워크의 XMPP 사용자에게는 Lync 사용자의 상태 메모가 표시되지 않습니다. Google Talk와 같은 공용 XMPP 공급자와의 페더레이션 시에는 이 설정을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-p111">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="04d4a-163">**연결 형식:** 다양한 규칙 및 전화 접속 회의 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="04d4a-164">**Tls 협상**   은 tls 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="04d4a-165">XMPP 서비스에 대해 TLS를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="04d4a-166">"선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 XMPP 서비스까지 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="04d4a-167">유효 및 알려진 오류 구성을 포함 하 여 SASL, TLS 및 전화 접속 회의 협상에 대해 가능한 모든 설정 및 세부 정보를 확인 하려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md) 참조</span><span class="sxs-lookup"><span data-stu-id="04d4a-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="04d4a-168">**필수**   xmpp 서비스에 TLS 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="04d4a-169">**Optional**   xmpp 서비스는 TLS가 필수-협상 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="04d4a-170">**지원 되지 않음**   xmpp 서비스에서 TLS를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="04d4a-171">**Sasl 협상**   은 sasl 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="04d4a-172">XMPP 서비스에 대해 SASL를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="04d4a-173">"선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 파트너 XMPP 서비스까지 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="04d4a-174">**필수**   xmpp 서비스에 SASL 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="04d4a-175">**Optional**   xmpp 서비스는 SASL이 필수-협상 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="04d4a-176">**지원 되지 않음**   xmpp 서비스에서 SASL을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="04d4a-177">**지원 서버 전화 접속 회의 협상** 지원 서버 전화 접속 회의 협상 프로세스는 DNS (domain name system) 및 신뢰할 수 있는 서버를 사용 하 여 요청이 유효한 XMPP 파트너 로부터 온 것 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="04d4a-178">이 작업을 수행 하기 위해 원래 서버는 생성 된 전화 접속 회의 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 수신 서버를 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="04d4a-179">원본 서버가 XML 스트림의 키를 결과 DNS 조회로 전송 하 고 받는 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="04d4a-180">XML stream에서 키를 받으면 수신 서버가 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="04d4a-181">신뢰할 수 있는 서버에서 키가 유효 하거나 올바르지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="04d4a-182">올바르지 않으면 받는 서버가 원래 서버에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="04d4a-183">키가 올바르면 받는 서버가 원래 서버에 id 및 키가 유효 하며 대화를 시작할 수 있음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="04d4a-184">**전화 접속 회의 협상**의 유효한 두 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="04d4a-185">**True**   원본 서버에서 요청을 받아야 하는 경우 xmpp 서버가 전화 접속 회의 협상을 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="04d4a-186">**False**   xmpp 서버가 전화 접속 회의 협상을 사용 하도록 구성 되어 있지 않으며, 원래 서버에서 요청을 받아야 하는 경우 해당 서버는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="04d4a-187">**커밋**을 클릭하여 변경 내용을 사이트 또는 사용자 정책에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="04d4a-188">Lync Server 2013 XMPP 게이트웨이의 DNS 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="04d4a-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="04d4a-189">XMPP 페더레이션을 사용 하도록 DNS를 구성 하려면 외부 DNS:\_xmpp-server에 다음 SRV 레코드를 추가 합니다. \_tcp를 \<도메인 이름\> SRV 레코드는에 지 서버의 액세스에 지 FQDN을 확인 하며 포트 값은 5269입니다.</span><span class="sxs-lookup"><span data-stu-id="04d4a-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

