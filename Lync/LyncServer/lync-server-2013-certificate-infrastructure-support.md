---
title: Lync Server 2013 인증서 인프라 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea4ea71564feca6c23c6d9e16b4ca336fa95e87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="c5595-102">Lync Server 2013의 인증서 인프라 지원</span><span class="sxs-lookup"><span data-stu-id="c5595-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5595-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c5595-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c5595-104">Lync Server 2013에서는 TLS (전송 계층 보안) 및 MTLS (상호 TLS) 연결을 지원 하기 위해 PKI (공개 키 인프라)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="c5595-105">기본적으로 Lync Server 2013는 클라이언트와 서버 간 연결에 TLS를 사용 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="c5595-106">서버 간 연결에는 MTLS가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="c5595-107">MTLS 인증서는 Lync Server 2013에 대해 신뢰할 수 있는 Ca (인증 기관)에서 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="c5595-108">Lync Server는 다음 CAs에서 발급 된 인증서를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="c5595-109">내부 CA에서 발급한 인증서:</span><span class="sxs-lookup"><span data-stu-id="c5595-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="c5595-110">Windows Server 2003 운영 체제 CA</span><span class="sxs-lookup"><span data-stu-id="c5595-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="c5595-111">Windows Server 2008 운영 체제 CA</span><span class="sxs-lookup"><span data-stu-id="c5595-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="c5595-112">Windows Server 2008 R2 운영 체제 CA</span><span class="sxs-lookup"><span data-stu-id="c5595-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="c5595-113">Windows Server 2012 운영 체제 CA</span><span class="sxs-lookup"><span data-stu-id="c5595-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="c5595-114">Windows Server 2012 R2 운영 체제 CA</span><span class="sxs-lookup"><span data-stu-id="c5595-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="c5595-115">공용 CA에서 발급한 인증서</span><span class="sxs-lookup"><span data-stu-id="c5595-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="c5595-116">Exchange 2013와 같은 다른 응용 프로그램 및 서버와 통신 하려면 다른 응용 프로그램 및 제품에서 지 원하는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="c5595-117">2013 릴리스의 경우 Lync Server 2013 및 기타 Microsoft 서버 제품 (Exchange 2013 및 SharePoint Server 포함)은 서버 간 인증 및 권한 부여를 위한 OAuth (Open Authorization) 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="c5595-118">자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5595-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="c5595-119">Windows 7 운영 체제, Windows Server 2008 R2 운영 체제 및 Microsoft Office Communicator 2007 Phone Edition을 실행 하는 클라이언트의 연결의 경우 Lync Server 2013에는 SHA-256을 사용 하 여 서명 된 인증서에 대 한 지원이 포함 되어 있지만 필요 하지는 않습니다. 암호화 해시 함수</span><span class="sxs-lookup"><span data-stu-id="c5595-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="c5595-120">SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5595-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="c5595-121">인증서 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 인증서 인프라 요구 사항](lync-server-2013-certificate-infrastructure-requirements.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5595-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="c5595-122">인증서와 함께 와일드 카드를 사용 하는 방법에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 와일드 카드 인증서 지원](lync-server-2013-wildcard-certificate-support.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5595-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

