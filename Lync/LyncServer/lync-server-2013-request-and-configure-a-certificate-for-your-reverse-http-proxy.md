---
title: HTTP 역방향 프록시에 대한 인증서 요청 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="2da04-102">Lync Server 2013에서 HTTP 역방향 프록시에 대한 인증서 요청 및 구성</span><span class="sxs-lookup"><span data-stu-id="2da04-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2da04-103">_**마지막으로 수정한 주제:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="2da04-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="2da04-104">Microsoft Lync를 실행 하는 서버에 대 한 루트 CA (인증 기관) 인증서를 설치 해야 합니다 (서버 인증서를 발급 하는 CA 인프라에 대 한 microsoft Forefront 위협 관리 게이트웨이 2010 또는 IIS ARR을 사용할 수 있습니다.) 서버 2013.</span><span class="sxs-lookup"><span data-stu-id="2da04-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="2da04-105">또한 역방향 프록시 서버에 공용 웹 서버 인증서를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="2da04-106">이 인증서의 주체 대체 이름에는 원격 액세스를 사용 하도록 설정 된 사용자에 게 가정용으로 지정 되는 각 풀의 게시 된 외부 Fqdn (정식 도메인 이름)과, 내에서 사용할 모든 디렉터 또는 디렉터 풀의 외부 Fqdn이 포함 됩니다. 해당 Edge 인프라.</span><span class="sxs-lookup"><span data-stu-id="2da04-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="2da04-107">또한 제목 대체 이름에는 모임 간단한 URL, 전화 접속 간단한 URL, 모바일 응용 프로그램을 배포 하는 경우 다음 표에 표시 된 대로 자동 검색 서비스 URL을 사용 하는 경우와 같이 해당 사용자에 게 연결 하는 방법에 대</span><span class="sxs-lookup"><span data-stu-id="2da04-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="2da04-108">값</span><span class="sxs-lookup"><span data-stu-id="2da04-108">Value</span></span></th>
<th><span data-ttu-id="2da04-109">예</span><span class="sxs-lookup"><span data-stu-id="2da04-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2da04-110">주체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="2da04-111">풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="2da04-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="2da04-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da04-113">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-114">풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="2da04-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="2da04-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="2da04-116">주체 이름은 주체 대체 이름에도 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da04-117">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-118">선택적 디렉터 웹 서비스 (디렉터가 배포 된 경우)</span><span class="sxs-lookup"><span data-stu-id="2da04-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="2da04-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da04-120">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-121">간단한 모임 URL</span><span class="sxs-lookup"><span data-stu-id="2da04-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="2da04-122">모든 모임 단순 Url은 주체 대체 이름에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="2da04-123">각 SIP 도메인에는 활성 모임의 간단한 URL이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="2da04-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da04-125">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-126">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="2da04-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="2da04-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da04-128">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-129">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="2da04-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="2da04-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da04-131">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="2da04-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="2da04-132">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="2da04-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2da04-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da04-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="2da04-134">Microsoft Exchange Server를 사용 하는 경우에도 Exchange 자동 검색 및 웹 서비스 Url에 대 한 리버스 프록시 규칙도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="2da04-135">내부 배포가 둘 이상의 Standard Edition server 또는 프런트 엔드 풀로 구성 된 경우 각 외부 웹 팜 FQDN에 대해 웹 게시 규칙을 구성 해야 하며 각각에 대 한 인증서 및 웹 수신기가 필요 하거나 인증서를 받아야 합니다. 해당 주체 대체 이름에는 모든 풀에서 사용 되는 이름이 포함 되어 있으며, 웹 수신기에 할당 하 고, 여러 웹 게시 규칙 간에 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="2da04-136">인증서 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="2da04-136">Create a Certificate Request</span></span>

