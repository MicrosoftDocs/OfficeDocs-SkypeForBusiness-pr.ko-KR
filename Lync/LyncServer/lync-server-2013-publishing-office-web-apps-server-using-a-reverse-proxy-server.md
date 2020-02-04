---
title: 역방향 프록시 서버를 사용하여 Office Online Server 게시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="d4544-102">리버스 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시</span><span class="sxs-lookup"><span data-stu-id="d4544-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4544-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d4544-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d4544-104">외부 사용자 (즉, 조직의 방화벽 외부에서 로그온 하는 사용자)가 Office Web Apps Server PowerPoint 프레젠테이션에 액세스할 수 있도록 하려면 Office Web Apps 서버와 Microsoft Forefront와 같은 역방향 프록시 서버를 사용 해야 합니다. 위협 관리 게이트웨이.</span><span class="sxs-lookup"><span data-stu-id="d4544-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="d4544-105">이는 또한 사용자가 웹 사이트 게시 규칙을 만들고 구성 해야 한다는 것을 의미 합니다. 이 규칙은 사용자가 서버에 연결할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="d4544-106">외부 사용자에 대 한 액세스를 제공할 필요가 없는 경우에는 웹 사이트 게시 규칙을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="d4544-107">Forefront Threat Management Gateway에서 웹 사이트 게시 규칙을 구성 하려면 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="d4544-108">**시작**, **모든 프로그램**, **MICROSOFT Forefront TMG**, **forefront TMG Management**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d4544-109">Forefront TMG에서 **방화벽 정책을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d4544-110">새 웹 게시 규칙 마법사의 **새 웹 게시 규칙 마법사 시작** 페이지에서 **웹 게시 규칙 이름** 상자에 새 규칙의 이름 (예: **Office Web Apps 서버 규칙**)을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="d4544-111">**규칙 동작 지정** 페이지에서 **허용** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="d4544-112">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="d4544-113">**서버 연결 보안** 페이지에서 **SSL을 사용 하 여 게시 된 웹 서버 또는 서버 팜에 연결** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="d4544-114">**내부 게시 세부 정보** 페이지에서 **내부 사이트 이름** 상자에 Office Web Apps 서버 (예: **officewebapps01.contoso.com**)의 FQDN을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="d4544-115">**내부 사이트 이름** 상자에 입력 한 이름은 Office Web Apps Server에 할당 한 인증서의 제목 필드 또는 주체 대체 이름 필드에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="d4544-116">**내부 게시 세부 정보** 페이지에서 \*\* / \*\* **경로 (선택 사항)** 상자에 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="d4544-117">/\* 구문을 사용 하면 사이트에 대 한 모든 폴더와 하위 폴더가 게시 되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="d4544-118">**공개 이름 정보** 페이지에서 다음 **에 대 한 요청 허용** 드롭다운 목록에서 **이 도메인 이름 (아래에 입력)** 을 선택한 다음, 공공 이름 상자에 Office Web Apps 서버의 정규화 된 항목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="d4544-119">이 이름은 웹 사이트에 액세스 하는 데 사용 되는 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="d4544-120">예를 들어 URL http://officewebapps01.contoso.com 을 사용 하 여 사이트에 액세스 한 경우에는 **공용 이름** 상자에 **officewebapps01.contoso.com** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="d4544-121">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-121">Click **Next**.</span></span>

11. <span data-ttu-id="d4544-122">**웹 수신기 선택** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="d4544-123">새 웹 수신기 정의 마법사의 **웹 수신기 이름** 상자에 새 웹 수신기의 이름 (예: **SSL**)을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="d4544-124">**클라이언트 연결 보안** 페이지에서 **클라이언트와 SSL 보안 연결 필요** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="d4544-125">**웹 수신기 IP 주소** 페이지에서 **외부**를 선택 하 고 **내부**를 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="d4544-126">**수신기 SSL 인증서** 페이지에서 **이 웹 수신기에 대해 단일 인증서 사용** 을 선택한 다음 **인증서 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="d4544-127">**인증서 선택** 대화 상자에서이 웹 수신기에 사용할 인증서를 선택한 다음 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="d4544-128">**수신기 SSL 인증서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="d4544-129">**인증 설정** 페이지의 **클라이언트가 Forefront TMG에 자격 증명을 제공 하는 방법 선택** 드롭다운 목록에서 **인증 안** 됨을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="d4544-130">**단일 사인온 설정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="d4544-131">**새 웹 수신기 마법사 완료** 페이지에서 사용자가 만든 구성 선택 사항에 대 한 요약을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="d4544-132">준비가 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="d4544-133">**웹 수신기 선택** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="d4544-134">**인증 위임** 페이지에서 **위임 없음을 선택 하지만 클라이언트가** **Forefront TMG에서 게시 된 웹 서버 인증을 위해 사용 하는 메서드 선택** 드롭다운 목록에서 직접 인증 하 고 **다음**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="d4544-135">**사용자 집합** 페이지에서 적절 한 사용자 집합이 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="d4544-136">기본적으로이 사용자 집합은 **모든 사용자** 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="d4544-137">**추가** 를 클릭 하 여 정의한 다른 사용자 집합을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="d4544-138">완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="d4544-139">**새 웹 게시 규칙 마법사 완료** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="d4544-140">**마침을** 클릭 해도 프로세스가 완료 되었음을 의미 하지는 않습니다. 즉, 새 규칙을 자동으로 적용 하 고 사용 하도록 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="d4544-141">대신 Forefront TMG 사용자 인터페이스에 표시 되는 **적용** 단추를 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="d4544-142">**구성 변경 설명** **적용** 대화 상자가 표시 되 면을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="d4544-143">이 대화 상자에서 **적용** 을 클릭 하 여 새 게시 규칙을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="d4544-144">새 규칙을 적용 한 후에는 사용자가 새로운 PowerPoint 프레젠테이션 기능을 사용할 수 있도록 규칙을 약간 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="d4544-145">이렇게 하려면 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="d4544-146">Forefront TMG에서 새 게시 규칙의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="d4544-147">**속성** 대화 상자의 **받는 사람** 탭에서 **실제 항목 대신 원래 호스트 헤더를 전달**하는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="d4544-148">**트래픽** 탭에서 **필터링** 을 클릭 한 다음 **HTTP 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="d4544-149">**규칙에 대 한 HTTP 정책 구성** 대화 상자에서 **정규화 확인** 확인란의 선택을 취소 한 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="d4544-150">**속성** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="d4544-151">Forefront TMG에서 **적용** 을 클릭 하 여 변경 내용을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="d4544-152">**구성 변경 설명** 대화 상자가 표시 되 면 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="d4544-153">설치를 완료 한 후 [Lync server 2013에서 Office Web Apps 서버의 구성 유효성 검사](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)항목에 있는 절차를 사용 하 여 Office Web apps 서버를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4544-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

