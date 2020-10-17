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
ms.openlocfilehash: 1517ef4a7515a46b9237b1788c457c3aee10953d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514805"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="78351-102">Lync Server 2013에서 XMPP 파트너 구성 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="78351-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78351-103">_**마지막으로 수정 된 항목:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="78351-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="78351-104">Microsoft Lync Server 2013는 Edge 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이와 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 프록시를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="78351-105">다른 XMPP 배포 로부터의 연결을 허용 하려면 Lync Server 제어판에서 XMPP를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="78351-106">XMPP 도메인별로 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="78351-107">새 파트너 연결을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="78351-108">새 페더레이션 파트너를 만들거나 기존 구성을 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="78351-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="78351-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78351-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="78351-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="78351-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="78351-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="78351-112">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **XMPP 페더레이션 파트너**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="78351-113">새 구성을 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="78351-114">기존 구성을 편집하려면 구성을 선택하고 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="78351-115">**XMPP 페더레이션 파트너**에 대한 구성을 만들거나 편집하려면 다음 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="78351-116">**주 도메인** (필수)</span><span class="sxs-lookup"><span data-stu-id="78351-116">**Primary domain** (Required).</span></span> <span data-ttu-id="78351-117">주 도메인은 XMPP 파트너의 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="78351-118">예를 들어 XMPP 파트너 도메인 이름에는 **fabrikam.com** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="78351-119">필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-119">This is a required entry.</span></span>

8.  <span data-ttu-id="78351-120">**설명**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-120">**Description**.</span></span> <span data-ttu-id="78351-121">설명은 이러한 특정 구성에 대 한 메모 또는 기타 식별 정보에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="78351-122">이 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-122">This entry is optional.</span></span>

