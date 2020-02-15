---
title: 'Lync Server 2013: 단일 내부 풀에 대 한 웹 게시 규칙 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d87e0096ee71fb08da396188d419e918f66e125
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="9a2e1-102">Lync Server 2013의 단일 내부 풀에 대 한 웹 게시 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="9a2e1-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a2e1-103">_**마지막으로 수정 된 항목:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="9a2e1-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="9a2e1-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server 응용 프로그램 요청 라우팅 (IIS ARR)은 웹 게시 규칙을 사용 하 여 모임 URL 등의 내부 리소스를 인터넷의 사용자에 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="9a2e1-105">가상 디렉터리에 대 한 웹 서비스 Url 외에도 단순 Url, LyncDiscover URL 및 Office Web Apps 서버에 대 한 게시 규칙도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="9a2e1-106">각 단순 URL에 대해 해당 단순 URL을 가리키는 역방향 프록시에 대한 개별 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="9a2e1-107">모바일 기능을 배포하며 자동 검색을 사용하는 경우에는 외부 자동 검색 서비스 URL에 대해 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="9a2e1-108">또한 자동 검색을 사용 하려면 디렉터 풀 및 프런트 엔드 풀에 대 한 외부 Lync Server 웹 서비스 URL에 대 한 게시 규칙도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="9a2e1-109">자동 검색을 위한 웹 게시 규칙을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성을](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="9a2e1-110">웹 게시 규칙을 만들려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a2e1-111">이러한 절차에서는 Forefront Threat Management Gateway (TMG) 2010의 Standard Edition을 설치 했거나 IIS ARR (응용 프로그램 요청 라우팅) 확장을 사용 하 여 인터넷 정보 서버를 설치 및 구성 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="9a2e1-112">TMG 또는 IIS ARR 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="9a2e1-113">TMG 2010을 실행 중인 컴퓨터에 웹 서버 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9a2e1-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="9a2e1-114">**시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 선택한 다음 **Forefront TMG 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="9a2e1-115">왼쪽 창에서 **ServerName**을 확장하고 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 선택한 다음 **웹 사이트 게시 규칙**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="9a2e1-116">**새 웹 게시 규칙 시작** 페이지에서 게시 규칙의 표시 이름(예: LyncServerWebDownloadsRule)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="9a2e1-117">**규칙 동작 선택** 페이지에서 **허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="9a2e1-118">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="9a2e1-119">**서버 연결 보안** 페이지에서 **SSL을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="9a2e1-120">**내부 게시 정보** 페이지에서 **내부 사이트 이름** 상자에 모임 콘텐츠와 주소록 콘텐츠를 호스팅하는 내부 웹 팜의 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a2e1-121">내부 서버가 Standard Edition 서버이면 이 FQDN은 Standard Edition 서버 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="9a2e1-122">내부 서버가 프런트 엔드 풀이면 이 FQDN은 내부 웹 팜 서버의 부하를 분산하는 하드웨어 부하 분산 장치 VIP(가상 IP)입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="9a2e1-123">TMG 서버는 FQDN을 내부 웹 서버의 IP 주소로 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="9a2e1-124">TMG 서버가 FQDN을 적절 한 IP 주소로 확인할 수 없는 경우에는 <STRONG>컴퓨터 이름 또는 ip 주소를 사용 하 여 게시 된 서버에 연결한</STRONG>다음 <STRONG>컴퓨터 이름 또는</STRONG> <STRONG>ip 주소</STRONG> 상자에 내부 웹 서버의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="9a2e1-125">이렇게 하려면 TMG 서버에서 포트 53이 열려 있어 경계 네트워크에 있는 DNS 서버에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="9a2e1-126">로컬 호스트 파일의 항목을 사용하여 이름을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="9a2e1-127">**내부 게시 정보** 페이지의 **경로 (옵션)** 상자에 게시할 폴더의 경로를 \*\* / \*\* 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a2e1-p105">웹 사이트 게시 마법사에서는 하나의 경로만 지정할 수 있습니다. 추가 경로는 규칙의 속성을 수정하여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="9a2e1-130">**공개 이름 정보** 페이지에서 **다음에 대한 요청 허용** 아래에 **이 도메인 이름**이 선택되었는지 확인하고 **공개 이름** 상자에 외부 웹 서비스 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="9a2e1-131">**웹 수신기 선택** 페이지에서 **새로 만들기**를 클릭하여 새 웹 수신기 정의 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="9a2e1-132">**새 웹 수신기 마법사 시작** 페이지에서 **웹 수신기 이름** 상자에 웹 수신기의 이름(예: LyncServerWebServers)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="9a2e1-133">**클라이언트 연결 보안** 페이지에서 **클라이언트와의 SSL 보안 연결 필요**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="9a2e1-134">**웹 수신기 IP 주소** 페이지에서 **외부**를 선택한 다음 **IP 주소 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="9a2e1-135">**외부 수신기 IP 선택** 페이지에서 **선택한 네트워크에 있는 Forefront TMG 컴퓨터의 지정한 IP 주소**를 선택하고 해당하는 IP 주소를 선택한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="9a2e1-136">**수신기 SSL 인증서** 페이지에서 **각 IP 주소에 인증서 할당**을 선택하고 외부 웹 FQDN과 연결되어 있는 IP 주소를 선택한 다음 **인증서 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="9a2e1-137">**인증서 선택** 페이지에서 9단계에서 지정한 공용 이름과 일치하는 인증서를 선택하고 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="9a2e1-138">**인증 설정** 페이지에서 **인증 없음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="9a2e1-139">**Single Sign On 설정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="9a2e1-140">**웹 수신기 마법사 완료** 페이지에서 **웹 수신기** 설정이 올바른지 확인한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="9a2e1-141">**인증 위임** 페이지에서 **위임 안 함 - 클라이언트에서 직접 인증**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="9a2e1-142">**사용자 집합** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="9a2e1-143">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="9a2e1-144">세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="9a2e1-145">IIS ARR을 실행 하는 컴퓨터에서 웹 서버 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9a2e1-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="9a2e1-146">역방향 프록시에 사용할 인증서를 HTTPS 프로토콜로 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="9a2e1-147">**시작**을 클릭 하 고 **프로그램**, **관리 도구**를 차례로 선택한 다음 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a2e1-148">Iis ARR 배포 및 구성에 대 한 추가 도움말, 화면 샷 및 지침은 <A href="http://go.microsoft.com/fwlink/?linkid=293391">Lync Server 2013에 대 한 역방향 프록시로 IIS arr을 사용 하</A>는 다음 홉 문서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="9a2e1-149">아직 수행 하지 않은 경우 역방향 프록시에 사용할 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="9a2e1-150">**IIS (인터넷 정보 서비스) 관리자**에서 콘솔 왼쪽 크기의 역방향 프록시 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="9a2e1-151">콘솔의 중앙에서 **서버 인증서**를 **찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="9a2e1-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="9a2e1-152">**서버 인증서** 를 마우스 오른쪽 단추로 클릭 하 고 **기능 열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="9a2e1-153">콘솔 오른쪽에서 **가져오기 ...** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="9a2e1-154">내선 번호를 사용 하 여 인증서의 경로 및 파일 이름을 입력 하거나 **...** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="9a2e1-155">를 클릭 하 여 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-155">to browse for the certificate.</span></span> <span data-ttu-id="9a2e1-156">인증서를 선택 하 고 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="9a2e1-157">개인 키를 보호 하는 데 사용 되는 암호를 입력 합니다 (인증서와 개인 키를 내보낼 때 암호를 할당 한 경우).</span><span class="sxs-lookup"><span data-stu-id="9a2e1-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="9a2e1-158">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-158">Click **OK**.</span></span> <span data-ttu-id="9a2e1-159">인증서 가져오기가 성공적으로 완료 되 면 인증서가 **서버 인증서**의 항목으로 콘솔의 중앙에 항목으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="9a2e1-160">HTTPS에서 사용할 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="9a2e1-161">콘솔의 왼쪽에서 IIS 서버의 **기본 웹 사이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="9a2e1-162">오른쪽에서 **바인딩을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="9a2e1-163">**사이트 바인딩** 대화 상자에서 **추가 ...** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="9a2e1-164">**사이트 바인딩 추가** 대화 상자의 **유형:** 에서 **https**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="9a2e1-165">Https를 선택 하면 https에 사용할 인증서를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="9a2e1-166">**SSL 인증서:** 에서 역방향 프록시로 가져온 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="9a2e1-167">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-167">Click **OK**.</span></span> <span data-ttu-id="9a2e1-168">그런 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-168">Then, click **Close**.</span></span> <span data-ttu-id="9a2e1-169">이제 인증서가 SSL (secure sockets layer) 및 TLS (전송 계층 보안)에 대 한 역방향 프록시에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9a2e1-170">중간 인증서가 누락 되었다는 바인딩 대화 상자를 닫을 때 경고 메시지가 표시 되 면 공용 CA 루트 인증 기관 인증서 및 모든 중간 CA 인증서를 찾아서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="9a2e1-171">인증서를 요청한 공용 CA의 지침을 참조 하 고 지침에 따라 인증서 체인을 요청 하 고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="9a2e1-172">에 지 서버에서 인증서를 내보낸 경우에는에 지 서버와 연결 된 루트 CA 인증서 및 모든 중간 CA 인증서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="9a2e1-173">루트 CA 인증서를 컴퓨터의 (사용자 저장소와 혼동 하지 않음)에 게 컴퓨터의 중개 인증 기관 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="9a2e1-174">콘솔의 왼쪽에 있는 IIS 서버 이름 아래에서 **서버 팜을** 마우스 오른쪽 단추로 클릭 하 고 **서버 팜 만들기**...를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a2e1-175"><STRONG>서버 팜</STRONG> 노드가 표시 되지 않으면 응용 프로그램 요청 라우팅을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="9a2e1-176">자세한 내용은 up a <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">reverse proxy servers For Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="9a2e1-177">**서버 팜 이름의** **서버 팜 만들기** 대화 상자에서 첫 번째 URL에 대 한 이름 (id를 식별 하기 위한 친근 한 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="9a2e1-178">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-178">Click **Next**.</span></span>

6.  <span data-ttu-id="9a2e1-179">서버 **주소**에 **서버 추가** 대화 상자에서 프런트 엔드 서버에 있는 외부 웹 서비스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="9a2e1-180">예를 들어 여기에 사용 되는 이름은 [Lync Server 2013의 역방향 프록시, 인증서 요약-역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)계획 섹션에서 사용 되는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="9a2e1-181">역방향 프록시 계획을 참조 하 여 FQDN `webext.contoso.com`을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="9a2e1-182">**온라인** 옆의 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="9a2e1-183">**추가** 를 클릭 하 여이 구성에 대 한 웹 서버 풀에 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9a2e1-184">Lync Server에서는 하드웨어 부하 분산 장치를 사용 하 여 HTTP 및 HTTPS 트래픽에 대 한 디렉터 및 프런트 엔드 서버를 풀링 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="9a2e1-185">IIS ARR 서버 팜에 서버를 추가할 때 FQDN을 하나만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="9a2e1-186">FQDN은 풀링되지 않은 서버 구성의 프런트 엔드 서버 또는 디렉터 또는 서버 풀에 대해 구성 된 하드웨어 부하 분산 장치의 FQDN이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="9a2e1-187">HTTP 및 HTTPS 트래픽의 부하를 분산 하는 데 지원 되는 유일한 방법은 하드웨어 부하 분산 장치를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="9a2e1-188">**서버 추가** 대화 상자에서 **고급 설정**...을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="9a2e1-189">이렇게 하면 구성 된 FQDN에 대 한 요청에 대 한 응용 프로그램 요청 라우팅을 정의 하는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="9a2e1-190">IIS ARR에서 요청을 처리 하는 데 사용 되는 포트를 다시 정의 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="9a2e1-191">기본적으로 대상 HTTP 포트는 8080로 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="9a2e1-192">현재 **Httpport 80** 옆의을 클릭 하 고 값을 **8080**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="9a2e1-193">현재 **Httpsport 443** 옆의을 클릭 하 고 값을 **4443**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="9a2e1-194">**가중치** 매개 변수는 100에 남겨 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="9a2e1-195">필요한 경우 기준 통계가 있으면 주어진 규칙의 가중치를 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="9a2e1-196">**마침** 을 클릭 하 여 규칙 구성의 해당 부분을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="9a2e1-197">IIS 관리자가 들어오는 모든 요청을 서버 팜으로 자동으로 라우팅하는 URL 재작성 규칙을 만들 수 있다는 것을 알리는 대화 재작성 규칙을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="9a2e1-198">**예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-198">Click **Yes**.</span></span> <span data-ttu-id="9a2e1-199">규칙을 수동으로 조정 하지만 예를 선택 하면 초기 구성이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="9a2e1-200">방금 만든 서버 팜의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="9a2e1-201">IIS 관리자 기능 보기의 **서버 팜에서** **캐싱을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="9a2e1-202">**디스크 캐시 사용**을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="9a2e1-203">오른쪽에 있는 **적용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="9a2e1-204">서버 팜의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-204">Click the name of the server farm.</span></span> <span data-ttu-id="9a2e1-205">IIS 관리자 기능 보기의 **서버 팜에서** **프록시**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="9a2e1-206">프록시 설정 페이지에서 **시간 제한 (초)** 값을 배포에 적합 한 값으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="9a2e1-207">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9a2e1-208">프록시 제한 시간 값은 배포에 따라 달라 지는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="9a2e1-209">배포를 모니터링 하 고 클라이언트의 모범 환경에 맞게 값을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="9a2e1-210">200 보다 낮은 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="9a2e1-211">사용자 환경에서 Lync 모바일 클라이언트를 지 원하는 경우 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하려면 값을 960로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="9a2e1-212">값이 너무 낮을 때 클라이언트 연결이 끊어지지 않도록 하려면 시간 제한 값을 늘려야 하며, 그렇지 않으면 클라이언트 연결이 끊어진 후에 프록시를 통한 연결이 끊어지지 않는 경우에는 시간이 더 줄어들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="9a2e1-213">이 값에 대 한 적절 한 설정의 위치를 결정 하는 유일한 방법은 사용자 환경에서 정상에 해당 하는 모니터링 및 기본 맞춤 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="9a2e1-214">서버 팜의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-214">Click the name of the server farm.</span></span> <span data-ttu-id="9a2e1-215">IIS 관리자 기능 보기의 **서버 팜에서** **라우팅 규칙**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="9a2e1-216">라우팅 아래의 라우팅 규칙 대화 상자에서 SSL 오프 로딩 사용 옆에 있는 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="9a2e1-217">확인란의 선택을 취소 하는 기능을 사용할 수 없는 경우 **URL 재작성 사용**의 확인란을 선택 하 여 들어오는 요청을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="9a2e1-218">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9a2e1-219">역방향 프록시에의 한 SSL 오프 로딩은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="9a2e1-220">역방향 프록시를 통과 해야 하는 각 URL에 대해 5-11 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="9a2e1-221">일반적인 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="9a2e1-222">프런트 엔드 서버 웹 서비스 외부: webext.contoso.com (이미 초기 워크를 통해 구성 됨)</span><span class="sxs-lookup"><span data-stu-id="9a2e1-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="9a2e1-223">디렉터 웹 서비스 외부: webdirext.contoso.com (디렉터를 배포 하는 경우 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a2e1-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="9a2e1-224">단순 URL 충족: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a2e1-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="9a2e1-225">단순 URL 전화 걸기: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a2e1-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="9a2e1-226">Lync 자동 검색 URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a2e1-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="9a2e1-227">Office Web Apps 서버 URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a2e1-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="9a2e1-228">Office Web Apps 서버에 대 한 URL이 다른 httpsPort 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="9a2e1-229">7 단계에서는 <STRONG>Httpsport</STRONG> 를 <STRONG>443</STRONG> 로 정의 하 고 <STRONG>httpsport</STRONG> 를 port <STRONG>80</STRONG>으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="9a2e1-230">다른 모든 구성 설정은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="9a2e1-231">콘솔의 왼쪽에서 IIS 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="9a2e1-232">콘솔의 가운데에서 **IIS**아래에 있는 **URL 재작성** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="9a2e1-233">URL 다시 쓰기 규칙 구성을 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="9a2e1-234">이전 단계에서 만든 각 서버 팜에 대 한 규칙이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="9a2e1-235">그렇지 않으면 인터넷 정보 서버 관리자 콘솔의 **시작 페이지** 노드 바로 아래에서 **IIS 서버** 이름을 클릭 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="9a2e1-236">**URL 재작성** 대화 상자에서 webext.contoso.com를 예로 사용 하 여 표시 되는 규칙의 전체 이름은 **ARR\_\_webext.contoso.com loadbalance\_SSL**입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="9a2e1-237">규칙을 두 번 클릭 하 여 **인바운드 규칙 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="9a2e1-238">**추가 ...** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-238">Click **Add…**</span></span> <span data-ttu-id="9a2e1-239">**조건** 대화 상자에서</span><span class="sxs-lookup"><span data-stu-id="9a2e1-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="9a2e1-240">조건 **추가** 에서 **입력:** 유형의 **{\_HTTP HOST}** 에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="9a2e1-241">입력 하는 동안 조건을 선택할 수 있는 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="9a2e1-242">**입력 문자열:** 선택에서 **패턴과 일치 하는**경우 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="9a2e1-243">**패턴 입력** 형식 **\***</span><span class="sxs-lookup"><span data-stu-id="9a2e1-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="9a2e1-244">**대/소문자 무시** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="9a2e1-245">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="9a2e1-246">**인바운드 규칙 편집** 대화 상자에서 아래로 스크롤하여 **작업** 대화 상자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="9a2e1-247">**작업 유형:** 이 규칙이 적용 되는 URL로 설정 된 **서버 팜의 경로**( **구성표:** **https://**, **Server farm:** set)로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="9a2e1-248">이 예에서는 **webext.contoso.com**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="9a2e1-249">**경로:** : **0** 으로 설정 됨</span><span class="sxs-lookup"><span data-stu-id="9a2e1-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="9a2e1-250">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="9a2e1-251">**규칙으로 돌아가기** 를 클릭 하 여 URL 다시 쓰기 규칙으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="9a2e1-252">정의한 각 SSL 재작성 규칙 (서버 팜 URL 마다 하나씩)에 대해 14 단계에서 정의한 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9a2e1-253">기본적으로 HTTP 규칙도 만들어지고 마찬가지로 SSL 규칙과 비슷한 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="9a2e1-254">현재 예에서 HTTP 규칙의 이름은 <STRONG>ARR_webext. com_loadbalance</STRONG>입니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="9a2e1-255">이러한 규칙에 대 한 수정이 필요 하지 않으며 무시 해도 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="9a2e1-256">TMG 2010에서 웹 게시 규칙의 속성을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="9a2e1-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="9a2e1-257">**시작**을 클릭 하 고 **프로그램**을 가리킨 다음 **Microsoft Forefront TMG**를 선택한 다음 **Forefront TMG Management**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="9a2e1-258">왼쪽 창에서 **ServerName**을 확장한 다음 **방화벽 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="9a2e1-259">세부 정보 창에서 이전 절차에서 만든 웹 서버 게시 규칙(예: LyncServerExternalRule)을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="9a2e1-260">**속성** 페이지의 **시작** 탭에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="9a2e1-261">**이 규칙은 다음 원본에서 생성된 트래픽에 적용됩니다** 목록에서 **원하는 위치**를 클릭한 다음 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="9a2e1-262">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="9a2e1-263">**네트워크 엔터티 추가**에서 **네트워크**를 확장하고 **외부**, **추가**를 차례로 클릭한 다음 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="9a2e1-264">**종료** 탭에서 **실제 호스트 헤더 대신 원래 호스트 헤더 전달** 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="9a2e1-265">**브리징** 탭에서 **SSL 포트로 요청 리디렉션** 확인란을 선택한 다음 포트 **4443**을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="9a2e1-266">**공개 이름** 탭에서 단순 URL(예: meet.contoso.com 및 dialin.contoso.com)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="9a2e1-267">**적용**을 클릭하여 변경 내용을 저장한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="9a2e1-268">세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="9a2e1-269">IIS ARR에서 웹 게시 규칙의 속성을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="9a2e1-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="9a2e1-270">**시작**을 클릭 하 고 **프로그램**, **관리 도구**를 차례로 선택한 다음 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="9a2e1-271">콘솔의 왼쪽에서 IIS 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="9a2e1-272">콘솔의 가운데에서 **IIS**아래에 있는 **URL 재작성** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="9a2e1-273">URL 다시 쓰기 규칙 구성을 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="9a2e1-274">수정 해야 하는 규칙을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="9a2e1-275">**일치 URL**, **조건**, **서버 변수** 또는 **작업**에서 필요에 따라 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="9a2e1-276">**적용** 을 클릭 하 여 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="9a2e1-277">**규칙으로 돌아가기** 를 클릭 하 여 다른 규칙을 수정 하거나, 변경 작업이 완료 되 면 **IIS 관리자** 콘솔을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9a2e1-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

