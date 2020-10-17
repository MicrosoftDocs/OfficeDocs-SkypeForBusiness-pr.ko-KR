---
title: 역방향 프록시 서버를 사용 하 여 Office Web Apps 서버 게시
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
ms.openlocfilehash: cb200204cc96d40d66d0546c86687fb0e1c48de5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512235"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="d9e64-102">역방향 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시</span><span class="sxs-lookup"><span data-stu-id="d9e64-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e64-103">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d9e64-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d9e64-104">외부 사용자(조직 방화벽 외부에서 로그온하는 사용자)가 Office Web Apps PowerPoint 프레젠테이션에 액세스할 수 있도록 하려면 Office Web Apps Server 및 역방향 프록시 서버(예: Microsoft Forefront Threat Management Gateway)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="d9e64-105">즉, 웹 사이트 게시 규칙을 만들고 구성 해야 합니다. 이 규칙은 사용자가 서버에 연결할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="d9e64-106">외부 사용자에게 액세스 권한을 제공할 필요가 없으면 웹 사이트 게시 규칙을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="d9e64-107">Forefront Threat Management Gateway에서 웹 사이트 게시 규칙을 구성하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="d9e64-108">**시작**, **모든 프로그램**, **Microsoft Forefront TMG**, **Forefront TMG 관리**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d9e64-109">Forefront TMG에서 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후에 **웹 사이트 게시 규칙**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d9e64-110">웹 게시 규칙 생성 마법사의 **웹 게시 규칙 생성 마법사 시작** 페이지에서 **웹 게시 규칙 이름** 상자에 새 규칙의 이름을 **Office Web Apps Server 규칙**과 같이 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="d9e64-111">**규칙 동작 지정** 페이지에서 **허용**을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="d9e64-112">**게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="d9e64-113">**서버 연결 보안** 페이지에서 **SSL을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="d9e64-p102">**내부 게시 정보** 페이지의 **내부 사이트 이름** 상자에 Office Web Apps Server의 FQDN을 **officewebapps01.contoso.com**과 같이 입력하고 **다음**을 클릭합니다. **내부 사이트 이름** 상자에 입력한 이름은 Office Web Apps Server에 할당한 인증서의 제목 필드 또는 주체 대체 이름 필드에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="d9e64-116">**내부 게시 정보** 페이지의 **/\*** **경로 (옵션)** 상자에 다음을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="d9e64-117">/ \* 구문을 통해 사이트의 모든 폴더와 하위 폴더가 게시 되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="d9e64-118">**공개 이름 정보** 페이지의 **다음에 대한 요청 허용** 드롭다운 목록에서 **이 도메인 이름(아래에 입력)** 을 선택하고 공개 이름 상자에 Office Web Apps Server의 정규화된 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="d9e64-119">이 이름은 웹 사이트에 액세스하는 데 사용하는 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="d9e64-120">예를 들어 URL을 사용 하 여 사이트에 액세스 하는 경우 http://officewebapps01.contoso.com **공개 이름** 상자에 **officewebapps01.contoso.com** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="d9e64-121">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-121">Click **Next**.</span></span>

11. <span data-ttu-id="d9e64-122">**웹 수신기 선택** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="d9e64-123">새 웹 수신기 정의 마법사의 **웹 수신기 이름** 상자에 새 웹 수신기의 이름을 **SSL**과 같이 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="d9e64-124">**클라이언트 연결 보안** 페이지에서 **클라이언트와의 SSL 보안 연결 필요**를 선택한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="d9e64-125">**웹 수신기 IP 주소** 페이지에서 **외부**를 선택하고 **내부**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="d9e64-126">**수신기 SSL 인증서** 페이지에서 **이 웹 수신기에 단일 인증서 사용**을 선택하고 **인증서 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="d9e64-127">**인증서 선택** 대화 상자에서 이 웹 수신기에 사용할 인증서를 선택하고 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="d9e64-128">**수신기 SSL 인증서** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="d9e64-129">**인증 설정** 페이지의 **클라이언트에서 Forefront TMG에 자격 증명을 제공하는 방법 선택** 드롭다운 목록에서 **인증 없음**을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="d9e64-130">**Single Sign On 설정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="d9e64-p105">**새 웹 수신기 마법사 완료** 페이지에서 선택한 구성의 요약을 검토합니다. 검토를 마친 후 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="d9e64-133">**웹 수신기 선택** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="d9e64-134">**인증 위임** 페이지의 **Forefront TMG에서 게시된 웹 서버의 인증을 받는 데 사용하는 방법 선택** 드롭다운 목록에서 **위임 안 함 - 클라이언트에서 직접 인증**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="d9e64-p106">**사용자 집합** 페이지에서 적절한 사용자 집합이 나열되어 있는지 확인합니다. 기본적으로 이 집합은 **모든 사용자** 사용자 집합입니다. 정의했을 수 있는 다른 사용자 집합을 추가하려면 **추가**를 클릭합니다. 추가가 완료되면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="d9e64-139">**웹 게시 규칙 생성 마법사 완료** 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="d9e64-p107">**마침**을 클릭해도 프로세스가 완료되는 것은 아니며, 새 규칙이 자동으로 적용 및 사용하도록 설정되지도 않습니다. 대신 Forefront TMG 사용자 인터페이스에 나타나는 **적용** 단추를 클릭해야 합니다. **적용**을 클릭하면 **구성 변경 설명** 대화 상자가 나타납니다. 해당 대화 상자에서 **적용**을 클릭하면 새 게시 규칙이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="d9e64-144">새 규칙을 적용 한 후에는 사용자가 새 PowerPoint 프레젠테이션 기능을 사용할 수 있도록 규칙을 약간 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="d9e64-145">이렇게 하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="d9e64-146">Forefront TMG에서 새 게시 규칙의 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="d9e64-147">**속성** 대화 상자의 **대상** 탭에서 **실제 호스트 헤더 대신 원래 호스트 헤더 전달** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="d9e64-148">**트래픽** 탭에서 **필터링**을 클릭하고 **HTTP 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="d9e64-149">**규칙에 대한 HTTP 정책 구성** 대화 상자에서 **정규화 확인** 확인란 선택을 취소하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="d9e64-150">**속성** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="d9e64-p109">Forefront TMG에서 **적용**을 클릭하여 변경 내용을 사용하도록 설정합니다. **구성 변경 설명** 대화 상자가 나타나면 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="d9e64-153">설치를 완료 한 후 [Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)항목에 나와 있는 절차를 사용 하 여 Office Web apps 서버를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e64-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