<span data-ttu-id="2da04-137">역방향 프록시에 대 한 인증서 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="2da04-138">다른 컴퓨터에서 요청을 만들지만 공개 인증 기관에서 받은 인증서를 개인 키를 사용 하 여 내보낸 후 역방향 프록시로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2da04-139">인증서 요청 또는 CSR (인증서 서명 요청)는 신뢰할 수 있는 CA (인증 기관)에 대 한 요청으로, 요청 하는 컴퓨터의 공개 키에 대 한 유효성을 검사 하 고 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="2da04-140">인증서가 생성 되 면 공개 키와 개인 키가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="2da04-141">공개 키만 공유 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="2da04-142">이름에서 알 수 있듯이 공개 키는 공개 요청에 대해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="2da04-143">공개 키는 정보를 안전 하 게 교환 하 고 컴퓨터 id를 확인 해야 하는 클라이언트, 서버 및 기타 요청자에 의해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="2da04-144">개인 키는 보호 된 상태로 유지 되며 공개 키를 사용 하 여 암호화 된 메시지의 암호를 해독 하기 위해 키 쌍을 만든 컴퓨터 에서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="2da04-145">개인 키를 다른 목적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="2da04-146">역방향 프록시를 위해 데이터 암호화가 기본 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="2da04-147">Secondarily는 인증서 키 수준의 인증서 인증을 사용할 수 있으며, 요청자에 게 컴퓨터의 공개 키가 있거나 해당 공개 키가 있는 컴퓨터가 실제로 주장 하는 컴퓨터 인지 확인 하는 경우에만 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="2da04-148">Edge 서버 인증서와 역방향 프록시 인증서를 동시에 계획 하는 경우 두 개의 인증서 요구 사항 사이에 상당한 유사도가 있다는 것을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="2da04-149">Edge 서버 인증서를 구성 하 고 요청할 때 Edge 서버와 리버스 프록시 제목 대체 이름을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="2da04-150">인증서와 개인 키를 내보내고 내보낸 파일을 리버스 프록시로 복사한 다음, 이후 절차에서 필요에 따라 인증서/키 쌍을 가져와 필요한 경우 역방향 프록시에 대해 동일한 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="2da04-151">Lync server 2013 및 lync server 2013의 역방향&nbsp;프록시 <A href="lync-server-2013-certificate-summary-reverse-proxy.md">인증서 요약-리버스 프록시의</A>edge 서버 계획에 대 한 edge server<A href="lync-server-2013-plan-for-edge-server-certificates.md">요금제</A> 의 인증서 요구 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2da04-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="2da04-152">내보낼 수 있는 개인 키를 사용 하 여 인증서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="2da04-153">풀링된 Edge 서버에는 내보낼 수 있는 개인 키를 사용 하 여 인증서 및 인증서 요청 만들기가 필요 하므로,이는 일반적인 관행으로, Edge 서버용 Lync Server 배포 마법사의 인증서 마법사를 사용 하 여 <STRONG>개인 키 내보내기 가능한 사용자 만들기</STRONG> 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="2da04-154">공용 인증 기관에서 인증서 요청을 받은 후에는 인증서와 개인 키를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="2da04-155">개인 키를 사용 하 여 인증서를 만들고 내보내는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013의 외부에 지 인터페이스</A> 에 대 한 인증서를 설정 하는 항목의 "풀의 Edge 서버의 개인 키를 사용 하 여 인증서를 내보내려면" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2da04-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="2da04-156">인증서의 확장명은 .pfx 형식 이어야 합니다 <STRONG>.</STRONG></span><span class="sxs-lookup"><span data-stu-id="2da04-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="2da04-157">인증서와 개인 키가 할당 될 컴퓨터에서 인증서 서명 요청을 생성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="2da04-158">**인증서 서명 요청 만들기**</span><span class="sxs-lookup"><span data-stu-id="2da04-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="2da04-159">MMC (Microsoft Management Console)를 열고 인증서 스냅인을 추가 하 고 **컴퓨터**를 선택한 다음 **개인**을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="2da04-160">MMC (Microsoft Management Console)에서 인증서 콘솔을 만드는 방법에 대 한 자세한 내용은을 참조 [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)하세요.</span><span class="sxs-lookup"><span data-stu-id="2da04-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="2da04-161">**인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **고급 작업**을 클릭 하 고 **사용자 지정 요청 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="2da04-162">**인증서 등록** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="2da04-163">**인증서 등록 정책 선택** 페이지의 **사용자 지정 요청**에서 **등록 정책 없이 진행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="2da04-164">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-164">Click **Next**.</span></span>

5.  <span data-ttu-id="2da04-165">**사용자 지정 요청** 페이지에서 **서식 파일** 선택 **(템플릿 없음) 레거시 키**</span><span class="sxs-lookup"><span data-stu-id="2da04-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="2da04-166">다른 방법으로 인증서 공급자가 지정 하지 않는 한 **기본 확장명** 을 선택 하지 않은 상태로 유지 하 **고 \#PKCS 10**의 **요청 형식** 선택 항목을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="2da04-167">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-167">Click **Next**.</span></span>

