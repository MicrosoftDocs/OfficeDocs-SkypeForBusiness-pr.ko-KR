---
title: 'Lync Server 2013: 단일 내부 풀에 대한 웹 게시 규칙 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="612a9-102">Lync Server 2013에서 단일 내부 풀에 대한 웹 게시 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="612a9-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="612a9-103">_**마지막으로 수정한 주제:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="612a9-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="612a9-104">Microsoft Forefront 위협 관리 게이트웨이 2010 및 인터넷 정보 서버 응용 프로그램 요청 라우팅 (IIS ARR)은 웹 게시 규칙을 사용 하 여 인터넷의 사용자에 게 모임 URL 등의 내부 리소스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="612a9-105">가상 디렉터리의 웹 서비스 Url 외에도 간단한 Url, LyncDiscover URL 및 Office Web Apps 서버에 대 한 게시 규칙도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="612a9-106">각 간단한 URL에 대해 해당 간단한 URL을 가리키는 리버스 프록시에서 개별 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="612a9-107">이동성을 배포 하 고 자동 검색을 사용 하는 경우 외부 자동 검색 서비스 URL에 대 한 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="612a9-108">자동 검색에는 사용자의 디렉터 풀 및 프런트 엔드 풀에 대 한 외부 Lync Server 웹 서비스 URL에 대 한 게시 규칙도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="612a9-109">자동 검색을 위한 웹 게시 규칙을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 이동성에 대 한 리버스 프록시 구성을](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612a9-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="612a9-110">다음 절차를 사용 하 여 웹 게시 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="612a9-111">이 절차에서는 TMG (Forefront Threat Management Gateway) 2010의 표준 버전을 설치 했거나 IIS ARR (응용 프로그램 요청 라우팅) 확장을 사용 하 여 인터넷 정보 서버를 설치 하 고 구성한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="612a9-112">TMG 또는 IIS ARR 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="612a9-113">TMG 2010를 실행 하는 컴퓨터에서 웹 서버 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="612a9-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="612a9-114">**시작**을 클릭 하 고 **프로그램**을 선택한 다음 **Microsoft forefront TMG**를 선택 하 고 **Forefront TMG Management**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="612a9-115">왼쪽 창에서 **ServerName**을 확장 하 고 **방화벽 정책을**마우스 오른쪽 단추로 클릭 한 다음 **새로 만들기**를 선택 하 고 **웹 사이트 게시 규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="612a9-116">**새 웹 게시 규칙 시작** 페이지에서 게시 규칙에 대 한 표시 이름을 입력 합니다 (예: L Cserverwebdownloadsrule).</span><span class="sxs-lookup"><span data-stu-id="612a9-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="612a9-117">**규칙 동작 선택** 페이지에서 **허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="612a9-118">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="612a9-119">**서버 연결 보안** 페이지에서 **SSL을 사용 하 여 게시 된 웹 서버 또는 서버 팜에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="612a9-120">**내부 게시 세부 정보** 페이지에서 모임 콘텐츠를 호스트 하는 내부 웹 팜의 FQDN (정규화 된 도메인 이름)과 **내부 사이트 이름** 상자에 주소록 콘텐츠를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="612a9-121">내부 서버가 Standard Edition 서버인 경우이 FQDN은 Standard Edition 서버 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="612a9-122">내부 서버가 프런트 엔드 풀 인 경우이 FQDN은 내부 웹 팜 서버의 부하를 분산 하는 하드웨어 부하 분산 장치 VIP (가상 IP)입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="612a9-123">TMG 서버는 내부 웹 서버의 IP 주소에 대 한 FQDN을 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="612a9-124">TMG 서버에서 FQDN을 적절 한 IP 주소로 확인할 수 없는 경우 <STRONG>컴퓨터 이름 또는 ip 주소 사용을 선택 하 여 게시 된 서버에 연결한</STRONG>다음 <STRONG>컴퓨터 이름 또는</STRONG> <STRONG>ip 주소</STRONG> 상자에 내부 웹 서버의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="612a9-125">이 작업을 수행 하는 경우 TMG 서버에서 포트 53이 열려 있고 경계 네트워크에 있는 DNS 서버에 도달할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="612a9-126">로컬 hosts 파일의 항목을 사용 하 여 이름 확인을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="612a9-127">**내부 게시 세부 정보** 페이지의 **경로 (선택 사항)** 상자에 게시할 폴더의 \*\* / \*\* 경로로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="612a9-128">웹 사이트 게시 마법사에서 하나의 경로만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="612a9-129">규칙의 속성을 수정 하 여 추가 경로를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="612a9-130">**공개 이름 정보** 페이지의 **요청 수락에** **이 도메인 이름이** 선택 되어 있는지 확인 하 고 **공용 이름** 상자에 외부 웹 서비스 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="612a9-131">**웹 수신기 선택** 페이지에서 **새로 만들기** 를 클릭 하 여 새 웹 수신기 정의 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="612a9-132">**새 웹 수신기 마법사 시작** 페이지에서 **웹 수신기 이름** 상자에 웹 수신기의 이름을 입력 합니다 (예: L cserverwebserver).</span><span class="sxs-lookup"><span data-stu-id="612a9-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="612a9-133">**클라이언트 연결 보안** 페이지에서 **클라이언트와 SSL 보안 연결 필요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="612a9-134">**웹 수신기 IP 주소** 페이지에서 **외부**를 선택 하 고 **IP 주소 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="612a9-135">**외부 수신기 IP 선택** 페이지에서 **선택한 네트워크의 Forefront TMG Computer에서 지정 된 ip 주소**를 선택 하 고 적절 한 ip 주소를 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="612a9-136">**수신기 SSL 인증서** 페이지에서 **각 IP 주소에 대해 인증서 할당**을 선택 하 고, 외부 웹 FQDN과 연결 된 ip 주소를 선택한 다음 **인증서 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="612a9-137">**인증서 선택** 페이지에서 9 단계에서 지정한 공개 이름과 일치 하는 인증서를 선택 하 고 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="612a9-138">**인증 설정** 페이지에서 **인증 안**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="612a9-139">**단일 사인온 설정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="612a9-140">**웹 수신기 마법사 완료** 페이지에서 **웹 수신기** 설정이 올바른지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="612a9-141">**인증 위임** 페이지에서 **위임 안을 선택 하지만 클라이언트가 직접 인증할 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="612a9-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="612a9-142">**사용자 설정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="612a9-143">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="612a9-144">세부 정보 창에서 **적용** 을 클릭 하 여 변경 내용을 저장 하 고 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="612a9-145">IIS ARR을 실행 하는 컴퓨터에서 웹 서버 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="612a9-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="612a9-146">역방향 프록시에 사용할 인증서를 HTTPS 프로토콜에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="612a9-147">**시작**을 클릭 하 고 **프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **인터넷 정보 서비스 (IIS) 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="612a9-148">IIS ARR 배포 및 구성에 대 한 추가 도움말, 화면 샷 및 지침은 <A href="http://go.microsoft.com/fwlink/?linkid=293391">Lync Server 2013의 역방향 프록시로 IIS arr을 사용 하 여</A>NextHop 아티클에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="612a9-149">아직 수행 하지 않은 경우에는 리버스 프록시에 사용할 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="612a9-150">**IIS (인터넷 정보 서비스) 관리자**에서 콘솔의 왼쪽 크기에서 역방향 프록시 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="612a9-151">콘솔의 가운데에서 **서버 인증서**를 **찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="612a9-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="612a9-152">**서버 인증서** 를 마우스 오른쪽 단추로 클릭 하 고 **기능 열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="612a9-153">콘솔의 오른쪽에 있는 **가져오기**...를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="612a9-154">확장명과 함께 인증서의 경로와 파일 이름을 입력 하거나 ...를 클릭 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="612a9-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="612a9-155">를 눌러 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-155">to browse for the certificate.</span></span> <span data-ttu-id="612a9-156">인증서를 선택 하 고 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="612a9-157">개인 키를 보호 하는 데 사용 되는 암호를 제공 합니다 (인증서와 개인 키를 내보낼 때 암호를 지정한 경우).</span><span class="sxs-lookup"><span data-stu-id="612a9-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="612a9-158">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-158">Click **OK**.</span></span> <span data-ttu-id="612a9-159">인증서 가져오기에 성공 하면 인증서가 콘솔의 중앙에 **서버 인증서**의 항목으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="612a9-160">HTTPS에서 사용할 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="612a9-161">콘솔의 왼쪽에서 IIS 서버의 **기본 웹 사이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="612a9-162">오른쪽에서 **바인딩을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="612a9-163">**사이트 바인딩** 대화 상자에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="612a9-164">**사이트 바인딩 추가** 대화 상자의 **종류**아래에서 **https**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="612a9-165">Https를 선택 하면 https에 사용할 인증서를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="612a9-166">**SSL 인증서:** 에서 역방향 프록시에 대해 가져온 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="612a9-167">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-167">Click **OK**.</span></span> <span data-ttu-id="612a9-168">그런 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-168">Then, click **Close**.</span></span> <span data-ttu-id="612a9-169">이제 인증서가 SSL (secure socket layer) 및 TLS (전송 계층 보안)에 대 한 역방향 프록시에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="612a9-170">중간 인증서가 누락 된 바인딩 대화 상자를 닫을 때 경고 메시지가 표시 되는 경우 공용 CA 루트 인증 기관 인증서와 중간 CA 인증서를 찾아 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="612a9-171">인증서를 요청한 공개 CA의 지침을 참조 하 고 지침을 따라 인증서 체인을 요청 하 고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="612a9-172">Edge 서버에서 인증서를 내보낸 경우에는 Edge 서버와 연결 된 루트 CA 인증서와 중간 CA 인증서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="612a9-173">루트 CA 인증서를 컴퓨터의 (사용자 저장소와 혼동 하지 않음) 신뢰할 수 있는 루트 인증 기관 저장소와 중개 인증서를 컴퓨터의 중개 인증 기관 저장소에 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="612a9-174">콘솔의 왼쪽에서 IIS 서버 이름 아래에 있는 **서버 팜을** 마우스 오른쪽 단추로 클릭 하 고 **서버 팜 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="612a9-175"><STRONG>서버 팜</STRONG> 노드가 표시 되지 않으면 응용 프로그램 요청 라우팅을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="612a9-176">자세한 내용은 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013에 대 한 리버스 프록시 서버 설정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612a9-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="612a9-177">**서버 팜 이름의** **서버 팜 만들기** 대화 상자에서 첫 번째 URL에 대 한 이름 (식별에 대 한 알기 쉬운 이름을 지정할 수 있음)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="612a9-178">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-178">Click **Next**.</span></span>

