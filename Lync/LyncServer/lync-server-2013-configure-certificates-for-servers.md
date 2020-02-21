---
title: 'Lync Server 2013: 서버에 대 한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="0613b-102">Lync Server 2013에서 서버에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="0613b-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0613b-103">_**마지막으로 수정 된 항목:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="0613b-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="0613b-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그인하거나 올바른 권한을 위임받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="0613b-105">사용 권한 위임에 대 한 자세한 내용은 [Lync Server 2013에서 대리인 설치 권한을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0613b-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="0613b-106">조직 및 인증서 요청 요구 사항에 따라 다른 그룹 구성원 자격이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="0613b-107">PKI(공개 키 인프라) CA(인증 기관)를 관리하는 그룹에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="0613b-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0613b-108">Lync Server 2013에는 Windows 7, Windows Server 512 R2, Windows Server 2008, Windows Vista를 실행 하는 클라이언트 로부터의 연결에 대 한 다이제스트 해시 및 서명 알고리즘의 SHA-1, 256, 384 또는 2008 비트에 대 한 지원 (SHA-224 2)이 포함 되어 있습니다. Lync Phone Edition과 함께 Windows XP 운영 체제</span><span class="sxs-lookup"><span data-stu-id="0613b-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="0613b-109">SHA-2 제품군을 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 동일한 비트 길이 다이제스트를 사용 하 여 인증서를 발급할 수 있는 공용 CA에서 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="0613b-110">클라이언트와 서버에서 사용 하는 서버 및 기타 컴퓨터 및 장치와 통신 하는 데 사용 되는 해시 다이제스트 및 서명 알고리즘과 클라이언트와 서버가 서로 통신할 수 있는 사용자는 누구에 게 달려 있습니다. 기관을.</span><span class="sxs-lookup"><span data-stu-id="0613b-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="0613b-111">운영 체제 및 일부 클라이언트 응용 프로그램에서 지원 되는 다이제스트 길이에 대 한 자세한 내용은<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0613b-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="0613b-112">각 Standard Edition server 또는 프런트 엔드 서버에는 인증서가 최대 4 개 (oAuthTokenIssuer 인증서, 기본 인증서, 웹 내부 인증서 및 웹 외부 인증서)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="0613b-113">그러나 적절한 주체 대체 이름 항목을 사용하여 단일 기본 인증서는 물론 oAuthTokenIssuer 인증서도 요청하고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="0613b-114">인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0613b-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="0613b-115">OAuthTokenIssuer 인증서를 요청, 할당 및 설치 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0613b-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="0613b-116">다음 절차에 따라 Standard Edition server 또는 프런트 엔드 서버 인증서를 요청, 할당 및 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="0613b-117">각 프런트 엔드 서버에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0613b-118">다음 절차에서는 조직에서 배포한 내부 엔터프라이즈 PKI에서 인증서를 구성하는 방법 및 오프라인 요청 처리에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="0613b-119">공용 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0613b-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="0613b-120">또한이 절차에서는 프런트 엔드 서버를 설정 하는 동안 인증서를 요청, 할당 및 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="0613b-121">이 배포 설명서의 <A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 섹션에 대해 미리 인증서 요청 (선택 사항)</A> 에 설명 된 대로 인증서를 미리 요청 하거나 조직에 배포 된 내부 엔터프라이즈 PKI를 사용 하 여 인증서를 가져올 수 없는 경우에는이 절차를 적절 하 게 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="0613b-122">프런트 엔드 서버에 대해 인증서를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="0613b-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="0613b-123">Lync Server 배포 마법사에서 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="0613b-124">**인증서 마법사** 페이지에서 **요청**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="0613b-125">**인증서 요청** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="0613b-p107">**지연 또는 즉시 요청** 페이지에서 **다음**을 클릭하여 기본 옵션인 **요청을 온라인 인증 기관으로 즉시 보냅니다**를 적용할 수 있습니다. 이 옵션을 선택한 경우 자동 온라인 등록을 지원하는 내부 CA를 사용할 수 있어야 합니다. 요청을 지연하는 옵션을 선택하면 인증서 요청 파일을 저장할 위치 및 파일 이름을 묻는 메시지가 나타납니다. 인증서 요청은 조직 내부의 CA 또는 공용 CA에서 제공하고 처리해야 합니다. 이 작업이 완료되면 인증서 응답을 가져와 적절한 인증서 역할에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="0613b-131">**Ca (인증 기관) 선택** 페이지에서 해당 **환경의 검색 된 목록에서 ca 선택** 옵션을 선택한 다음 목록에서 알려진 (Active Directory 도메인 서비스에서 등록을 통해) ca를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="0613b-132">또는 **다른 인증 기관 지정** 옵션을 선택하고 상자에 다른 CA 이름을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="0613b-p109">**인증 기관 계정** 페이지에서 CA에 요청하고 인증서 요청을 처리하기 위해 자격 증명을 요구하는 메시지가 표시됩니다. 인증서를 요청하기 위해 사용자 이름 및 암호가 필요한지 사전에 확인해야 합니다. CA 관리자가 필요한 정보를 가지고 있어 이 단계에서 도움을 받아야 할 수 있습니다. 대체 자격 증명을 제공해야 하는 경우 확인란을 선택하고 텍스트 상자에 사용자 이름 및 암호를 제공한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="0613b-137">**대체 인증서 템플릿 지정** 페이지에서 기본 웹 서버 템플릿을 사용하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0613b-p110">조직에서 기본 웹 서버 CA 템플릿 대신 사용할 대체 템플릿을 만든 경우 확인란을 선택한 다음 대체 템플릿의 이름을 입력하십시오. CA 관리자가 정의한 템플릿 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="0613b-p111">**이름 및 보안 설정** 페이지에서 인증서 및 용도를 식별하는 데 사용할 **대화명**을 지정합니다. 대화명을 비워 두면 이름이 자동으로 생성됩니다. 키의 **비트 길이**를 설정하거나 기본값 2048비트를 수락합니다. 인증서와 개인 키를 다른 시스템으로 이동하거나 복사하려면 **인증서의 개인 키를 내보낼 수 있는 것으로 표시**를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p111">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose. If you leave it blank, a name will be generated automatically. Set the **Bit length** of the key, or accept the default of 2048 bits. Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0613b-144">Lync Server 2013에는 내보낼 수 있는 개인 키에 대 한 최소 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="0613b-145">이러한 위치 중 하나로 미디어 중계 인증 서비스가 풀의 각 인스턴스에 대한 개별 인증서 대신 인증서 복사본을 사용하는 풀의 에지 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="0613b-146">**조직 정보** 페이지에서 선택적으로 조직 정보를 제공하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="0613b-147">**지역 정보** 페이지에서 선택적으로 지역 정보를 제공하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="0613b-148">**주체 이름/주체 대체 이름** 페이지에서 추가할 주체 대체 이름을 검토한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="0613b-149">**SIP 도메인 설정** 페이지에서 **SIP 도메인**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="0613b-150">**추가 주체 대체 이름 구성** 페이지에서 이후의 추가 SIP 도메인에 필요할 수 있는 것을 포함하여 필요한 추가 주체 대체 이름을 추가하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="0613b-p113">**인증서 요청 요약** 페이지에서 요약 정보를 검토합니다. 정보가 올바르면 **다음**을 클릭합니다. 설정을 수정해야 하는 경우 **뒤로**를 클릭하여 해당 페이지로 이동한 후 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="0613b-154">**명령 실행** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="0613b-155">**온라인 인증서 요청 상태** 페이지에서 반환된 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="0613b-156">인증서가 발급되고 로컬 인증서 저장소에 설치되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="0613b-157">발급 및 설치 되었지만 유효 하지 않은 것으로 보고 되 면 서버에서 신뢰할 수 있는 루트 CA 저장소에 CA 루트 인증서가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="0613b-158">신뢰할 수 있는 루트 CA 인증서를 검색하는 방법은 CA 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0613b-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="0613b-159">검색된 인증서를 확인하려면 **인증서 정보 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="0613b-160">기본적으로 **Lync Server 인증서 사용에 이 인증서 할당** 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="0613b-161">인증서를 수동으로 할당하려면 확인란의 선택을 취소하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="0613b-p115">이전 페이지에서 **Lync Server 인증서 사용에 이 인증서 할당** 확인란의 선택을 취소한 경우 **인증서 할당** 페이지가 나타납니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p115">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page. Click **Next**.</span></span>

