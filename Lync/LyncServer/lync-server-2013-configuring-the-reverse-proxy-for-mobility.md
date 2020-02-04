---
title: 'Lync Server 2013: 모바일 기능에 대해 역방향 프록시 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51fffae60df68a6aa2843919f95d7a00590ddd65
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e4dd0-102">Lync Server 2013에서 모바일 기능에 대해 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="e4dd0-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4dd0-103">_**마지막으로 수정한 주제:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="e4dd0-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="e4dd0-104">모바일 장치 클라이언트에 대 한 자동 검색을 사용 하려는 경우 역방향 프록시 인증서의 주체 대체 이름 목록을 업데이트 하는지 여부에 관계 없이 기존 항목을 수정 하거나 리버스 프록시의 새 웹 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="e4dd0-105">초기 Lync Server 2013 자동 검색 서비스 요청에 HTTPS를 사용 하기로 결정 하 고 역방향 프록시 인증서의 주체 대체 이름 목록을 업데이트 하는 경우 업데이트 된 공개 인증서를 SSL (Secure Sockets layer) 수신기에 할당 해야 합니다. 리버스 프록시</span><span class="sxs-lookup"><span data-stu-id="e4dd0-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="e4dd0-106">필수 주제 대체 이름 항목에 대 한 자세한 내용은 [Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="e4dd0-107">외부 자동 검색 서비스 URL에 대 한 기존 수신기를 수정 하거나 새 웹 게시 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="e4dd0-108">프런트 엔드 풀에 대 한 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 아직 없는 경우 해당 항목에 대 한 규칙도 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4dd0-109">수신기에 할당 된 인증서에는 필요한 주체 이름과 제목 대체 이름이 모두 포함 되어 있는 한, 역방향 프록시 게시 규칙과 수신기는 외부 웹 서비스와 자동 검색 서비스를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="e4dd0-110">웹 수신기 및 게시 규칙의 기본 구성에 대 한 자세한 내용은 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013의 리버스 프록시 서버 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="e4dd0-111">초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하기로 결정 한 경우, 역방향 프록시의 주체의 대체 이름을 업데이트할 필요가 없도록 하려면 포트 80에 대 한 웹 게시 규칙을 만들거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="e4dd0-112">이 섹션의 절차에서는 자동 검색을 위해 Microsoft Forefront Threat Management Gateway 2010에서 웹 게시 규칙을 만들거나 수정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4dd0-113">이 절차에서는 TMG (Forefront Threat Management Gateway) 2010의 스탠더드 버전을 설치한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="e4dd0-114">다른 리버스 프록시를 사용 하는 경우 절차가 비슷하지만 타사 제품에 대 한 설명서에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="e4dd0-115">외부 자동 검색 URL에 대 한 웹 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e4dd0-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="e4dd0-116">**시작**을 클릭 하 고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG Management**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e4dd0-117">왼쪽 창에서 **ServerName**을 확장 하 고 **방화벽 정책을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e4dd0-118">**새 웹 게시 규칙 시작** 페이지에서 새 게시 규칙에 대 한 표시 이름을 입력 합니다 (예: Lonline Cdiscoveryurl).</span><span class="sxs-lookup"><span data-stu-id="e4dd0-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="e4dd0-119">**규칙 동작 선택** 페이지에서 **허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e4dd0-120">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e4dd0-121">**서버 연결 보안** 페이지에서 **SSL을 사용 하 여 게시 된 웹 서버 또는 서버 팜에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e4dd0-122">**내부 게시 세부 정보** 페이지의 **내부 사이트 이름**에 디렉터 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다 (예: lyncdir01).</span><span class="sxs-lookup"><span data-stu-id="e4dd0-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="e4dd0-123">프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀 앞에 HLB (하드웨어 부하 분산 장치)의 VIP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="e4dd0-124">**내부 게시 세부 정보** 페이지의 **path (선택 사항)** 에 게시할 폴더 \*\* / \*\* 의 경로로 입력 한 다음 **원래 호스트 헤더 전달을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="e4dd0-125">**공개 이름 정보** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e4dd0-126">**요청 수락**에서 **이 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e4dd0-127">**공개 이름**에 **lyncdiscover를 입력 합니다.** \<sipdomain\> (외부 자동 검색 서비스 URL).</span><span class="sxs-lookup"><span data-stu-id="e4dd0-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="e4dd0-128">프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN을 입력 합니다 (예: lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e4dd0-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="e4dd0-129">**경로**에를 입력 \*\* / \*\*합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e4dd0-130">**웹 수신기 선택** 페이지의 **웹 수신기**에서 업데이트 된 공개 인증서가 있는 기존 SSL 수신기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="e4dd0-131">**인증 위임** 페이지에서 **위임 안을 선택 하지만 클라이언트가 직접 인증할 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="e4dd0-132">**사용자 설정** 페이지에서 **모든 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e4dd0-133">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e4dd0-134">웹 게시 규칙의 Forefront TMG 목록에서 방금 추가한 새 규칙을 두 번 클릭 하 여 **속성**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e4dd0-135">**대상** 탭에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="e4dd0-136">**실제 항목 대신 원본 호스트 헤더 전달을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="e4dd0-137">선택 **요청이 FOREFRONT TMG 컴퓨터에서 온 것으로 표시**됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="e4dd0-138">**브리징** 탭에서 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e4dd0-139">**웹 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e4dd0-140">**요청을 HTTP 포트로 리디렉션**을 선택 하 고 포트 번호로 **8080** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e4dd0-141">**요청을 SSL 포트로 리디렉션**을 선택 하 고 포트 번호로 **4443** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="e4dd0-142">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-142">Click **OK**.</span></span>

