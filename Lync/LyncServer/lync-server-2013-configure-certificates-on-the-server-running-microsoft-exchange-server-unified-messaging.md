---
title: 'Lync Server 2013: Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="21264-102">Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="21264-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21264-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="21264-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="21264-104">계획 설명서의 [Lync Server 2013에서 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 에 설명 된 대로 exchange Um (통합 메시징)를 배포 하 고 조직의 Enterprise Voice 사용자에 게 exchange um 기능을 제공 하려는 경우 다음 절차를 사용 하 여 exchange um을 실행 하는 서버에서 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21264-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21264-105">내부 인증서의 경우 Lync Server 2013를 실행 하는 서버와 Microsoft Exchange를 실행 하는 서버에 모두 상호 신뢰 되는 신뢰할 수 있는 루트 인증 기관 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="21264-106">CA (인증 기관)가 신뢰할 수 있는 루트 인증 기관 인증서 저장소에 등록 되어 있는 경우 해당 서버는 동일 하거나 다른 인증 기관 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="21264-107">Lync Server 2013에 연결 하려면 서버 인증서를 사용 하 여 Exchange 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="21264-108">Exchange 서버에 대 한 CA 인증서를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="21264-109">Exchange 서버에 대 한 CA 인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="21264-110">CA가 Exchange Server의 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="21264-111">Exchange 서버에 대 한 인증서 요청을 만들고 인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="21264-112">Exchange 서버에 대 한 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="21264-113">CA 인증서를 다운로드 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="21264-114">Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **발급 하는 CA 서버\<\>/certsrv의 http://이름을**입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="21264-115">**작업 선택**에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="21264-116">**Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **Base 64에 대 한 인코딩 방법을**선택한 다음 **CA 인증서 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21264-117">이 단계에서 DER (고유 인코딩 규칙) 인코딩을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21264-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="21264-118">DER 인코딩을 선택 하는 경우이 절차의 다음 단계인 <STRONG>CA 인증서를 설치 하</STRONG> 는 10 단계의 파일 형식은. .cer이 아닌.</span><span class="sxs-lookup"><span data-stu-id="21264-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="21264-119">**파일 다운로드** 대화 상자에서 **저장**을 클릭 한 다음 서버의 하드 디스크에 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="21264-120">(이 파일에는 이전 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 확장명 중 하나가 사용 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="21264-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="21264-121">CA 인증서를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="21264-122">Exchange UM을 (를) 실행 하는 서버에서 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 **열기** 상자에 **mmc** 를 입력 하 고 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21264-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="21264-123">**파일** 메뉴에서 **스냅인 추가/제거**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="21264-124">**독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="21264-125">**인증서 스냅인** 대화 상자에서 **컴퓨터 계정을**클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="21264-126">**컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="21264-127">**닫기를**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="21264-128">콘솔 트리에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관을**확장 한 다음 **인증서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="21264-129">**인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="21264-130">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-130">Click **Next**.</span></span>

10. <span data-ttu-id="21264-131">**찾아보기를** 클릭 하 여 파일을 찾은 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="21264-132">(이 파일은 **CA 인증서를 다운로드 하기 위해**3 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 파일 확장명을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="21264-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="21264-133">**모든 인증서를 다음 저장소에**저장을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="21264-134">**찾아보기를**클릭 한 다음 **신뢰할 수 있는 루트 인증 기관을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="21264-135">**다음** 을 클릭 하 여 설정을 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="21264-136">CA가 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 하려면 다음을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="21264-137">Exchange UM을 실행 하는 서버의 MMC에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관**을 확장 한 다음 **인증서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="21264-138">세부 정보 창에서 CA가 신뢰할 수 있는 Ca 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="21264-139">Lync Server를 사용 하 여 Exchange Server 2013 UM을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="21264-140">자세한 내용은 Exchange Server 설명서에서 "Lync 서버와 Exchange 2013 UM 통합"을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span><span class="sxs-lookup"><span data-stu-id="21264-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="21264-141">인증서 요청을 만들고이 인증서를 Exchange Server 2007 (SP1)에 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="21264-142">Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 발급 하는 CA 서버**\>/certsrv**의 **http://\<** 이름을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="21264-143">**작업 선택**에서 **인증서 요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="21264-144">**인증서 요청**에서 **고급 인증서 요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="21264-145">**고급 인증서 요청**에서 **이 CA에 대 한 요청 만들기 및 제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="21264-146">**고급 인증서 요청**에서 서버 인증을 위해 구성 된 **웹 서버** 또는 다른 서버 인증서 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="21264-147">**오프 라인 서식 파일에 대 한 정보 확인**아래에 있는 **이름** 상자에 Exchange Server의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21264-148">통신을 사용 하려면 Exchange 서버의 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="21264-149">**키 옵션**에서 **로컬 컴퓨터 인증서 저장소에 인증서 저장** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="21264-150">웹 페이지 아래쪽에 있는 **제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="21264-151">확인 하 라는 메시지가 열리는 대화 상자에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="21264-152">인증서 발급 됨 페이지의 **인증서 발급 됨**에서 **이 인증서 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="21264-153">확인 하 라는 메시지가 열리는 대화 상자에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="21264-154">"새 인증서가 성공적으로 설치 되었습니다" 라는 메시지가 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="21264-155">Exchange Server 2010에서 인증서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="21264-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="21264-156">적절 한 사용자 권한을 사용 하 여 Exchange UM을 (를) 실행 하는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="21264-157">자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"클라이언트 액세스 권한"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21264-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="21264-158">인증서를 만들려면 다음 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21264-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="21264-159">"새 Exchange 인증서 만들기"[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="21264-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="21264-160">"Exchange 인증서 가져오기"[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="21264-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21264-161">인증서 <STRONG>주체 이름의</STRONG>경우 통신이 작동 하려면 EXCHANGE 서버의 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="21264-162">Exchange Server 2007 (SP1)에서 인증서를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="21264-163">Exchange UM을 (를) 실행 하는 서버에서 MMC를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21264-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="21264-164">콘솔 트리에서 **개인** 을 확장 한 다음 **인증서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="21264-165">세부 정보 창에서 개인 인증서가 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="21264-166">인증서를 두 번 클릭 하 여 세부 정보를 읽고 유효한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21264-167">인증서가 유효한 것으로 표시 되기까지 몇 분이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21264-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="21264-168">Microsoft Exchange 통합 메시징 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21264-169">Exchange Server 2007 SP1 통합 메시징을 실행 하는 서버는 올바른 인증서를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="21264-170">이벤트 뷰어를 열고 Exchange Server 2007 SP1 통합 메시징을 실행 하는 서버가 검색 한 인증서를 지정 하는 이벤트 ID 1112을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="21264-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="21264-171">Exchange Server 2010에서 인증서를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="21264-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="21264-172">적절 한 사용자 권한을 사용 하 여 Exchange UM을 (를) 실행 하는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="21264-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="21264-173">자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"클라이언트 액세스 권한"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21264-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="21264-174">인증서를 할당 하는 절차는에서 [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)"인증서에 서비스 할당"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21264-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