18. <span data-ttu-id="0613b-p116">**인증서 저장소** 페이지에서 요청한 인증서를 선택합니다. 인증서를 보려면 **인증서 정보 보기**, **다음**을 차례로 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0613b-p117"><STRONG>온라인 인증서 요청 상태</STRONG> 페이지에 인증서에 대한 문제(예: 유효하지 않은 인증서)가 보고된 경우 실제 인증서를 보면 문제를 해결하는 데 도움이 될 수 있습니다. 인증서 유효성을 일으킬 수 있는 두 가지 특정 문제는 앞서 설명한 신뢰할 수 있는 루트 CA 인증서의 누락과 인증서와 연결된 개인 키의 누락입니다. 이 두 문제를 해결하는 방법은 CA 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0613b-p117">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue. Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate. Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="0613b-169">**인증서 할당 요약** 페이지에서 제공 되는 정보를 검토 하 여이 인증서가 할당 되어야 하는 것으로 확인 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="0613b-p118">**명령 실행** 페이지에서 명령 출력을 검토합니다. 할당 프로세스를 검토하려는 경우 또는 오류나 경고가 발생한 경우 **로그 보기**를 클릭합니다. 검토를 마치면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="0613b-173">**인증서 마법사** 페이지에서 인증서의 **상태**가 "할당됨"인지 확인한 후 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0613b-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0613b-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0613b-174">See Also</span></span>


[<span data-ttu-id="0613b-175">Lync Server 2013의 인증서 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0613b-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

