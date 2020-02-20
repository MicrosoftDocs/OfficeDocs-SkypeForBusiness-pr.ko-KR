---
title: 'Lync Server 2013: 공개 키 인프라'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ba5224d6663050295c5fddf9ea08e230f78506
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="c9b18-102">Lync Server 2013 용 공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="c9b18-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9b18-103">_**마지막으로 수정 된 항목:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="c9b18-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="c9b18-104">Microsoft Lync Server 2013에서는 인증서를 사용 하 여 서버를 인증 하 고 클라이언트와 서버 간 및 서로 다른 서버 역할 간에 트러스트 체인을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="c9b18-105">Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows server 2008 및 Windows Server 2003 PKI (공개 키 인프라)에서는이 신뢰 체인을 설정 하 고 유효성을 검사 하기 위한 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="c9b18-106">인증서는 디지털 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-106">Certificates are digital IDs.</span></span> <span data-ttu-id="c9b18-107">이름으로 서버를 식별 하 고 해당 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="c9b18-108">인증서에 대 한 정보가 올바른지 확인 하려면 클라이언트 또는 서버에 연결 하는 다른 서버에서 신뢰 하는 CA에서 인증서를 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="c9b18-109">서버가 개인 네트워크에 있는 다른 클라이언트 및 서버에만 연결 하는 경우에는 CA가 엔터프라이즈 CA가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="c9b18-110">서버가 개인 네트워크 외부의 엔터티와의 상호 작용 하는 경우 공용 CA가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="c9b18-p103">인증서의 정보가 유효하더라도 인증서를 제공하는 서버가 실제로 인증서에 나와 있는 서버인지를 확인하는 방법이 있어야 합니다. 이를 위해 Windows PKI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="c9b18-p104">각 인증서는 공개 키에 연결됩니다. 인증서에 이름이 지정되어 있는 서버는 다른 위치에서는 알 수 없는 해당 개인 키를 포함합니다. 이 서버에 연결하는 클라이언트 또는 서버는 공개 키를 사용하여 임의의 정보를 암호화한 다음 서버로 보냅니다. 서버에서 이 정보의 암호를 해독하여 일반 텍스트로 반환하면 연결 대상 엔터티는 해당 서버가 인증서의 개인 키를 포함하며 인증서에 이름이 나와 있는 서버임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9b18-117">모든 공용 Ca가 Lync Server 2013 인증서의 요구 사항을 준수 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="c9b18-118">따라서 인증된 공용 CA 공급업체 목록을 참조하여 공용 인증서 요구 사항을 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="c9b18-119">자세한 내용은의 <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>통합 통신 인증서 파트너를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9b18-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="c9b18-120">CRL 배포 지점</span><span class="sxs-lookup"><span data-stu-id="c9b18-120">CRL Distribution Points</span></span>

<span data-ttu-id="c9b18-121">Lync Server 2013에서는 모든 서버 인증서에 CRL (인증서 해지 목록) 배포 지점을 하나 이상 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="c9b18-122">CDP(CRL 배포 지점)는 인증서 발급 시점 이후로 인증서가 해지되지 않았는지 그리고 인증서가 아직 유효 기간 내에 있는지 확인하기 위해 CRL을 다운로드할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="c9b18-123">CRL 배포 지점은 인증서 속성에 URL로 기록되며 일반적으로 보안 HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="c9b18-124">향상 키 사용</span><span class="sxs-lookup"><span data-stu-id="c9b18-124">Enhanced Key Usage</span></span>

<span data-ttu-id="c9b18-125">Lync Server 2013에서는 서버 인증 목적으로 모든 서버 인증서에 대해 EKU (확장 된 키 사용)를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="c9b18-126">서버 인증을 위해 EKU 필드를 구성하면 인증서를 서버 인증용으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="c9b18-127">이 EKU는 MTLS에 필수적인 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="c9b18-128">EKU에 여러 항목을 포함하여 인증서를 다양한 용도로 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9b18-p108">Live Communications Server 2003 및 Live Communications Server 2005로부터의 아웃바운드 MTLS 연결에는 클라이언트 인증 EKU가 필요했지만 이제는 더 이상 필요하지 않습니다. 그러나 공용 IM 연결을 통해 AOL에 연결하는 에지 서버에는 이 EKU가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b18-p108">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required. However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