6.  <span data-ttu-id="612a9-179">서버 **주소**에 **서버 추가** 대화 상자에서 프런트 엔드 서버에 있는 외부 웹 서비스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="612a9-180">예를 들어 여기에 사용 되는 이름은 [Lync Server 2013의 리버스 프록시, 인증서 요약-역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)에 대 한 계획 섹션에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="612a9-181">역방향 프록시 계획을 참조 하 여 FQDN `webext.contoso.com`을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="612a9-182">**온라인** 옆에 있는 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="612a9-183">**추가** 를 클릭 하 여이 구성에 대 한 웹 서버의 풀에 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="612a9-184">Lync Server는 하드웨어 부하 분산 장치를 사용 하 여 HTTP 및 HTTPS 트래픽에 대 한 디렉터 및 프런트 엔드 서버를 풀링 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="612a9-185">IIS ARR 서버 팜에는 서버를 추가할 때 하나의 FQDN만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="612a9-186">FQDN은 풀링되지 않은 서버 구성의 프런트 엔드 서버 또는 디렉터 또는 서버 풀에 대해 구성 된 하드웨어 부하 분산 장치의 FQDN이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="612a9-187">HTTP 및 HTTPS 트래픽을 로드 하는 데 지원 되는 유일한 방법은 하드웨어 부하 분산 장치를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="612a9-188">**서버 추가** 대화 상자에서 **고급 설정을 클릭 합니다**.</span><span class="sxs-lookup"><span data-stu-id="612a9-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="612a9-189">이렇게 하면 구성 된 FQDN에 대 한 요청에 대 한 응용 프로그램 요청 라우팅을 정의 하는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="612a9-190">이는 IIS ARR에서 요청을 처리 하는 경우 사용 되는 포트를 재정의 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="612a9-191">기본적으로 대상 HTTP 포트는 8080으로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="612a9-192">현재 **Httpport 80** 옆에 있는을 클릭 하 고 값을 **8080**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="612a9-193">현재 **Httpsport 443** 옆에 있는을 클릭 하 고 값을 **4443**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="612a9-194">100에서 **가중치** 매개 변수를 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="612a9-195">필요에 따라 기준 통계를 사용 하는 경우 지정 된 규칙의 가중치를 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="612a9-196">**마침을** 클릭 하 여 규칙 구성의이 부분을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="612a9-197">IIS 관리자가 모든 수신 요청을 서버 팜에 자동으로 라우팅하는 URL 재작성 규칙을 만들 수 있음을 알리는 대화 상자 재작성 규칙이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="612a9-198">**예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-198">Click **Yes**.</span></span> <span data-ttu-id="612a9-199">규칙을 수동으로 조정 하지만 예를 선택 하면 초기 구성이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="612a9-200">방금 만든 서버 팜 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="612a9-201">IIS 관리자 기능 보기의 **서버 팜** 아래에서 **캐싱을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="612a9-202">**디스크 캐시 사용**을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="612a9-203">오른쪽에 **적용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="612a9-204">서버 팜 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-204">Click the name of the server farm.</span></span> <span data-ttu-id="612a9-205">IIS 관리자 기능 보기의 **서버 팜** 아래에서 **Proxy**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="612a9-206">프록시 설정 페이지에서 **시간 제한 (초)** 값을 배포에 적합 한 값으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="612a9-207">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="612a9-208">프록시 시간 초과 값은 배포에 따라 달라 지는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="612a9-209">배포를 모니터링 하 고 클라이언트에 대 한 최상의 환경을 위해 값을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="612a9-210">200 보다 낮은 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="612a9-211">환경에서 Lync 모바일 클라이언트를 지 원하는 경우 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하려면 값을 960로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="612a9-212">값이 너무 낮을 경우 클라이언트 연결이 끊어지지 않도록 시간 초과 값을 늘리고, 프록시를 통한 연결이 연결 해제 되지 않는 경우, 그리고 클라이언트가 연결이 끊어지면 long 키를 해제 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="612a9-213">이 값에 대 한 적절 한 설정의 위치를 결정 하는 유일한 정확한 방법은 사용자 환경의 표준에 맞게 모니터링 및 기준 맞춤을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="612a9-214">서버 팜 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-214">Click the name of the server farm.</span></span> <span data-ttu-id="612a9-215">IIS 관리자 기능 보기의 **서버 팜** 아래에서 **라우팅 규칙**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="612a9-216">라우팅의 라우팅 규칙 대화 상자에서 SSL 오프 로딩 사용 옆에 있는 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="612a9-217">확인란을 지우는 기능을 사용할 수 없는 경우 URL 재작성 사용 확인란을 선택 **하 여 들어오는 요청을 검사**합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="612a9-218">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="612a9-219">리버스 프록시로의 SSL 오프 로드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="612a9-220">역방향 프록시를 통과 해야 하는 각 URL에 대해 5-11 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="612a9-221">일반적인 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="612a9-222">프런트 엔드 서버 웹 서비스 외부: webext.contoso.com (이미 초기 안내를 통해 구성 됨)</span><span class="sxs-lookup"><span data-stu-id="612a9-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="612a9-223">디렉터에 대 한 외부 웹 서비스 감독: webdirext.contoso.com (디렉터를 배포 하는 경우 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="612a9-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="612a9-224">간단한 URL 소개: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="612a9-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="612a9-225">간단한 URL 전화 접속: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="612a9-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="612a9-226">Lync 자동 검색 URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="612a9-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="612a9-227">Office Web Apps 서버 URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="612a9-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="612a9-228">Office Web Apps 서버에 대 한 URL이 다른 httpsPort 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="612a9-229">7 단계에서는 <STRONG>Httpsport</STRONG> 를 <STRONG>443</STRONG> 로 정의 하 고 <STRONG>httpsport</STRONG> 를 port <STRONG>80</STRONG>로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="612a9-230">다른 모든 구성 설정은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="612a9-231">콘솔의 왼쪽에서 IIS 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="612a9-232">콘솔 중간에서 **IIS**아래에 있는 **URL 재작성** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="612a9-233">URL 재작성 규칙 구성을 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="612a9-234">이전 단계에서 만든 각 서버 팜에 대해 규칙이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="612a9-235">그렇지 않으면 인터넷 정보 서버 관리자 콘솔의 **시작 페이지** 바로 아래에서 **IIS 서버** 이름을 클릭 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="612a9-236">**URL 재작성** 대화 상자에서 webext.contoso.com를 예로 사용 하 여 표시 된 규칙의 전체 이름은 **ARR\_\_webext.contoso.com loadbalance\_SSL**입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="612a9-237">규칙을 두 번 클릭 하 여 **인바운드 규칙 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="612a9-238">추가를 클릭 **합니다** .</span><span class="sxs-lookup"><span data-stu-id="612a9-238">Click **Add…**</span></span> <span data-ttu-id="612a9-239">**조건** 대화 상자</span><span class="sxs-lookup"><span data-stu-id="612a9-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="612a9-240">조건 **추가** **조건의 입력:** **\_{HTTP HOST}** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="612a9-241">(입력 하는 동안 조건을 선택할 수 있는 대화 상자가 나타납니다.)</span><span class="sxs-lookup"><span data-stu-id="612a9-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="612a9-242">**입력 문자열:** Select **가 패턴과 일치 하는**경우 확인에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="612a9-243">**패턴 입력** 형식 **\***</span><span class="sxs-lookup"><span data-stu-id="612a9-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="612a9-244">**대/소문자 무시** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="612a9-245">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="612a9-246">**인바운드 규칙 편집** 대화 상자에서 아래로 스크롤하여 **작업** 대화 상자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="612a9-247">**작업 유형:** **서버 팜으로 라우팅하도록**설정 해야 합니다. **스키마:** **https://**, **서버 팜:** 이 규칙이 적용 되는 URL로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="612a9-248">이 예제에서는 **webext.contoso.com**으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="612a9-249">**경로:** **/{r: 0** 으로 설정 됨</span><span class="sxs-lookup"><span data-stu-id="612a9-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="612a9-250">**적용** 을 클릭 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="612a9-251">**규칙으로 돌아가기** 를 클릭 하 여 URL 다시 쓰기 규칙으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="612a9-252">정의한 각 SSL 다시 작성 규칙에 대해 14 단계에서 정의한 절차 인 각 서버 팜 URL을 하나씩 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="612a9-253">기본적으로 HTTP 규칙도 생성 되며 SSL 규칙에 대 한 유사한 이름으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="612a9-254">현재 예제에 대 한 HTTP 규칙의 이름은 <STRONG>ARR_webext. com_loadbalance</STRONG>입니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="612a9-255">이러한 규칙에는 수정이 필요 하지 않으며 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="612a9-256">TMG 2010에서 웹 게시 규칙의 속성을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="612a9-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="612a9-257">**시작**을 클릭 하 고 **프로그램**을 가리킨 다음 **Microsoft forefront TMG**를 선택 하 고 **Forefront TMG Management**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="612a9-258">왼쪽 창에서 **ServerName**을 확장 한 다음 **방화벽 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="612a9-259">세부 정보 창에서 이전 절차에서 만든 웹 서버 게시 규칙을 마우스 오른쪽 단추로 클릭 한 다음 (예: LyncServerExternalRule) **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="612a9-260">**속성** 페이지의 **보낸 사람** 탭에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="612a9-261">**이 규칙은 다음 원본에 있는 트래픽에 적용 됩니다** 목록에서 **아무 곳 이나**클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="612a9-262">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="612a9-263">**네트워크 엔터티 추가**에서 **네트워크**, **외부**를 차례로 클릭 하 고 **추가**를 클릭 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="612a9-264">**받는 사람** 탭에서 **실제 항목 대신 원본 호스트 머리글 전달** 확인란을 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="612a9-265">**브리징** 탭에서 **SSL 포트로 요청 리디렉션** 확인란을 선택한 다음 포트 **4443**를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="612a9-266">**공용 이름** 탭에서 간단한 url (예: meet.contoso.com 및 dialin.contoso.com)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="612a9-267">**적용** 을 클릭 하 여 변경 내용을 저장 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="612a9-268">세부 정보 창에서 **적용** 을 클릭 하 여 변경 내용을 저장 하 고 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="612a9-269">IIS ARR에서 웹 게시 규칙의 속성을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="612a9-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="612a9-270">**시작**을 클릭 하 고 **프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **인터넷 정보 서비스 (IIS) 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="612a9-271">콘솔의 왼쪽에서 IIS 서버 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="612a9-272">콘솔 중간에서 **IIS**아래에 있는 **URL 재작성** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="612a9-273">URL 재작성 규칙 구성을 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="612a9-274">수정 해야 하는 규칙을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="612a9-275">필요에 따라 일치 하는 **URL**, **조건**, **서버 변수** 또는 **작업**에서 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="612a9-276">**적용** 을 클릭 하 여 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="612a9-277">**규칙으로 돌아가기** 를 클릭 하 여 다른 규칙을 수정 하거나 변경 작업을 완료 한 경우 **IIS 관리자** 콘솔을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="612a9-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