18. <span data-ttu-id="e4dd0-143">세부 정보 창에서 **적용** 을 클릭 하 여 변경 내용을 저장 하 고 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="e4dd0-144">**규칙 테스트** 를 클릭 하 여 새 규칙이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="e4dd0-145">기존 웹 게시 규칙을 수정 하 여 외부 자동 검색 SAN 및 URL을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e4dd0-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="e4dd0-146">**시작**을 클릭 하 고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG Management**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4dd0-147">보유 한 각 게시 규칙 및 수신기에 대해 수정 작업을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="e4dd0-148">일반적으로이는 프런트 엔드 풀에 대 한 하나의 규칙 및 수신기와 선택적 디렉터 또는 디렉터 풀 (배포 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="e4dd0-149">왼쪽 창에서 **ServerName**을 확장 하 고 **방화벽 정책을**마우스 오른쪽 단추로 클릭 한 다음 해당 규칙을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="e4dd0-150">**작업** 탭에서 **선택한 규칙 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="e4dd0-151">**공개 이름** 탭의 **이 규칙 적용 대상**에서 **다음 웹 사이트 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="e4dd0-152">**추가**를 클릭 하 고 새 자동 검색 사이트의 이름 (예: "lyncdiscover.contoso.com")을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="e4dd0-153">**수신기** 탭에서 **인증서 선택을** 클릭 하 고 추가 된 자동 검색 SAN 항목을 사용 하 여 새 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="e4dd0-154">수신기 및 웹 게시 속성을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="e4dd0-155">세부 정보 창에서 **적용** 을 클릭 하 여 변경 내용을 저장 하 고 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="e4dd0-156">**규칙 테스트** 를 클릭 하 여 새 규칙이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="e4dd0-157">포트 80에 대 한 웹 게시 규칙을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e4dd0-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="e4dd0-158">**시작**을 클릭 하 고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG Management**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e4dd0-159">왼쪽 창에서 **ServerName**을 확장 하 고 **방화벽 정책을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e4dd0-160">**새 웹 게시 규칙 시작** 페이지에서 새 게시 규칙의 표시 이름 (예: Lync 자동 검색 (HTTP))을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="e4dd0-161">**규칙 동작 선택** 페이지에서 **허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e4dd0-162">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e4dd0-163">**서버 연결 보안** 페이지에서 비보안 **연결을 사용 하 여 게시 된 웹 서버 또는 서버 팜에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e4dd0-164">**내부 게시 세부 정보** 페이지의 **내부 사이트 이름**에 프런트 엔드 풀 앞에 하드웨어 부하 분산 장치 (HLB)의 VIP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="e4dd0-165">**내부 게시 세부 정보** 페이지의 **path (선택 사항)** 에 게시할 폴더 \*\* / \*\* 의 경로로 입력 한 다음 **내부 사이트 이름 필드에 지정 된 원본 호스트 헤더**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="e4dd0-166">**공개 이름 정보** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e4dd0-167">**요청 수락**에서 **이 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e4dd0-168">**공개 이름**에 **lyncdiscover를 입력 합니다.** \<sipdomain\> (외부 자동 검색 서비스 URL).</span><span class="sxs-lookup"><span data-stu-id="e4dd0-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="e4dd0-169">**경로**에를 입력 \*\* / \*\*합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e4dd0-170">웹 **수신기 선택** 페이지의 **웹 수신기**에서 웹 수신기를 선택 하거나 새 웹 수신기 정의 마법사를 사용 하 여 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="e4dd0-171">**인증 위임** 페이지에서 **위임 없음을 선택 하 고 클라이언트가 직접 인증할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="e4dd0-172">**사용자 설정** 페이지에서 **모든 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e4dd0-173">**새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e4dd0-174">웹 게시 규칙의 Forefront TMG 목록에서 방금 추가한 새 규칙을 두 번 클릭 하 여 **속성**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e4dd0-175">**브리징** 탭에서 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e4dd0-176">**웹 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e4dd0-177">**요청을 HTTP 포트로 리디렉션**을 선택 하 고 포트 번호로 **8080** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e4dd0-178">**SSL 포트로 요청 리디렉션** 이 선택 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="e4dd0-179">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-179">Click **OK**.</span></span>

17. <span data-ttu-id="e4dd0-180">세부 정보 창에서 **적용** 을 클릭 하 여 변경 내용을 저장 하 고 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="e4dd0-181">**규칙 테스트** 를 클릭 하 여 새 규칙이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="e4dd0-182">외부 자동 검색 서비스 URL이 다른 웹 게시 규칙에 정의 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd0-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4dd0-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4dd0-183">See Also</span></span>


[<span data-ttu-id="e4dd0-184">Lync Server 2013에 대한 역방향 프록시 서버 설치</span><span class="sxs-lookup"><span data-stu-id="e4dd0-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="e4dd0-185">Lync Server 2013의 모바일 기능에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4dd0-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

