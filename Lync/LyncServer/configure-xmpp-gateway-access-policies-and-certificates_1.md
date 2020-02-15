---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f622ed573a6d30d35b55d2c07ec21ef79b46424
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="53544-102">XMPP 게이트웨이 액세스 정책 및 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="53544-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53544-103">_**마지막으로 수정 된 항목:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="53544-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="53544-p101">XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)에 따라 외부 배포를 정의합니다. XMPP 구성을 사용하면 Lync 사용자가 다음을 통해 MPP 도메인 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53544-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="53544-106">IM 및 현재 상태 – 개인 간에만</span><span class="sxs-lookup"><span data-stu-id="53544-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="53544-107">Lync 클라이언트에서 XMPP 페더레이션 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="53544-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="53544-p102">XMPP(eXtensible Messaging and Presence Protocol) 페더레이션 파트너 지원을 위한 정책을 구성하는 경우 SIP(Session Initiation Protocol) 서비스 공급자(예: Windows Live)나 SIP 페더레이션된 도메인의 사용자가 아닌 XMPP 페더레이션된 도메인의 사용자에게 적용됩니다. 사용자가 연락처를 추가하고 통신하도록 허용할 각 XMPP 페더레이션된 도메인에 대해 XMPP 페더레이션 파트너를 구성할 수 있습니다. 정책을 만들었으면 XMPP 게이트웨이 인증서를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53544-111">XMPP 게이트웨이 마이그레이션을 시작 하려면 Lync Server 2013 XMPP 게이트웨이를 배포 하 고 사용자가 Lync Server 2013 XMPP 게이트웨이를 사용할 수 있도록 액세스 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="53544-112">다음 단계를 수행 하기 전에 모든 사용자를 Lync Server 2013 배포로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="53544-113">자세한 내용은 <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway In Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53544-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="53544-114">사용자가 Lync Server 2013 XMPP 게이트웨이를 사용할 수 있도록 외부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="53544-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="53544-115">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="53544-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="53544-116">왼쪽 탐색 모음에서 **Federation and External Access(페더레이션 및 외부 액세스)** 를 클릭하고 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="53544-117">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="53544-118">외부 액세스 사용자 정책의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="53544-119">외부 액세스 사용자 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="53544-120">**페더레이션 사용자와의 통신 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="53544-121">Select **Enable communications with XMPP federated users(XMPP 페더레이션 사용자와의 통신 사용)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="53544-122">**커밋**을 클릭하여 사이트 또는 사용자 정책에 대한 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

