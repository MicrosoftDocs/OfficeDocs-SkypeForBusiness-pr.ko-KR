---
title: XMPP (extensible messaging and 거점 protocol) 페더레이션 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f95a8e53de2c11473d8424eb2bc794e41aa7d1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="1e89c-102">Lync Server 2013의 XMPP (extensible messaging and 거점 protocol) 페더레이션 계획</span><span class="sxs-lookup"><span data-stu-id="1e89c-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e89c-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1e89c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1e89c-104">이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와의 페더레이션을 허용 하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP (extensible messaging and 거점 protocol) 게이트웨이를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="1e89c-105">Microsoft Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="1e89c-106">XMPP 기능은에 지 서버에서 실행 되는 XMPP 프록시 및 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="1e89c-107">XMPP의 배포 및 구성은 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 에서 설명 하며, 방화벽에 포트 및 프로토콜 규칙을 정의 하 고, 인증서를 구성 하 고, DNS 레코드를 추가 하 여 조직에서 xmpp를 지원 하기 위한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="1e89c-108">이 섹션의 다음 항목에서는 배포에 대해 XMPP 페더레이션을 계획 하는 데 필요한 정보를 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1e89c-109">Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="1e89c-110">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e89c-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e89c-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="1e89c-111">In This Section</span></span>

  - [<span data-ttu-id="1e89c-112">Lync Server 2013의 인증서 요약-XMPP (Extensible messaging and 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="1e89c-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="1e89c-113">포트 요약-Lync Server 2013의 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="1e89c-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="1e89c-114">Lync Server 2013의 DNS 요약-XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="1e89c-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e89c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e89c-115">See Also</span></span>


[<span data-ttu-id="1e89c-116">Lync Server 2013에서 XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="1e89c-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="1e89c-117">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="1e89c-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="1e89c-118">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="1e89c-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="1e89c-119">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e89c-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="1e89c-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e89c-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="1e89c-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e89c-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

