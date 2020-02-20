---
title: 'Lync Server 2013: 내부에 지 인터페이스에 대 한 인증서 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1e43527c188b95863f2285c1adf4107ea53ebed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="80f9f-102">Lync Server 2013에서 내부에 지 인터페이스에 대 한 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="80f9f-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80f9f-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="80f9f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80f9f-104">인증서 마법사를 실행할 때는 사용할 인증서 템플릿의 유형에 대해 적절한 권한이 할당된 그룹 구성원인 계정을 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="80f9f-105">기본적으로 Lync Server 2013 인증서 요청은 웹 서버 인증서 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="80f9f-106">RTCUniversalServerAdmins 그룹 구성원인 계정을 사용하여 이 템플릿을 사용하는 인증서를 요청하는 경우 이 그룹에 해당 템플릿을 사용하는 데 필요한 등록 권한이 할당되었는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="80f9f-p102">각 에지 서버의 내부 인터페이스에는 단일 인증서가 필요합니다. 내부 인터페이스의 인증서는 내부 엔터프라이즈 CA(인증 기관) 또는 공용 CA에서 발행할 수 있습니다. 조직에 내부 CA가 배포되어 있는 경우 내부 CA를 통해 내부 인터페이스의 인증서를 발행하여 공용 인증서 사용 비용을 절약할 수 있습니다. 내부 Windows Server 2008 CA 또는 Windows Server 2008 R2 CA를 사용하여 이러한 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="80f9f-111">이 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="80f9f-112">사이트의 내부 에지 인터페이스에서 인증서를 설정하려면 이 섹션의 절차를 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="80f9f-113">내부 인터페이스에 대한 CA 인증 체인을 각 에지 서버에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="80f9f-114">각 에지 서버에서 내부 인터페이스에 대한 CA 인증 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="80f9f-115">한 에지 서버(첫 번째 에지 서버)에서 내부 인터페이스에 대한 인증서 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="80f9f-116">첫 번째 에지 서버에서 내부 인터페이스에 대한 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="80f9f-117">이 사이트의 다른 에지 서버 또는 이 부하 분산 장치 뒤에 배포된 다른 에지 서버에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="80f9f-118">모든 에지 서버의 내부 인터페이스에 대한 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="80f9f-119">에지 서버를 가진 사이트가 두 개 이상이거나(즉, 다중 사이트 에지 토폴로지) 여럿으로 나뉜 에지 서버 집합을 서로 다른 부하 분산 장치 뒤에 배포한 경우에는 에지 서버가 있는 각 사이트와 서로 다른 부하 분산 장치 뒤에 배포된 각 에지 서버 집합에 대해 이러한 단계의 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80f9f-120">이 섹션의 절차를 수행 하는 단계는 Windows Server&nbsp;2008 CA, windows server&nbsp;2008&nbsp;R2 ca, Windows server 2012 CA 또는 windows server 2012 r2 ca를 사용 하 여 각에 지 서버에 대 한 인증서를 만드는 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="80f9f-121">다른 CA에 대한 단계별 지침은 해당 CA의 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="80f9f-122">기본적으로 인증된 모든 사용자는 인증서를 요청할 수 있는 적합한 사용자 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="80f9f-p104">이 섹션의 절차에서는 에지 서버 배포 프로세스의 일부로 에지 서버에서 인증서 요청을 만드는 방법을 다룹니다. 프런트 엔드 서버를 사용하여 인증서 요청을 만들 수 있습니다. 이 작업을 수행하면 에지 서버의 배포를 시작하기 전에 계획 및 배포 프로세스 초기에 인증서 요청을 완료할 수 있습니다. 이 작업을 수행하려면 요청한 인증서가 내보낼 수 있는 개인 키를 사용하여 정의되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="80f9f-p105">이 섹션의 절차에서는 인증서에 대해 .cer 및 .p7b 파일을 사용하는 방법을 설명합니다. 다른 파일 형식을 사용하는 경우 이러한 절차를 적절하게 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="80f9f-129">certsrv 웹 사이트를 사용하여 내부 인터페이스에 대한 CA 인증 체인을 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="80f9f-130">**Administrators** 그룹의 구성원으로 서 내부 네트워크 (에 지 서버는 아님)에 있는 Lync server 2013 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="80f9f-131">**시작**을 클릭하고 **실행**을 클릭한 후 다음을 입력하여 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="80f9f-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80f9f-133">Windows Server 2008 또는 Windows Server 2008 R2 엔터프라이즈 CA를 사용하는 경우 http가 아니라 https를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="80f9f-134">발급 CA의 certsrv 웹 페이지에 있는 **작업 선택**에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="80f9f-135">**CA 인증서, 인증서 체인 또는 CRL 다운로드**에서 **CA 인증서 체인 다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="80f9f-136">**파일 다운로드** 대화 상자에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="80f9f-137">.p7b 파일을 서버의 하드 디스크 드라이브에 저장한 다음 각 에지 서버의 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80f9f-p106">p7b 파일에는 인증 경로에 있는 모든 인증서가 포함됩니다. 인증 경로를 보려면 서버 인증서를 열고 해당 인증 경로를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="80f9f-140">MMC를 사용하여 내부 인터페이스에 대한 CA 인증 체인을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="80f9f-141">MMC (Microsoft Management Console)를 사용 하 여 도메인에 가입 된 컴퓨터에서 CA 루트 인증서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="80f9f-142">**시작**, **실행**을 차례로 클릭하고 **MMC**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="80f9f-143">MMC 콘솔에서 **파일**을 클릭하고 **추가/제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="80f9f-p108">**스냅인 추가/제거** 대화 상자 목록에서 **인증서**를 선택한 후 **추가**를 클릭합니다. 메시지가 표시되면 **컴퓨터 계정**을 선택합니다. **컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터**를 선택합니다. **마침**을 클릭한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="80f9f-p109">**인증서(로컬 컴퓨터)**, **신뢰할 수 있는 루트 인증 기관**을 차례로 확장한 다음 **인증서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="80f9f-p110">CA에서 발급된 루트 인증서를 클릭합니다. 이 인증서를 마우스 오른쪽 단추로 클릭하고 **모든 작업**, **내보내기**를 차례로 선택합니다. **인증서 내보내기 마법사**가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="80f9f-154">**인증서 내보내기 마법사**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="80f9f-155">**파일 내보내기 형식** 대화 상자에서 내보낼 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="80f9f-156">**암호화 메시지 구문 Standard-PKCS \#7 인증서 (. P7B)**</span><span class="sxs-lookup"><span data-stu-id="80f9f-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="80f9f-157">**암호화 메시지 구문 Standard-PKCS \#7 인증서 (를 선택 하는 경우 P7B)** 에서 루트 CA 인증서 및 중간 CA 인증서를 포함 하 여 인증서 체인을 내보내려면 **인증 경로에서 모든 인증서 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="80f9f-158">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-158">Click **Next**.</span></span>