6.  <span data-ttu-id="2da04-168">**인증서 정보** 페이지에서 **세부 정보**를 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="2da04-169">**일반** 탭의 **인증서 속성** 페이지에서 **이름** 필드에이 인증서의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="2da04-170">필요에 따라 **설명** 필드에 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="2da04-171">일반적으로 이름 및 설명은 관리자가 인증서 용도를 식별 하는 데 사용 됩니다 (예: **Lync Server의 리버스 프록시 수신기**).</span><span class="sxs-lookup"><span data-stu-id="2da04-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="2da04-172">**제목** 탭을 선택 합니다. 유형의 **주체 이름** 에서 주체 \*\*\*\* 이름 유형의 **일반 이름을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="2da04-173">해당 **값**에는 리버스 프록시에 사용할 주체 이름을 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="2da04-174">이 항목의 표에 나와 있는 예제에서는 주체 이름이 webext.contoso.com 주체 이름에 대 한 값 필드에 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="2da04-175">**대체 이름**아래의 **제목** 탭에서 **유형에**대 한 드롭다운에서 **DNS** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="2da04-176">인증서에 대해 요구 하는 정의 된 각 주체의 대체 이름에 대해 정규화 된 도메인 이름을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="2da04-177">예를 들어 표에는 세 가지 주제 대체 이름인 meet.contoso.com, dialin.contoso.com 및 lyncdiscover.contoso.com이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="2da04-178">**값** 필드에 meet.contoso.com를 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="2da04-179">정의 해야 하는 각 주체의 대체 이름에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="2da04-180">**인증서 속성** 페이지에서 **확장** 탭을 클릭 합니다. 이 페이지에서는 **키 사용** 및 확장 키 사용 **(용도 정책)** 에서 확장 키 사용을 통해 암호화 키 용도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="2da04-181">**키 용도** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="2da04-182">사용 가능한 옵션에서 **디지털 서명을**클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="2da04-183">**키 암호화**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="2da04-184">**이 키** 를 사용 하는 데 필요한 확인란의 선택을 취소 한 경우 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="2da04-185">확장 된 **키 사용 (응용 프로그램 정책)** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="2da04-186">사용 가능한 옵션에서 **서버 인증**을 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="2da04-187">**클라이언트 인증**을 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="2da04-188">**확장 키** 사용을 중요 한 것으로 설정 확인란을 선택 하는 경우 확인란을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="2da04-189">선택 해야 하는 키 용도 확인란에 반대 되는 것은 확장 된 키 사용 확인란이 선택 되어 있지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="2da04-190">**인증서 속성** 페이지에서 **개인 키** 탭을 클릭 합니다. **키 옵션** 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="2da04-191">**키 크기**의 경우 드롭다운에서 **2048** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="2da04-192">이 인증서를 대상으로 하는 역방향 프록시 이외의 컴퓨터에서이 키 쌍과 CSR을 생성 하는 경우 **개인 키를 내보낼 수 있도록 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="2da04-194">보안 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="2da04-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="2da04-195"><strong>개인 키를 내보낼 수 있도록 만들기</strong> 를 선택 하는 것은 일반적으로 팜에 있는 각 컴퓨터에 인증서와 개인 키를 복사할 때 발생 하는 하나 이상의 역방향 프록시가 있는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="2da04-196">내보낼 수 있는 개인 키를 허용 하는 경우 인증서와이를 생성 하는 컴퓨터를 추가로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="2da04-197">개인 키 (손상 된 경우)는 해당 인증서를 쓸모 없는 상태로 렌더링 하 고 컴퓨터 또는 컴퓨터를 외부 액세스 및 기타 보안 취약점에 노출 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="2da04-198">**개인 키** 탭에서 **키 유형** 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="2da04-199">**Exchange** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="2da04-200">**확인** 을 클릭 하 여 설정한 **인증서 속성** 을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="2da04-201">**인증서 등록** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="2da04-202">**오프 라인 요청을 어디에 저장 하 시겠습니까?** 페이지에서 **파일 이름과** 인증서 서명 요청을 저장할 **파일 형식을** 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="2da04-203">**파일 이름** 입력 필드에 요청의 경로와 파일 이름을 입력 하거나 **찾아보기를** 클릭 하 여 파일의 위치를 선택 하 고 요청에 대 한 파일 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="2da04-204">**파일 형식**에 대해 **Base 64** 또는 **Binary**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="2da04-205">공급 업체에서 인증서에 대해 다른 방법으로 지시가 있지 않은 한 **기본 64** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="2da04-206">이전 단계에서 저장 한 요청 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="2da04-207">공용 인증 기관에 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2da04-208">Microsoft는 통합 커뮤니케이션 목적에 대 한 요구 사항을 충족 하는 공개 Ca를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="2da04-209">목록은 다음 기술 자료 문서에서 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da04-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

