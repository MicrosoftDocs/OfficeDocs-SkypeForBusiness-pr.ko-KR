---
title: 'Lync Server 2013: 자동 검색을 위한 역방향 프록시 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 712dbc4e3bc9acf083f540520968953115ffc699
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="c610b-102">Lync Server 2013에서 자동 검색을 위한 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="c610b-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c610b-103">_**마지막으로 수정 된 항목:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c610b-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c610b-104">자동 검색 및 새 검색을 사용 하는 클라이언트의 지원에는 기존 웹 게시 규칙을 수정 하거나 역방향 프록시에 대 한 새로운 웹 게시 규칙을 만드는 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="c610b-105">새 게시 규칙을 수정 하거나 만드는 것은 역방향 프록시 인증서의 주체 대체 이름 목록을 업데이트 하거나 업데이트 하지 않는 결정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="c610b-106">초기 Lync Server 2013 자동 검색 서비스 요청에 HTTPS를 사용 하 고 역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하는 경우 업데이트 된 공용 인증서를 SSL (Secure Sockets layer) 수신기에 할당 해야 합니다. 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="c610b-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="c610b-107">외부 (공용) 인증서에 대 한 필수 업데이트에는 lyncdiscover에 대 한 SAN (주체 대체 이름) 항목이 포함 됩니다. \<도메인 이름\>입니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="c610b-108">그런 다음 외부 자동 검색 서비스 URL (예: **lyncdiscover.contoso.com**)에 대 한 기존 수신기를 수정 하거나 새 웹 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="c610b-109">프런트 엔드 풀 및 디렉터 풀에 대 한 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 아직 없는 경우 (디렉터를 배포한 경우)에도 규칙을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c610b-110">리스너에 지정된 인증서에 두 서비스 모두에 필요한 주체 이름 및 주체 대체 이름이 포함된 경우 역방향 프록시 게시 규칙 및 리스너가 외부 웹 서비스와 자동 검색 서비스 모두를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="c610b-111">웹 수신기 및 게시 규칙의 기본 구성에 대 한 자세한 내용은 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers For Lync Server 2013</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c610b-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="c610b-112">역방향 프록시용 주체 대체 이름을 업데이트하지 않아도 되도록 초기 자동 검색 서비스 요청에 대해 HTTP를 사용하려는 경우에는 포트 80에 대해 웹 게시 규칙을 만들거나 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="c610b-113">이 섹션의 절차에서는 자동 검색을 위해 Microsoft Forefront Threat Management Gateway 2010에서 웹 게시 규칙을 만들거나 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c610b-p104">이러한 절차에서는 Forefront Threat Management Gateway(TMG) 2010의 Standard Edition이 설치되어 있다고 가정합니다. 또 다른 역방향 프록시를 사용 중인 경우 절차가 비슷하지만 타사 제품에 대한 설명서에 맞게 매핑할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c610b-116">외부 자동 검색 URL에 대해 새 웹 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c610b-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="c610b-117">**시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c610b-118">왼쪽 창에서 **ServerName**을 확장하고 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c610b-119">**새 웹 게시 규칙 시작** 페이지에서 새 게시 규칙의 표시 이름(예: LyncDiscoveryURL)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="c610b-120">**규칙 동작 선택** 페이지에서 **허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c610b-121">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c610b-122">**서버 연결 보안** 페이지에서 **SSL을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c610b-123">**내부 게시 정보** 페이지의 **내부 사이트 이름**에 디렉터 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다 (예: lyncdir01).</span><span class="sxs-lookup"><span data-stu-id="c610b-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="c610b-124">프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 FQDN (예:: lyncpool01.contoso.local)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c610b-125">**내부 게시 정보** 페이지의 **경로 (옵션)** 에 게시할 폴더의 경로 \*\* / \*\* 를 입력 한 다음 **원래 호스트 헤더 전달을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="c610b-126">**공개 이름 정보** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c610b-127">**다음에 대한 요청 허용**에서 **이 도메인 이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c610b-128">**공개 이름**에 **lyncdiscover를 입력 합니다.** \<microsoft.rtc.management.xds.sipdomain object\> (외부 자동 검색 서비스 URL)</span><span class="sxs-lookup"><span data-stu-id="c610b-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="c610b-129">프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN (예: lyncwebextpool01.contoso.com)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="c610b-130">**경로**에를 입력 \*\* / \*\*합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c610b-131">**웹 수신기 선택** 페이지의 **웹 수신기**에서 업데이트된 공용 인증서를 포함하는 기존 SSL 수신기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="c610b-132">**인증 위임** 페이지에서 **위임 안 함 - 클라이언트에서 직접 인증**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="c610b-133">**사용자 집합** 페이지에서 **모든 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c610b-134">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c610b-135">Forefront TMG의 웹 게시 규칙 목록에서 방금 추가한 새 규칙을 두 번 클릭하여 **속성**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c610b-136">**대상** 탭에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="c610b-137">**실제 호스트 헤더 대신 원래 호스트 헤더 전달**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="c610b-138">**Forefront TMG 컴퓨터에서 보낸 요청(Requests appear to come from the Forefront TMG computer)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="c610b-139">**브리징** 탭에서 다음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c610b-140">**웹 서버**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c610b-141">**HTTP 포트로 요청 리디렉션**을 선택하고 포트 번호로 **8080**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c610b-142">**SSL 포트로 요청 리디렉션**을 선택하고 포트 번호로 **4443**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="c610b-143">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-143">Click **OK**.</span></span>

