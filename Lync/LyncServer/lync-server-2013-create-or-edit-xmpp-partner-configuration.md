---
title: 'Lync Server 2013: XMPP 파트너 구성 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="df363-102">Lync Server 2013에서 XMPP 파트너 구성 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="df363-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df363-103">_**마지막으로 수정한 주제:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="df363-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="df363-104">Microsoft Lync Server 2013는 Edge 서버의 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 프록시를 통합 하 고 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="df363-105">다른 XMPP 배포의 연결을 허용 하려면 Lync Server 제어판에서 XMPP를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="df363-106">XMPP 도메인 단위로 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="df363-107">새 파트너 연결을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="df363-108">새 페더레이션 파트너를 만들거나 기존 구성을 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="df363-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="df363-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df363-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df363-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df363-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df363-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df363-112">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **Xmpp 페더레이션된 파트너**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="df363-113">새 구성을 만들려면 **새로** 만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="df363-114">기존 구성을 편집 하려면 구성을 선택 하 고 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="df363-115">**Xmpp 페더레이션 파트너**에 대 한 구성을 만들거나 편집 하려면 다음 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="df363-116">**주 도메인** (필수).</span><span class="sxs-lookup"><span data-stu-id="df363-116">**Primary domain** (Required).</span></span> <span data-ttu-id="df363-117">주 도메인은 XMPP 파트너의 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="df363-118">예를 들어 XMPP 파트너 도메인 이름에 대해 **fabrikam.com** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="df363-119">필수 입력 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-119">This is a required entry.</span></span>

8.  <span data-ttu-id="df363-120">**설명**.</span><span class="sxs-lookup"><span data-stu-id="df363-120">**Description**.</span></span> <span data-ttu-id="df363-121">설명은이 특정 구성에 대 한 메모 또는 기타 식별 정보에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="df363-122">이 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-122">This entry is optional.</span></span>

