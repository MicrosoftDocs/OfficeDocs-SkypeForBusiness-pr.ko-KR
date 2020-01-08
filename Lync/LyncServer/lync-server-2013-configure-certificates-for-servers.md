---
title: 'Lync Server 2013: 서버에 대한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="059a5-102">Lync Server 2013에서 서버에 대한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="059a5-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059a5-103">_**마지막으로 수정한 주제:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="059a5-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="059a5-104">이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 올바른 사용 권한을 위임한 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="059a5-105">사용 권한 위임에 대 한 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="059a5-106">조직의 인증서 요청과 요구 사항에 따라 다른 그룹 구성원 자격이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="059a5-107">PKI (공개 키 인프라) CA (인증 기관)를 관리 하는 그룹에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="059a5-108">Lync Server 2013에는 Windows 7, Windows Server 512 R2, Windows Server 2008, Windows Vista를 실행 하는 클라이언트의 연결에 대 한 다이제스트 해시 및 서명 알고리즘의 SHA-1 제품군 (SHA-1-2에서 다이제스트 길이 224, 256, 384 또는 2008 비트)에 대 한 지원이 포함 됩니다. Windows XP 운영 체제 (Lync Phone Edition 외)</span><span class="sxs-lookup"><span data-stu-id="059a5-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="059a5-109">SHA-2 제품군을 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 동일한 비트 길이 다이제스트를 사용 하 여 인증서를 발급할 수 있는 공용 CA에서 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="059a5-110">인증서를 사용 하는 클라이언트 및 서버, 그리고 클라이언트와 서버가 통신 하는 다른 컴퓨터 및 장치에 따라 달라 지는 선택 항목은 사용자가 사용 하는 알고리즘을 사용 하는 방법을 알고 있어야 하는 경우에만 해당 됩니다. 인증.</span><span class="sxs-lookup"><span data-stu-id="059a5-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="059a5-111">운영 체제에서 지원 되는 다이제스트 길이와 일부 클라이언트 응용 프로그램에 대 한 자세한 내용은<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="059a5-112">각 Standard Edition server 또는 프런트 엔드 서버는 최대 4 개의 인증서 (oAuthTokenIssuer 인증서, 기본 인증서, 웹 내부 인증서, 웹 외부 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="059a5-113">그러나 적절 한 주체 대체 이름 항목과 oAuthTokenIssuer 발급자 인증서를 사용 하 여 단일 기본 인증서를 요청 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="059a5-114">인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="059a5-115">OAuthTokenIssuer 인증서 요청, 할당 및 설치에 대 한 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="059a5-116">다음 절차를 사용 하 여 Standard Edition server 또는 프런트 엔드 서버 인증서를 요청 하 고 할당 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="059a5-117">각 프런트 엔드 서버에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="059a5-118">다음 절차에서는 조직과 오프 라인 요청 처리를 통해 배포 된 내부 엔터프라이즈 PKI에서 인증서를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="059a5-119">공용 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013에서 내부 서버의 인증서 요구 사항을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="059a5-120">또한이 절차에서는 프런트 엔드 서버 설정 중에 인증서를 요청, 할당 및 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="059a5-121">이 배포 설명서의 <A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 섹션에 대 한 요청 인증서 미리 보기 (선택 사항)</A> 에 설명 된 대로 인증서를 미리 요청 했거나, 인증서를 얻기 위해 조직에 배포 된 내부 엔터프라이즈 PKI를 사용 하지 않는 경우에는이 절차를 적절 하 게 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="059a5-122">프런트 엔드 서버에 대 한 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="059a5-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="059a5-123">Lync Server 배포 마법사에서 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="059a5-124">**인증서 마법사** 페이지에서 **요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="059a5-125">**인증서 요청** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="059a5-126">**지연 또는 즉시 요청** 페이지에서 **다음**을 클릭 하 여 기본적으로 **온라인 인증 기관에 게 요청을 보냅니다** 옵션으로 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-126">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="059a5-127">이 옵션을 선택 하는 경우 자동 온라인 등록을 사용 하는 내부 CA를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-127">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="059a5-128">요청을 지연 하는 옵션을 선택 하면 인증서 요청 파일을 저장할 이름과 위치를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-128">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="059a5-129">인증서 요청은 조직 내부 또는 공개 CA에서 CA에 의해 표시 되 고 처리 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-129">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="059a5-130">그런 다음 인증서 응답을 가져와 적절 한 인증서 역할에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-130">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="059a5-131">**Ca (인증 기관 선택)** 페이지에서 **환경에서 검색 된 목록에서 CA 선택** 옵션을 선택한 다음 목록에서 알려진 (Active Directory 도메인 서비스에서 등록을 통해) ca를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="059a5-132">또는 **다른 인증 기관 지정** 옵션을 선택 하 고 상자에 다른 CA의 이름을 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="059a5-133">**인증 기관 계정** 페이지에 CA에서 인증서 요청을 요청 하 고 처리 하는 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="059a5-134">미리 인증서를 요청 하는 데 사용자 이름 및 암호가 필요한 경우를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="059a5-135">CA 관리자에 게 필요한 정보를 포함 하 고 있으며이 단계에서 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="059a5-136">대체 자격 증명을 제공 해야 하는 경우 확인란을 선택 하 고 텍스트 상자에 사용자 이름 및 암호를 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="059a5-137">**대체 인증서 서식 파일 지정** 페이지에서 기본 웹 서버 서식 파일을 사용 하려면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="059a5-138">조직에서 기본 웹 서버 CA 서식 파일 대신 사용할 서식 파일을 만든 경우 확인란을 선택 하 고 대체 서식 파일의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-138">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template.</span></span> <span data-ttu-id="059a5-139">CA 관리자가 정의한 서식 파일 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-139">You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="059a5-140">**이름 및 보안 설정** 페이지에서 인증서와 용도를 식별 하는 데 사용할 **이름을** 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="059a5-141">비워 두면 이름이 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="059a5-142">키의 **비트 길이** 를 설정 하거나 기본값 2048 비트를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="059a5-143">인증서와 개인 키를 다른 시스템으로 이동 하거나 복사 하도록 결정 한 경우 **인증서의 개인 키를 내보낼** 수 있도록 표시를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="059a5-144">Lync Server 2013에는 내보내기 가능한 개인 키에 대 한 최소 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="059a5-145">이러한 위치 중 하나는 풀의 각 인스턴스에 대 한 개별 인증서 대신 미디어 릴레이 인증 서비스에서 인증서 복사본을 사용 하는 Edge 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="059a5-146">**조직 정보** 페이지에서 조직 정보를 선택적으로 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="059a5-147">**지리적 정보** 페이지에서 필요에 따라 지리 정보를 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="059a5-148">**주체 이름/주체 대체 이름** 페이지에서 추가할 주체의 대체 이름을 검토 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="059a5-149">**Sip 도메인 설정** 페이지에서 **sip 도메인**을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="059a5-150">**추가 제목 대체 이름 구성** 페이지에서 나중에 추가 SIP 도메인에 필요할 수 있는 모든 항목을 포함 하 여 필요한 추가 주체 대체 이름을 추가 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="059a5-151">**인증서 요청 요약** 페이지에서 요약의 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-151">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="059a5-152">정보가 올바르면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-152">If the information is correct, click **Next**.</span></span> <span data-ttu-id="059a5-153">설정을 수정 하거나 변경 해야 하는 경우 적절 한 페이지로 **뒤로** 를 클릭 하 여 수정 또는 수정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-153">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="059a5-154">**명령 실행** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="059a5-155">**온라인 인증서 요청 상태** 페이지에서 반환 된 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="059a5-156">인증서가 로컬 인증서 저장소에 발급 되 고 설치 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="059a5-157">발급 되 고 설치 되었지만 유효 하지 않은 것으로 보고 되는 경우 CA 루트 인증서가 서버의 신뢰할 수 있는 루트 CA 저장소에 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="059a5-158">신뢰할 수 있는 루트 CA 인증서를 검색 하는 방법에 대 한 CA 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="059a5-159">검색 된 인증서를 확인 해야 하는 경우 **인증서 정보 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="059a5-160">기본적으로 **Lync Server 인증서 용도에 인증서를 할당 하** 는 확인란이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="059a5-161">수동으로 인증서를 할당 하려면 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="059a5-162">이전 페이지에서 **Lync Server 인증서 용도에 인증서 할당** 확인란의 선택을 취소 한 경우 **인증서 할당** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="059a5-163">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-163">Click **Next**.</span></span>

