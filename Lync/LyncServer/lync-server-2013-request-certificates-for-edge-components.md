---
title: 'Lync Server 2013: 에지 구성 요소에 대한 인증서 요청'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="5ff2b-102">Lync Server 2013에서 에지 구성 요소에 대한 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="5ff2b-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ff2b-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="5ff2b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="5ff2b-104">외부 사용자 액세스를 지 원하는 데 필요한 인증서에는 공용 CA (인증 기관)에서 발급 한 인증서와 내부 엔터프라이즈 CA에서 발급 한 인증서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="5ff2b-105">Edge 서버의 외부 인터페이스와 역방향 프록시에 필요한 인증서는 공용 CA에서 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="5ff2b-106">내부 인터페이스에 필요한 인증서는 공용 CA 또는 내부 엔터프라이즈 CA 중 하나에서 발급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="5ff2b-107">공용 인증서를 사용 하 여 비용을 절약 하기 위해 이러한 인증서를 만드는 데 사용할 수 있는 내부 Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows server 2012 CA 또는 Windows Server 2012 R2 CA를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ff2b-108">인증서 요청 (특히 공용 Ca에 대 한 요청)을 처리 하는 데 시간이 걸릴 수 있으므로 edge 서버 구성 요소 배포를 시작할 때 사용할 수 있도록 먼저 Edge 서버에 대 한 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="5ff2b-109">Edge 서버의 인증서 요구 사항에 대 한 요약 정보는 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5ff2b-110">내부에 지 인증서에 대해 공용 CA를 사용할 수 있지만, 인증서 비용을 최소화 하는 대신 다른 인증서에 대해 내부 엔터프라이즈 CA를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="5ff2b-111">Edge 서버의 인증서 요구 사항에 대 한 요약 정보는 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ff2b-112">Edge 서버를 설치할 때 설치 프로그램에는 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013의 Edge 인증서 설정</A> 섹션에 설명 된 대로 인증서 요청, 할당 및 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="5ff2b-113">Edge 서버를 설치 하기 전에 인증서를 요청 하는 경우 (예: Edge 서버 구성 요소의 실제 배포 중에 시간을 절약 하는 경우), 인증서를 내보낼 수 있고 모든 작업을 포함 하는 경우 내부 서버를 사용 하는 것이 좋습니다. 필수 주제 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="5ff2b-114">이 설명서에서는 내부 서버를 사용 하 여 인증서를 요청 하는 절차는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="5ff2b-115">공용 CA에 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="5ff2b-115">Request certificates from a public CA</span></span>

<span data-ttu-id="5ff2b-116">Edge 서버 배포에는 Edge 서버의 외부 인터페이스에 대 한 단일 공용 인증서가 필요 하며, 여기에는 Access Edge 서비스, 웹 회의 Edge 서비스, 그리고/V 인증 서비스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="5ff2b-117">A/V 인증 서비스에서 풀의 모든 Edge 서버에 동일한 키를 사용 하도록 하려면이 인증서에는 내보낼 수 있는 개인 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="5ff2b-118">Microsoft Internet Security 및 가속 (ISA) 서버 2006 또는 Microsoft Forefront Threat Management Gateway 2010에 사용 되는 역방향 프록시에도 공용 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="5ff2b-119">내부 엔터프라이즈 CA에서 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="5ff2b-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="5ff2b-120">내부에 지 인터페이스에 필요한 인증서는 공용 ca (인증 기관) 또는 내부 CA에 의해 발급 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="5ff2b-121">내부 엔터프라이즈 CA를 사용 하 여 인증서 비용을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="5ff2b-122">조직에 내부 CA가 배포 되어 있는 경우 내부에 지에 대 한 인증서가 내부 CA에 의해 발급 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="5ff2b-123">내부 인증서에 내부 엔터프라이즈 CA를 사용 하 여 인증서 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="5ff2b-124">Edge 구성 요소의 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스를 위한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="5ff2b-125">공용 CA를 사용 하 여 인증서를 가져오는 방법에 대 한 자세한 내용은 [Lync Server 2013의 edge 구성 요소에 대 한 인증서 요청](lync-server-2013-request-certificates-for-edge-components.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="5ff2b-126">인증서 요청, 설치 및 할당에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Edge 인증서 설정을](lync-server-2013-set-up-edge-certificates.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