8.  <span data-ttu-id="80f9f-p112">**내보낼 파일** 대화 상자에서 파일 이름 항목에 내보내는 인증서의 경로와 파일 이름(기본 확장명: .p7b)을 입력합니다. 또는 **찾아보기**를 클릭하여 내보내는 인증서를 배치할 디렉터리를 찾고 내보내는 인증서의 이름을 제공합니다. **저장**을 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="80f9f-p113">작업에 대한 요약 내용을 검토하고 **마침**을 클릭하여 인증서 내보내기를 완료합니다. **확인**을 클릭하여 내보내기 성공을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="80f9f-165">내부 인터페이스에 대한 CA 인증 체인을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="80f9f-166">각 에지 서버에서 **시작**, **실행**을 차례로 클릭하고 **열기** 상자에 **mmc**를 입력한 다음 **확인**을 클릭하여 MMC(Microsoft Management Console)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="80f9f-167">**파일** 메뉴에서 **스냅인 추가/제거**를 클릭한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="80f9f-168">**독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="80f9f-169">**인증서 스냅인** 대화 상자에서 **컴퓨터 계정**을 클릭한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="80f9f-170">**컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행되고 있는 컴퓨터)** 확인란이 선택되었는지 확인한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="80f9f-171">**닫기**를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="80f9f-172">콘솔 트리에서 **인증서(로컬 컴퓨터)** 를 확장하고 **신뢰할 수 있는 루트 인증 기관**을 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 가리킨 다음 **가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="80f9f-173">마법사의 **가져올 파일**에서 인증서의 파일 이름을 지정합니다(즉, 이전 절차에서 내부 인터페이스의 CA 인증 체인을 다운로드할 때 지정한 이름).</span><span class="sxs-lookup"><span data-stu-id="80f9f-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="80f9f-174">각 에지 서버에서 이 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="80f9f-175">내부 인터페이스에 대한 인증서 요청을 만들려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="80f9f-176">에지 서버 중 하나에서 배포 마법사를 시작하고 **3단계: 인증서 요청, 설치 또는 할당** 옆에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80f9f-177">풀에 여러 에지 서버가 있는 경우 에지 서버 중 하나에서 인증서 마법사를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="80f9f-178">3단계를 처음 실행하면 단추가 <STRONG>다시 실행</STRONG>으로 변경되고, 필요한 모든 인증서가 요청, 설치 및 할당된 후에만 작업의 성공적인 완료를 나타내는 녹색 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="80f9f-179">**사용할 수 있는 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="80f9f-180">**인증서 요청** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="80f9f-181">**지연 또는 즉시 요청** 페이지에서 **지금 요청을 준비하고 나중에 보냅니다**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="80f9f-182">**인증서 요청 파일** 페이지에서 요청을 저장할 전체 경로와 파일 이름을 입력 합니다 (예를 들어, **\\c: cert\_내부\_에 지**).</span><span class="sxs-lookup"><span data-stu-id="80f9f-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="80f9f-183">**대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 **선택한 인증 기관에 대체 인증서 템플릿 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="80f9f-184">**이름 및 보안 설정** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="80f9f-185">**대화명**에서 인증서의 표시 이름을 입력합니다(예: 내부 에지).</span><span class="sxs-lookup"><span data-stu-id="80f9f-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="80f9f-186">**비트 길이**에서 비트 길이(일반적으로 기본값은 **2048**)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="80f9f-187">비트 길이가 길수록 보안은 강화되지만 속도는 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="80f9f-188">인증서를 내보낼 수 있게 만들어야 하는 경우 **인증서의 개인 키를 내보낼 수 있는 것으로 표시** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="80f9f-189">**조직 정보** 페이지에서 조직과 조직 구성 단위(OU)의 이름(예: 사업부 또는 부서)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="80f9f-190">**지역 정보** 페이지에서 위치 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="80f9f-191">**주체 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="80f9f-192">**추가 주체 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="80f9f-193">**요청 요약** 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="80f9f-194">명령이 완료되면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="80f9f-195">인증서 요청 로그를 보려면 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="80f9f-196">인증서 요청을 완료하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="80f9f-197">**인증서 요청 파일** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="80f9f-198">생성된 CSR(인증서 서명 요청) 파일을 보려면 **보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="80f9f-199">마법사를 닫으려면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="80f9f-200">전자 메일이나 조직에서 엔터프라이즈 CA에 대해 지원하는 다른 방법으로 이 파일을 CA로 제출하고, 응답 파일을 받으면 새 인증서를 이 컴퓨터로 복사하여 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="80f9f-201">내부 인터페이스에 대한 인증서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="80f9f-202">로컬 Administrators 그룹의 구성원으로 인증서 요청을 만든 에지 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="80f9f-203">배포 마법사의 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="80f9f-204">3단계를 처음 실행하면 단추가 **다시 실행**으로 변경되고, 필요한 모든 인증서가 요청, 설치 및 할당된 후에만 작업의 성공적인 완료를 나타내는 녹색 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="80f9f-205">**사용할 수 있는 인증서 작업** 페이지에서 **.P7b, .pfx 또는 .cer 파일에서 인증서 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="80f9f-206">**인증서 가져오기** 페이지에서 이 에지 서버의 내부 인터페이스에 대해 요청하고 수신한 인증서의 전체 경로 및 파일 이름을 입력합니다(또는 **찾아보기**를 클릭하여 파일을 찾아 선택합니다).</span><span class="sxs-lookup"><span data-stu-id="80f9f-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="80f9f-207">풀에서 개인 키를 포함하는 다른 구성원의 인증서를 가져오려면 **인증서 파일에 인증서의 개인 키가 있음** 확인란을 선택하고 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="80f9f-208">풀의 에지 서버에 대해 개인 키를 사용하여 인증서를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="80f9f-209">인증서를 가져온 것과 동일한 에지 서버에 Administrators 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="80f9f-210">**시작**, **실행**을 차례로 클릭하고 **mmc**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="80f9f-211">MMC 콘솔에서 **파일**을 클릭하고 **스냅인 추가/제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="80f9f-212">스냅인 추가 또는 제거 페이지에서 **인증서**, **추가**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="80f9f-p114">인증서 스냅인 대화 상자에서 **컴퓨터 계정**을 선택합니다. **다음**을 클릭합니다. 컴퓨터 선택에서 **로컬 컴퓨터: (이 콘솔이 실행되고 있는 컴퓨터)** 를 선택합니다. **마침**을 클릭합니다. **확인**을 클릭하여 MMC 콘솔의 구성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="80f9f-p115">**인증서(로컬 컴퓨터)** 를 두 번 클릭하여 인증서 저장소를 확장하고 **개인**, **인증서**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="80f9f-p116">인증서 개인 저장소에 로컬 컴퓨터에 대한 인증서가 없으면 가져온 인증서와 연관된 개인 키도 없습니다. 요청 및 가져오기 단계를 검토하십시오. 문제가 계속되면 인증 기관 관리자 또는 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="80f9f-p117">로컬 컴퓨터의 인증서 개인 저장소에서 내보내려는 인증서를 마우스 오른쪽 단추로 클릭하고, **모든 작업**, **내보내기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="80f9f-p118">인증서 내보내기 마법사에서 **다음**을 클릭합니다. **예, 개인 키를 내보냅니다.** 를 선택합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80f9f-p119"><STRONG>예, 개인 키를 내보냅니다.</STRONG> 선택 항목을 사용할 수 없으면 이 인증서와 연관된 개인 키가 내보내기용으로 표시되지 않은 것입니다. 인증서를 다시 요청하여 내보내기를 계속하기 전에 개인 키의 내보내기가 허용되도록 인증서가 표시되었는지 확인해야 합니다. 인증 기관 관리자 또는 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="80f9f-231">파일 형식 내보내기 대화 상자에서 **개인 정보 교환-PKCS\#12 (을 클릭 합니다. PFX)** 를 선택한 후 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="80f9f-232">가능하면 인증 경로에 있는 인증서를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="80f9f-233">모든 확장된 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="80f9f-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="80f9f-p120">에지 서버에서 인증서를 내보낼 때는 <STRONG>내보내기가 완료되면 개인 키 삭제</STRONG>를 선택하지 마십시오. 이 옵션을 선택하면 인증서 및 개인 키를 이 에지 서버로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="80f9f-236">계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="80f9f-p121">개인 키를 보호하기 위한 암호를 지정하려면 개인 키의 암호를 입력한 후 다시 암호를 입력하여 확인합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="80f9f-p122">파일 확장명 .pfx를 사용하여 내보낸 인증서에 대한 경로 및 파일 이름을 입력합니다. 경로는 풀의 다른 모든 에지 서버에서 액세스할 수 있거나 USB 플래시 드라이브와 같은 이동식 미디어를 사용하여 전송할 수 있어야 합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="80f9f-p123">인증서 내보내기 마법사 완료 대화 상자에서 요약 내용을 검토한 후 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="80f9f-245">내보내기 성공 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="80f9f-246">[Lync Server 2013의 외부에 지 인터페이스에 대 한 인증서 설정](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) 절차에 설명 된 단계에 따라 내보낸 인증서 파일을 다른에 지 서버로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="80f9f-247">에지 서버에서 내부 인증서를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="80f9f-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="80f9f-248">각 에지 서버의 배포 마법사에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="80f9f-249">**사용할 수 있는 인증서 작업** 페이지에서 **기존 인증서 할당**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="80f9f-250">**인증서 할당** 페이지의 목록에서 **에지 내부**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="80f9f-251">**인증서 저장소** 페이지에서 내부 에지에 대해 가져온 인증서를 선택합니다(이전 절차에서 가져온 인증서).</span><span class="sxs-lookup"><span data-stu-id="80f9f-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="80f9f-252">**인증서 지정 요약** 페이지에서 설정을 검토하고 **다음**을 클릭하여 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="80f9f-253">마법사 완료 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="80f9f-254">이 절차를 통해 내부 에지 인증서를 할당한 후에는 각 서버에서 인증서 스냅인을 열고 **인증서(로컬 컴퓨터)**, **개인**을 차례로 확장하고 **인증서**를 클릭한 다음 세부 정보 창에 해당 내부 에지 인증서가 나열되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="80f9f-255">배포에 여러 에지 서버가 포함된 경우 각 에지 서버에 대해 이 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="80f9f-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