9.  <span data-ttu-id="df363-123">**추가 도메인**.</span><span class="sxs-lookup"><span data-stu-id="df363-123">**Additional domains**.</span></span> <span data-ttu-id="df363-124">추가 도메인은 허용 된 XMPP 통신의 일부로 포함 되어야 하는 XMPP 파트너의 도메인에 속하는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="df363-125">예를 들어 주 도메인이 **fabrikam.com**인 경우에는 fabrikam.com 아래에 있는 다른 모든 도메인이 xmpp를 통해 통신 하도록 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="df363-126">예를 들어, 회사 XMPP 도메인 및 정보 기술 XMPP 도메인에 대 한 **corp.fabrikam.com** 및 **it.fabrikam.com** 를 fabrikam의 주 xmpp 도메인 아래에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="df363-127">**파트너 유형**.</span><span class="sxs-lookup"><span data-stu-id="df363-127">**Partner type**.</span></span> <span data-ttu-id="df363-128">**파트너 종류** 는 필수 설정이 며 드롭다운 메뉴에서 세 가지 선택 항목을 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="df363-129">추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="df363-130">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-130">You can select from:</span></span>
    
      - <span data-ttu-id="df363-131">**페더레이션**.</span><span class="sxs-lookup"><span data-stu-id="df363-131">**Federated**.</span></span> <span data-ttu-id="df363-132">**페더레이션** 파트너 종류는 Lync Server 또는 Office Communications Server 2007 R2 파트너 배포 간의 신뢰 된 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="df363-133">**공용이 확인**되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-133">**Public verified**.</span></span> <span data-ttu-id="df363-134">**공개 확인** 된 파트너는 공급자가 확인 한 배포의 일부인 연락처를 사용자의 연락처 목록에 추가할 수 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="df363-135">초대는 Lync 사용자에 게 서 보내거나, Lync 사용자가 파트너 연락처의 초대를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="df363-136">**공용**이 확인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-136">**Public unverified**.</span></span> <span data-ttu-id="df363-137">확인 되지 않은 **공용** 관계는 두 배포 간에 설정 및 확인 가능한 상태가 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="df363-138">Lync 사용자는 해당 연락처에 대 한 확인 되지 않은 연락처를 초대 하 여 Lync 사용자를 자신의 연락처 목록에 추가할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="df363-139">예를 들어 Google GTalk는 Lync Server와 관련 하 여 공용으로 확인 된 XMPP 서비스는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="df363-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="df363-140">GTalk 사용자는 Lync 사용자가 보낸 명시적 초대가 없는 경우 Lync 사용자를 연락처로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="df363-141">스트림 협상과 보안 방법 (TLS (전송 계층 보안) 및 SASL (소프트웨어 인증 및 보안 레이어)에 대 한 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="df363-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="df363-142">**Xmpp 표준 파운데이션** (XSF) 및 **Internet 공학적 작업 포스** (IETF)는 TLS 클라이언트 인증서, TLS 서버 인증서 및 SASL 메커니즘을 사용 하 고 관리 하기 위한 규칙 및 표준 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-142">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism.</span></span> <span data-ttu-id="df363-143">TLS 및 SASL을 사용 하는 것은 XMPP 스트림을 보호 하는 데 필요한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-143">Using TLS and SASL is the required process for securing the XMPP stream.</span></span> <span data-ttu-id="df363-144">XMPP 표준 문서 **Xmpp-0178**에서 "PKIX 인증서와 함께 SASL 외부 메커니즘을 사용 하기 위한 권장 프로토콜 흐름을 지정 합니다. 특히 xmpp 서비스에서 TLS가 필수 인 경우에는이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df363-144">From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.”</span></span> <span data-ttu-id="df363-145">XSF 설명서에 명시 된 대로 PKIX는 공개 키 인프라 (PKI 라고도 함)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df363-145">PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="df363-146">XEP 요구 사항에 대 한 자세한 내용은 XSF 문서 XEP-0178을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df363-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="df363-147">자세한 내용은 "XEP-0178: SASL 외부의 인증서 사용에 대 한 모범 사례"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df363-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="df363-148">IETF 문서 "확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP): Core", 섹션 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df363-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="df363-149">**TLS 협상**.</span><span class="sxs-lookup"><span data-stu-id="df363-149">**TLS Negotiation**.</span></span> <span data-ttu-id="df363-150">TLS 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="df363-151">XMPP 서비스는 TLS를 요구 하거나 TLS 옵션을 만들거나 해당 TLS가 지원 되지 않는 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="df363-152">선택 항목을 선택 하면 필수적으로 협상을 결정할 수 있도록 XMPP 서비스에 대 한 요구 사항이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="df363-153">SASL, TLS 및 Dialback 협상 (유효 하지 않은 알려진 오류 구성 포함)에 대 한 가능한 모든 설정 및 세부 정보를 보려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df363-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-154">**필요**합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-154">**Required**.</span></span> <span data-ttu-id="df363-155">XMPP 서비스에는 TLS 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-156">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-156">**Optional**.</span></span> <span data-ttu-id="df363-157">XMPP 서비스는 TLS가 필수적으로 협상 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df363-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-158">**지원 되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="df363-158">**Not Supported**.</span></span> <span data-ttu-id="df363-159">XMPP 서비스는 TLS를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="df363-160">**SASL 협상**.</span><span class="sxs-lookup"><span data-stu-id="df363-160">**SASL negotiation**.</span></span> <span data-ttu-id="df363-161">SASL 협상 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="df363-162">XMPP 서비스에는 SASL이 필요 하거나, SASL을 선택적으로 만들거나, SASL이 지원 되지 않는 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="df363-163">선택 항목을 선택 하면 파트너 XMPP 서비스에 대 한 필수-협상 결정을 위한 요구 사항이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="df363-164">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-164">SASL requires TLS.</span></span> <span data-ttu-id="df363-165">SASL을 사용 하려면 TLS가 필수 또는 선택 사항 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-165">To use SASL, TLS must either be required or optional.</span></span> <span data-ttu-id="df363-166">SASL을 필수 또는 선택 사항으로 정의 하는 구성은 모두 TLS를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-166">Any configuration that defines SASL as either required or optional must have TLS support.</span></span> <span data-ttu-id="df363-167"><STRONG>커밋을</STRONG> 클릭 하 여 변경 내용을 저장 하는 경우, tls를 필수 또는 선택 사항으로 설정 하지 않으면 SASL이 tls를 지원 해야 하며 변경 내용이 저장 되지 않은 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-167">When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved.</span></span> <span data-ttu-id="df363-168">이 오류를 해결 하려면 TLS를 <STRONG>Required</STRONG> 또는 <STRONG>Optional</STRONG>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-168">To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>.</span></span> <span data-ttu-id="df363-169">SASL을 사용할 수 없는 경우 TLS 협상이 지원 되지 않으면 SASL negotiation를 <STRONG>지원 되지 않는</STRONG>것으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-169">If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>.</span></span> <span data-ttu-id="df363-170">XMPP 서비스를 사용 하 여 TLS 및 SASL에 적합 한 협상 스트림 또는 서비스 중단이 발생할 지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-170">Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="df363-171">**필요**합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-171">**Required**.</span></span> <span data-ttu-id="df363-172">XMPP 서비스에는 SASL 협상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-173">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-173">**Optional**.</span></span> <span data-ttu-id="df363-174">XMPP 서비스는 SASL이 필수적으로 협상 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df363-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-175">**지원 되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="df363-175">**Not Supported**.</span></span> <span data-ttu-id="df363-176">XMPP 서비스는 SASL을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="df363-177">**Dialback 협상**.</span><span class="sxs-lookup"><span data-stu-id="df363-177">**Dialback negotiation**.</span></span> <span data-ttu-id="df363-178">Dialback 협상은 XSF에서 문서 **Xep-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="df363-179">서버 dialback 프로세스는 DNS (domain name system) 및 권한 있는 서버를 사용 하 여 해당 요청이 유효한 XMPP 파트너 로부터 제공 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="df363-180">이렇게 하려면 원래 서버에서 생성 된 dialback 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 받는 서버를 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="df363-181">원래 서버는 XML 스트림의 키를 결과 DNS 조회로 보내고 받는 서버를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="df363-182">XML 스트림을 통해 키를 수신 하면 받는 서버는 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="df363-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="df363-183">권한이 있는 서버는 키가 유효 하거나 유효 하지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df363-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="df363-184">유효 하지 않은 경우 받는 서버는 원래 서버에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="df363-185">키가 유효 하면 받는 서버는 id 및 키가 유효 하 고 대화를 시작할 수 있음을 원래 서버에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="df363-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="df363-186">**Dialback 협상**에는 다음과 같은 두 가지 유효한 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-187">**True**입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-187">**True**.</span></span> <span data-ttu-id="df363-188">원본 서버에서 요청을 받아야 하는 경우 XMPP 서버는 Dialback 협상을 사용 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df363-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="df363-189">**False**입니다.</span><span class="sxs-lookup"><span data-stu-id="df363-189">**False**.</span></span> <span data-ttu-id="df363-190">XMPP 서버는 Dialback 협상을 사용 하도록 구성 되어 있지 않으며 원래 서버에서 요청을 수신 해야 하는 경우 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df363-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