9.  <span data-ttu-id="78351-123">**추가 도메인**</span><span class="sxs-lookup"><span data-stu-id="78351-123">**Additional domains**.</span></span> <span data-ttu-id="78351-124">추가 도메인은 허용 되는 XMPP 통신의 일부로 포함 되어야 하는 XMPP 파트너 도메인의 일부인 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="78351-125">예를 들어 주 도메인이 **fabrikam.com**인 경우에는 xmpp를 사용 하 여 통신 하는 fabrikam.com 아래의 다른 모든 도메인을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="78351-126">예를 들어 회사 XMPP 도메인 및 정보 기술 XMPP 도메인에 대해 **corp.fabrikam.com** 및 **it.fabrikam.com** 를 fabrikam의 주 xmpp 도메인에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="78351-127">**파트너 유형**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-127">**Partner type**.</span></span> <span data-ttu-id="78351-128">**파트너 유형은** 필수 설정 이며 드롭다운 메뉴에서 세 가지 선택 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="78351-129">추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="78351-130">다음 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-130">You can select from:</span></span>
    
      - <span data-ttu-id="78351-131">**페더레이션**</span><span class="sxs-lookup"><span data-stu-id="78351-131">**Federated**.</span></span> <span data-ttu-id="78351-132">**페더레이션** 파트너 종류는 Lync Server 또는 Office Communications Server 2007 R2 파트너 배포 간의 트러스트 된 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="78351-133">**공용 확인**</span><span class="sxs-lookup"><span data-stu-id="78351-133">**Public verified**.</span></span> <span data-ttu-id="78351-134">**공용으로 확인** 된 파트너는 공급자가 확인 한 배포에 포함 된 연락처를 사용자의 대화 상대 목록에 추가할 수 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="78351-135">Lync 사용자 로부터 초대를 보내거나, Lync 사용자가 파트너 연락처의 초대를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="78351-136">**공용**확인 되지 않음</span><span class="sxs-lookup"><span data-stu-id="78351-136">**Public unverified**.</span></span> <span data-ttu-id="78351-137">**공용** 확인 되지 않은 관계는 두 배포 사이에 설정 및 확인이 가능 하지 않은 상태를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="78351-138">Lync 사용자가 자신의 대화 상대 목록에 Lync 사용자를 추가할 수 있으려면 해당 연락처의 확인 되지 않은 연락처를 초대 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="78351-139">예를 들어 Google GTalk는 Lync Server와 관련 된 공용 확인 된 XMPP 서비스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="78351-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="78351-140">GTalk 사용자는 Lync 사용자가 명시적인 초대를 보내지 않은 경우에는 Lync 사용자를 연락처로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="78351-141">스트림 협상 및 보안 방법 TLS(전송 계층 보안) 및 SASL(Software Authentication and Security Layer)에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="78351-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="78351-p110">XSF(**XMPP Standards Foundation**) 및 IETF(**Internet Engineering Task Force**)에서는 TLS 클라이언트 인증서, TLS 서버 인증서 및 SASL 메커니즘 사용/관리에 대한 규칙 및 표준 집합을 정의합니다. XMLL 스트림을 보호하려면 TLS 및 SASL을 사용해야 합니다. XMPP Standards 문서 **XEP-0178**에서 "PKIX 인증서를 사용하는 SASL EXTERNAL 메커니즘 사용을 위해 권장 프로토콜 흐름을 지정(특히 XMPP 서비스에서 TLS 협상을 필수로 지정하는 경우)"하는 작업은 PKI(공용 키 인프라)로 지칭됩니다.</span><span class="sxs-lookup"><span data-stu-id="78351-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="78351-146">XEP 요구 사항에 대 한 자세한 내용은 XSF 문서 XEP-0178를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78351-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="78351-147">자세한 내용은 "XEP-0178: SASL 외부의 인증서 사용에 대 한 모범 사례"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78351-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="78351-148">IETF 문서 "확장 가능 메시징 및 현재 상태 프로토콜 (XMPP): 코어", 섹션 5.0, STARTTLS 협상을 참조 하십시오 <https://tools.ietf.org/html/rfc6120> .</span><span class="sxs-lookup"><span data-stu-id="78351-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <https://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="78351-149">**TLS 협상**</span><span class="sxs-lookup"><span data-stu-id="78351-149">**TLS Negotiation**.</span></span> <span data-ttu-id="78351-150">TLS 협상 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="78351-151">XMPP 서비스에 대해 TLS를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="78351-152">"선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 XMPP 서비스까지 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="78351-153">유효 및 알려진 오류 구성을 포함 하 여 SASL, TLS 및 전화 접속 회의 협상에 대해 가능한 모든 설정 및 세부 정보를 확인 하려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78351-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-154">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-154">**Required**.</span></span> <span data-ttu-id="78351-155">XMPP 서비스에 TLS 협상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-156">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-156">**Optional**.</span></span> <span data-ttu-id="78351-157">XMPP 서비스는 TLS가 협상 필수 항목임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78351-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-158">**지원 되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="78351-158">**Not Supported**.</span></span> <span data-ttu-id="78351-159">XMPP 서비스가 TLS를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="78351-160">**SASL 협상**</span><span class="sxs-lookup"><span data-stu-id="78351-160">**SASL negotiation**.</span></span> <span data-ttu-id="78351-161">SASL 협상 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="78351-162">XMPP 서비스에 대해 SASL를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="78351-163">선택을 선택하면 파트너 XMPP 서비스에서 필수/협상에 대한 요구 사항을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="78351-p117">SASL에는 TLS가 필요합니다. SASL을 사용하려면 TLS가 필수 또는 선택이어야 합니다. SASL을 필수 또는 선택으로 정의하는 모든 구성에서는 TLS를 지원해야 합니다. TLS를 필수 또는 옵션으로 설정하지 않은 상태에서 <STRONG>커밋</STRONG>을 클릭하여 변경 내용을 저장하면 SASL에서 TLS를 지원해야 하며 변경 내용이 저장되지 않는다는 경고가 표시됩니다. 이 오류를 해결하려면 TLS를 <STRONG>필수</STRONG> 또는 <STRONG>선택</STRONG>으로 설정합니다. SASL 사용이 선택 사항이며 TLS 협상을 지원할 수 없는 경우에는 SASL 협상을 <STRONG>지원되지 않음</STRONG>으로 설정해야 합니다. XMPP 서비스에서 TLS 및 SASL에 대해 사용해야 하는 적절한 협상 스트림을 확인해야 하며, 그렇지 않으면 서비스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="78351-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="78351-171">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-171">**Required**.</span></span> <span data-ttu-id="78351-172">XMPP 서비스에 SASL 협상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-173">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-173">**Optional**.</span></span> <span data-ttu-id="78351-174">XMPP 서비스는 SASL가 협상 필수 항목임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78351-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-175">**지원 되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="78351-175">**Not Supported**.</span></span> <span data-ttu-id="78351-176">XMPP 서비스가 SASL를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="78351-177">**전화 접속 회의 협상**</span><span class="sxs-lookup"><span data-stu-id="78351-177">**Dialback negotiation**.</span></span> <span data-ttu-id="78351-178">전화 접속 회의 협상은 .XSF에서 문서 **Xep-220: Server 전화 접속 회의** 에 의해 정의 됩니다 <http://xmpp.org/extensions/xep-0220.html> .</span><span class="sxs-lookup"><span data-stu-id="78351-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="78351-179">Server 전화 접속 회의 프로세스는 DNS (domain name system) 및 신뢰할 수 있는 서버를 사용 하 여 요청이 유효한 XMPP 파트너 로부터 온 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="78351-180">이 작업을 수행 하기 위해 원래 서버는 생성 된 전화 접속 회의 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 수신 서버를 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="78351-181">원본 서버가 XML 스트림의 키를 결과 DNS 조회로 전송 하 고 받는 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="78351-182">XML stream에서 키를 받으면 수신 서버가 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="78351-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="78351-183">신뢰할 수 있는 서버에서 키가 유효 하거나 올바르지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78351-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="78351-184">올바르지 않으면 받는 서버가 원래 서버에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="78351-185">키가 올바르면 받는 서버가 원래 서버에 id 및 키가 유효 하며 대화를 시작할 수 있음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="78351-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="78351-186">**전화 접속 회의 협상**의 유효한 두 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-187">**True**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-187">**True**.</span></span> <span data-ttu-id="78351-188">원본 서버에서 요청을 받아야 하는 경우 XMPP 서버가 전화 접속 회의 협상을 사용 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78351-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="78351-189">**False**입니다.</span><span class="sxs-lookup"><span data-stu-id="78351-189">**False**.</span></span> <span data-ttu-id="78351-190">XMPP 서버가 전화 접속 회의 협상을 사용하도록 구성되지 않으며, 원본 서버에서 요청을 받아야 하는 경우 해당 요청은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78351-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