18. <span data-ttu-id="059a5-164">**인증서 저장소** 페이지에서 요청한 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-164">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="059a5-165">인증서를 보려면 **인증서 정보 보기**를 클릭 하 고 **다음** 을 클릭 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-165">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="059a5-166"><STRONG>온라인 인증서 요청 상태</STRONG> 페이지에서 인증서가 유효 하지 않은 인증서 등의 문제를 보고 한 경우 실제 인증서를 보면 문제 해결을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="059a5-167">인증서가 유효 하지 않게 될 수 있는 두 가지 문제가 앞에서 언급 한 신뢰할 수 있는 루트 CA 인증서와 인증서와 연결 된 개인 키가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="059a5-168">이러한 두 가지 문제를 해결 하려면 CA 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059a5-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="059a5-169">**인증서 할당 요약** 페이지에서 제공 된 정보를 검토 하 여이 인증서가 할당 되어야 하는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="059a5-170">명령 **실행** 페이지에서 명령의 출력을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-170">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="059a5-171">할당 프로세스를 검토 하거나 오류 또는 경고가 발생 한 경우 **로그 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-171">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="059a5-172">검토가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-172">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="059a5-173">**인증서 마법사** 페이지에서 인증서 **상태가** "할당 됨" 인지 확인 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059a5-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="059a5-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="059a5-174">See Also</span></span>


[<span data-ttu-id="059a5-175">Lync Server 2013에 대한 인증서 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="059a5-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