18. <span data-ttu-id="c610b-144">세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="c610b-145">**규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="c610b-146">외부 자동 검색 SAN 및 URL을 추가하기 위해 기존 웹 게시 규칙을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="c610b-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="c610b-147">**시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c610b-148">갖고 있는 각 게시 규칙 및 리스너에 대해 수정 작업을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="c610b-149">일반적으로이 작업은 프런트 엔드 풀에 대 한 하나의 규칙과 수신기와 선택적 디렉터 또는 디렉터 풀에 대해 하나씩 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="c610b-p108">왼쪽 창에서 **ServerName**을 확장하고 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 해당 규칙을 클릭합니다. **작업** 탭에서 **선택한 규칙 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="c610b-152">**공개 이름** 탭의 **이 규칙 적용**에서 **다음 웹 사이트에 대한 요청**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="c610b-153">**추가**를 클릭하고 새로운 자동 검색 사이트의 이름(예: 뱇yncdiscover.contoso.com?을 입력한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="c610b-p109">**리스너** 탭에서 **인증서 선택**을 클릭하고 추가된 자동 검색 SAN 항목을 포함하는 새 인증서를 지정합니다. 리스너 및 웹 게시 속성을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="c610b-156">세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="c610b-157">**규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="c610b-158">포트 80에 대해 웹 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c610b-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="c610b-159">**시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c610b-160">왼쪽 창에서 **ServerName**을 확장하여 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c610b-161">**새 웹 게시 규칙 시작** 페이지에서 게시 규칙의 표시 이름(예: Lync 자동 검색(HTTP))을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="c610b-162">**규칙 동작 선택** 페이지에서 **허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c610b-163">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c610b-164">**서버 연결 보안** 페이지에서 **보안되지 않은 연결을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c610b-165">**내부 게시 정보** 페이지의 **내부 사이트 이름**에 프런트 엔드 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncpool01.contoso.local)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c610b-166">**내부 게시 정보** 페이지의 **경로 (옵션)** 에 게시할 폴더의 경로 \*\* / \*\* 를 입력 하 고 **내부 사이트 이름 필드에 지정 된 호스트 헤더 대신 원래 host 머리글 전달을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="c610b-167">**공개 이름 정보** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c610b-168">**다음에 대한 요청 허용**에서 **이 도메인 이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c610b-169">**공개 이름**에 **lyncdiscover를 입력 합니다.** \<microsoft.rtc.management.xds.sipdomain object\> (외부 자동 검색 서비스 URL)</span><span class="sxs-lookup"><span data-stu-id="c610b-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="c610b-170">**경로**에를 입력 \*\* / \*\*합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c610b-171">**웹 수신기 선택** 페이지의 **웹 수신기**에서 웹 수신기를 선택하거나 새 웹 수신기 정의 마법사를 사용하여 새 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="c610b-172">**인증 위임** 페이지에서 **위임 안 함 - 클라이언트에서 직접 인증할 수 없음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="c610b-173">**사용자 집합** 페이지에서 **모든 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c610b-174">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c610b-175">Forefront TMG의 웹 게시 규칙 목록에서 방금 추가한 새 규칙을 두 번 클릭하여 **속성**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c610b-176">**브리징** 탭에서 다음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c610b-177">**웹 서버**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c610b-178">**HTTP 포트로 요청 리디렉션**을 선택하고 포트 번호로 **8080**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c610b-179">**SSL 포트로 요청 리디렉션**이 선택되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="c610b-180">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-180">Click **OK**.</span></span>

17. <span data-ttu-id="c610b-181">세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="c610b-182">**규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="c610b-183">다른 웹 게시 규칙에 대해 외부 자동 검색 서비스 URL이 정의되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c610b-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c610b-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c610b-184">See Also</span></span>


[<span data-ttu-id="c610b-185">Lync Server 2013에 대 한 역방향 프록시 서버 설정</span><span class="sxs-lookup"><span data-stu-id="c610b-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

