---
title: Lync Server 2013:에 지 구성 요소에 대 한 인증서 요청
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
ms.openlocfilehash: 473d526bbdf8f556f167c80cc3b654f336f78070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="571e4-102">Lync Server 2013의에 지 구성 요소에 대 한 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="571e4-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="571e4-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="571e4-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="571e4-104">외부 사용자 액세스를 지원하는 데 필요한 인증서에는 공용 CA(인증 기관)에서 발급한 인증서와 내부 엔터프라이즈 CA에서 발급한 인증서가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="571e4-105">에 지 서버 및 역방향 프록시에 대 한 외부 인터페이스에 필요한 인증서는 공용 CA에서 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="571e4-106">외부 인터페이스에 필요한 인증서는 공용 CA 또는 내부 엔터프라이즈 CA에서 발급한 인증서일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="571e4-107">내부 Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 ca 또는 Windows 2012 Server 2008 R2 CA를 사용 하 여 공용 인증서를 사용 하는 비용에도 이러한 인증서를 만들어 저장 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="571e4-108">인증서 요청 처리 시간 (특히 공용 CAs에 대 한 요청)을 처리할 때에는에 지 서버 구성 요소에 대 한 배포를 시작할 때에도 사용할 수 있도록 해당 서버에 대 한 인증서를 빠르게 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="571e4-109">에 지 서버에 대 한 인증서 요구 사항을 요약 한 내용은 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="571e4-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="571e4-110">내부 에지 인증서에 공용 CA를 사용하도록 선택할 수 있긴 하지만 인증서 비용을 최소화하는 대신 그러한 다른 인증서에 내부 엔터프라이즈 CA를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="571e4-111">에 지 서버에 대 한 인증서 요구 사항을 요약 한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="571e4-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="571e4-112">에 지 서버를 설치할 때 설치 프로그램에는 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013에 대 한 edge 인증서 설정</A> 섹션에 설명 된 대로 인증서 요청, 할당 및 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="571e4-113">Edge 서버를 설치 하기 전에 인증서를 요청 하려는 경우 (예:에 지 서버 구성 요소의 실제 배포 중에 시간을 절약 하는 것과 같은) 내부 서버를 사용 하 여 인증서를 내보낼 수 있게 하 고 모든 작업을 포함 하는 경우 필요한 주체 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="571e4-114">이 설명서에서는 내부 서버를 사용하여 인증서를 요청하는 절차는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="571e4-115">공용 CA에서 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="571e4-115">Request certificates from a public CA</span></span>

<span data-ttu-id="571e4-116">에 지 서버 배포에는 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V 인증 서비스에 사용 되는에 지 서버의 외부 인터페이스에 대 한 단일 공용 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="571e4-117">A/V 인증 서비스가 풀의 모든에 지 서버에서 동일한 키를 사용 하 게 하려면이 인증서에는 내보낼 수 있는 개인 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="571e4-118">Microsoft Internet Security and 가속도 (ISA) 서버 2006 또는 Microsoft Forefront Threat Management Gateway 2010와 함께 사용 되는 역방향 프록시에도 공용 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="571e4-119">내부 엔터프라이즈 CA에서 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="571e4-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="571e4-p106">내부 에지 인터페이스에 필요한 인증서는 공용 CA(인증 기관) 또는 내부 CA에서 발급한 인증서일 수 있습니다. 내부 엔터프라이즈 CA를 사용하면 인증서 비용을 최소화할 수 있습니다. 조직에 내부 CA가 배포되어 있는 경우에는 내부 에지용 인증서를 내부 CA에서 발급해야 합니다. 내부 인증서에 대해 내부 엔터프라이즈 CA를 사용하면 인증서 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e4-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="571e4-124">에 지 구성 요소에 대 한 인증서 요구 사항을 요약 한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="571e4-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="571e4-125">공용 CA를 사용 하 여 인증서를 가져오는 방법에 대 한 자세한 내용은 [Lync Server 2013에서에 지 구성 요소에 대 한 인증서 요청](lync-server-2013-request-certificates-for-edge-components.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="571e4-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="571e4-126">인증서 요청, 설치 및 할당에 대 한 자세한 내용은 [Set Up Edge certificate For Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="571e4-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

