---
title: 'Lync Server 2013: 내부 에지 인터페이스에 대한 인증서 설정'
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
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="4e81f-102">Lync Server 2013에서 내부 에지 인터페이스에 대한 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="4e81f-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e81f-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="4e81f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e81f-104">인증서 마법사를 실행할 때 사용할 인증서 서식 파일 형식에 대 한 적절 한 사용 권한이 할당 된 그룹의 구성원 인 계정을 사용 하 여 로그인 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="4e81f-105">기본적으로 Lync Server 2013 인증서 요청에서는 웹 서버 인증서 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="4e81f-106">RTCUniversalServerAdmins 그룹의 구성원 인 계정을 사용 하 여이 서식 파일을 사용 하 여 인증서를 요청 하는 경우 해당 서식 파일을 사용 하는 데 필요한 등록 권한이 그룹에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="4e81f-107">각 Edge 서버의 내부 인터페이스에 단일 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="4e81f-108">내부 인터페이스에 대 한 인증서는 내부 엔터프라이즈 CA (인증 기관) 또는 공용 CA에 의해 발급 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="4e81f-109">조직에서 내부 CA를 배포한 경우 내부 인터페이스를 사용 하 여 내부 인터페이스용 인증서를 발급 하는 방법으로 공용 인증서를 사용 하 여 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="4e81f-110">내부 Windows Server 2008 CA 또는 Windows Server 2008 R2 CA를 사용 하 여 이러한 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="4e81f-111">이 및 기타 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e81f-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="4e81f-112">사이트의 내부에 지 인터페이스에 대 한 인증서를 설정 하려면이 섹션의 절차를 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="4e81f-113">각 Edge 서버에 대 한 내부 인터페이스에 대 한 CA 인증서 체인을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="4e81f-114">각 Edge 서버에서 내부 인터페이스에 대 한 CA 인증 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="4e81f-115">1 Edge 서버에서 첫 번째 지 서버 라고 하는 내부 인터페이스에 대 한 인증서 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="4e81f-116">첫 번째 Edge 서버의 내부 인터페이스에 대 한 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="4e81f-117">이 사이트의 다른 Edge 서버 (또는이 부하 분산 장치 뒤에 배포 됨)에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="4e81f-118">모든 Edge 서버의 내부 인터페이스에 대 한 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="4e81f-119">Edge 서버 (즉, 다중 사이트에 지 토폴로지) 또는 여러 부하 분산 장치 뒤에 있는 별도의 Edge 서버를 사용 하는 사이트가 여러 개 있는 경우에는 Edge 서버와 각 Edge 서버 집합에 대 한 각 사이트에 대해 이러한 단계를 수행 해야 합니다. 다른 부하 분산 장치 뒤에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e81f-120">이 섹션의 절차 단계는 Windows Server&nbsp;2008 CA, windows server&nbsp;2008&nbsp;R2 ca, Windows server 2012 CA 또는 windows server 2012 r2 Ca를 사용 하 여 각 Edge 서버에 대 한 인증서를 만드는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="4e81f-121">다른 CA에 대 한 단계별 지침은 해당 CA에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e81f-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="4e81f-122">기본적으로 인증 된 모든 사용자에 게는 인증서를 요청할 수 있는 적절 한 사용자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="4e81f-123">이 섹션의 절차는 edge 서버 배포 프로세스의 일부로 Edge 서버에서 인증서 요청을 만드는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="4e81f-124">프런트 엔드 서버를 사용 하 여 인증서 요청을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="4e81f-125">이 작업을 수행 하 여 Edge 서버의 배포를 시작 하기 전에 계획 및 배포 프로세스 초반에 인증서 요청을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="4e81f-126">이렇게 하려면 요청한 인증서가 내보낼 수 있는 개인 키를 사용 하 여 정의 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="4e81f-127">이 섹션의 절차에서는 인증서에 대 한 .cer 및. p7b 파일을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="4e81f-128">다른 형식의 파일을 사용 하는 경우 적절 하 게 해당 프로시저를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="4e81f-129">Certsrv 웹 사이트를 사용 하 여 내부 인터페이스에 대 한 CA 인증서 체인을 다운로드 하려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="4e81f-130">내부 네트워크 (즉, Edge 서버가 아님)의 Lync Server 2013 서버에 **관리자** 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="4e81f-131">**시작**을 클릭 하 고 **실행**을 클릭 한 후 다음을 입력 하 여 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="4e81f-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e81f-133">Windows Server 2008 또는 Windows Server 2008 R2 enterprise CA를 사용 하는 경우 http가 아닌 https를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="4e81f-134">발급 CA의 certsrv 웹 페이지에 있는 **작업 선택**에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="4e81f-135">**Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **Ca 인증서 체인 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="4e81f-136">**파일 다운로드** 대화 상자에서 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="4e81f-137">P7b 파일을 서버의 하드 디스크 드라이브에 저장 한 다음 각 Edge 서버의 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e81f-138">P7b 파일에는 인증 경로에 있는 모든 인증서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="4e81f-139">인증 경로를 보려면 서버 인증서를 열고 인증 경로를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="4e81f-140">MMC를 사용 하 여 내부 인터페이스에 대 한 CA 인증서 체인을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="4e81f-141">MMC (Microsoft Management Console)를 사용 하 여 도메인에 연결 된 컴퓨터에서 CA 루트 인증서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="4e81f-142">**시작**을 클릭 하 고 **실행**을 클릭 한 다음 **MMC**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="4e81f-143">MMC 콘솔에서 **파일**을 클릭 하 고 **추가/제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="4e81f-144">**스냅인 추가/제거** 대화 상자 목록에서 **인증서**를 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="4e81f-145">메시지가 표시 되 면 **컴퓨터 계정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="4e81f-146">**컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="4e81f-147">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-147">Click **Finish**.</span></span> <span data-ttu-id="4e81f-148">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-148">Click **OK**.</span></span>

4.  <span data-ttu-id="4e81f-149">**인증서 (로컬 컴퓨터)** 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="4e81f-150">**신뢰할 수 있는 루트 인증 기관**을 확장 하 고 **인증서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="4e81f-151">CA에서 발급 한 루트 인증서를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="4e81f-152">인증서를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 선택한 다음 **내보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="4e81f-153">**인증서 내보내기 마법사** 가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="4e81f-154">**인증서 내보내기 마법사**에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="4e81f-155">**파일 내보내기 형식** 대화 상자에서 내보낼 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="4e81f-156">**암호화 메시지 구문 표준 – PKCS \#7 인증서 ()를 권장 합니다. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="4e81f-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="4e81f-157">**암호화 메시지 구문 표준 – PKCS \#7 인증서 ()를 선택 하는 경우 P7B)** 인 **경우 인증 경로에 모든 인증서 포함 가능** 확인란을 선택 하 여 루트 Ca 인증서와 중개 ca 인증서를 포함 하 여 인증서 체인을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="4e81f-158">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-158">Click **Next**.</span></span>

8.  <span data-ttu-id="4e81f-159">**내보낼 파일** 대화 상자의 파일 이름 항목에서 내보낸 인증서에 대 한 경로와 파일 이름 (기본 확장명은. p7b)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="4e81f-160">필요에 따라 **찾아보기를**클릭 하 고 내보낸 인증서를 배치할 디렉터리를 찾아 내보낸 인증서의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="4e81f-161">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-161">Click **Save**.</span></span> <span data-ttu-id="4e81f-162">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-162">Click **Next**.</span></span>

9.  <span data-ttu-id="4e81f-163">작업 요약을 검토 하 고 **마침을** 클릭 하 여 인증서 내보내기를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="4e81f-164">**확인** 을 클릭 하 여 내보내기가 성공적으로 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="4e81f-165">내부 인터페이스에 대 한 CA 인증서 체인을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="4e81f-166">각 Edge 서버에서 **시작**을 클릭 하 고 **실행**을 클릭 하 고 **열기** 상자에 **mmc** 를 입력 한 다음 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="4e81f-167">**파일** 메뉴에서 **스냅인 추가/제거**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="4e81f-168">**독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="4e81f-169">**인증서 스냅인** 대화 상자에서 **컴퓨터 계정을**클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="4e81f-170">**컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="4e81f-171">**닫기를**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="4e81f-172">콘솔 트리에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관을**마우스 오른쪽 단추로 클릭 한 다음 **모든 작업**을 가리킨 다음 **가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="4e81f-173">마법사의 **가져올 파일**에서 인증서의 파일 이름 (즉, 이전 절차의 내부 인터페이스에 대 한 CA 인증 체인을 다운로드할 때 지정한 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="4e81f-174">각 Edge 서버에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="4e81f-175">내부 인터페이스에 대 한 인증서 요청을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="4e81f-176">Edge 서버 중 하나에서 배포 마법사를 시작 하 고 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e81f-177">풀의 한 위치에 여러 개의 Edge 서버가 있는 경우에는 Edge 서버 중 하나에서 인증서 마법사를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="4e81f-178">3 단계를 처음으로 실행 한 후 단추가 <STRONG>다시 실행</STRONG>되도록 변경 되 고, 모든 인증서가 요청, 설치, 할당 된 경우에만 작업이 성공적으로 완료 되었음을 나타내는 녹색 확인 표시가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="4e81f-179">**사용 가능한 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="4e81f-180">**인증서 요청** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="4e81f-181">**지연 또는 즉시 요청** 페이지에서 **지금 요청 준비를 클릭 하지만 나중에 보냅니다**.</span><span class="sxs-lookup"><span data-stu-id="4e81f-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="4e81f-182">**인증서 요청 파일** 페이지에서 요청을 저장할 전체 경로와 파일 이름 (예 **\\: c: cert\_내부\_가장자리만**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="4e81f-183">**대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿 이외의 서식 파일을 사용 하려면 **선택한 인증 기관에 대체 인증서 서식 파일 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="4e81f-184">**이름 및 보안 설정** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="4e81f-185">**이름**에 인증서의 표시 이름 (예: 내부 모서리)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="4e81f-186">비트 **길이**에서 비트 길이를 지정 합니다 (일반적으로 **2048**의 기본값).</span><span class="sxs-lookup"><span data-stu-id="4e81f-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4e81f-187">비트 길이가 높을수록 더 많은 보안이 제공 되지만 속도에 부정적인 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="4e81f-188">인증서를 내보낼 수 있어야 하는 경우 **인증서 개인 키를 내보내기 가능한 것으로 표시** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="4e81f-189">**조직 정보** 페이지에서 조직의 이름과 OU (조직 구성 단위) (예: 부서 또는 부서)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="4e81f-190">**지역 정보** 페이지에서 위치 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="4e81f-191">**제목 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채워지는 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="4e81f-192">**추가 주제 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="4e81f-193">**요청 요약** 페이지에서 요청을 생성 하는 데 사용할 인증서 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="4e81f-194">명령이 완료 되 면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="4e81f-195">인증서 요청에 대 한 로그를 보려면 **로그 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="4e81f-196">인증서 요청을 완료 하려면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="4e81f-197">**인증서 요청 파일** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="4e81f-198">생성 된 CSR (인증서 서명 요청) 파일을 보려면 **보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="4e81f-199">마법사를 닫으려면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="4e81f-200">이 파일을 CA (조직에서 엔터프라이즈 CA에 대해 지원 되는 전자 메일 또는 기타 방법에 의해)에 게 제출 하 고 응답 파일을 받을 때이 컴퓨터에 새 인증서를 복사 하 여 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="4e81f-201">내부 인터페이스용 인증서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="4e81f-202">로컬 관리자 그룹의 구성원으로 인증서 요청을 만든 Edge 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="4e81f-203">배포 마법사의 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="4e81f-204">3 단계를 처음 실행 한 후에는 단추가 **다시 실행**되도록 변경 되지만, 작업을 성공적으로 완료 했음을 나타내는 녹색 확인 표시는 모든 인증서를 요청, 설치, 할당할 때까지 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="4e81f-205">**사용 가능한 인증서 작업** 페이지에서 **a에서 인증서 가져오기를 클릭 합니다. P7b, .pfx 또는 .cer 파일**.</span><span class="sxs-lookup"><span data-stu-id="4e81f-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="4e81f-206">**인증서 가져오기** 페이지에서이 Edge 서버의 내부 인터페이스에 대해 요청 하 고 받은 인증서의 전체 경로와 파일 이름을 입력 하거나 **찾아보기를** 클릭 하 여 파일을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="4e81f-207">개인 키가 포함 된 인증서 풀의 다른 구성원에 대 한 인증서를 가져오는 경우 **인증서 파일에 certifcate의 개인 키 포함** 확인란을 선택 하 고 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="4e81f-208">풀의 Edge 서버에 대 한 개인 키를 사용 하 여 인증서를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="4e81f-209">인증서를 가져온 동일한 Edge 서버에 관리자 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="4e81f-210">**시작**을 클릭 하 고 **실행**을 클릭 한 다음 **MMC**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="4e81f-211">MMC 콘솔에서 **파일**을 클릭 하 고 **스냅인 추가/제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="4e81f-212">스냅인 추가/제거 페이지에서 **인증서**를 클릭 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="4e81f-213">인증서 스냅인 대화 상자에서 **컴퓨터 계정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="4e81f-214">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-214">Click **Next**.</span></span> <span data-ttu-id="4e81f-215">컴퓨터 선택에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="4e81f-216">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-216">Click **Finish**.</span></span> <span data-ttu-id="4e81f-217">**확인** 을 클릭 하 여 MMC 콘솔의 구성을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="4e81f-218">인증서 저장소를 확장 하려면 **인증서 (로컬 컴퓨터)** 를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="4e81f-219">**개인**을 두 번 클릭 한 다음 **인증서**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4e81f-220">로컬 컴퓨터의 인증서 개인 저장소에 인증서가 없는 경우 가져온 인증서와 관련 된 개인 키가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="4e81f-221">요청 및 가져오기 단계를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-221">Review the request and import steps.</span></span> <span data-ttu-id="4e81f-222">문제가 지속 되 면 인증 기관 관리자 또는 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e81f-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="4e81f-223">로컬 컴퓨터의 인증서 개인 저장소에서 내보내려는 인증서를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="4e81f-224">**모든 작업**을 클릭 하 고 **내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="4e81f-225">인증서 내보내기 마법사에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="4e81f-226">**예, 개인 키를 내보냅니다를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="4e81f-227">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e81f-228">예를 선택 하는 경우 <STRONG>개인 키 내보내기를</STRONG> 사용할 수 없는 경우이 인증서와 연결 된 개인 키가 내보내도록 표시 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="4e81f-229">내보내기를 계속 하기 전에 인증서가 개인 키 내보내기를 허용 하도록 표시 되어 있는지 확인 하 여 인증서를 다시 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="4e81f-230">인증 기관 관리자 또는 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e81f-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="4e81f-231">파일 내보내기 형식 대화 상자에서 **개인 정보 교환-PKCS\#12 ()을 선택 합니다. PFX)** 을 선택한 후 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="4e81f-232">가능 하면 인증 경로에 있는 모든 인증서 포함</span><span class="sxs-lookup"><span data-stu-id="4e81f-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="4e81f-233">모든 확장 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="4e81f-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="4e81f-234">Edge 서버에서 인증서를 내보낼 때 <STRONG>내보내기가 성공한 경우 개인 키 삭제</STRONG>를 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4e81f-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="4e81f-235">이 옵션을 선택 하려면 인증서와 개인 키를이 Edge 서버로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="4e81f-236">계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="4e81f-237">개인 키를 보호 하기 위해 암호를 지정 하려면 개인 키에 대 한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="4e81f-238">암호를 다시 입력 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="4e81f-239">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-239">Click **Next**.</span></span>

11. <span data-ttu-id="4e81f-240">.Pfx 파일 확장명을 사용 하 여 내보낸 인증서의 경로와 파일 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="4e81f-241">경로는 풀의 다른 모든 Edge 서버에서 액세스 하거나 USB 플래시 드라이브 등의 이동식 미디어를 통해 전송할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="4e81f-242">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-242">Click **Next**.</span></span>

12. <span data-ttu-id="4e81f-243">인증서 내보내기 마법사 완료 대화 상자에서 요약을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="4e81f-244">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-244">Click **Finish**.</span></span>

13. <span data-ttu-id="4e81f-245">성공적으로 내보내기 대화 상자에서 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="4e81f-246">[Lync Server 2013 용 외부 Edge 인터페이스에 대 한 인증서 설정](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) 에 설명 된 단계에 따라 내보낸 인증서 파일을 다른 Edge 서버로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="4e81f-247">Edge 서버에 내부 인증서를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="4e81f-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="4e81f-248">각 Edge 서버에서 배포 마법사의 **3 단계: 인증서 요청, 설치 또는 할당**에서 다음을 **다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="4e81f-249">**사용 가능한 인증서 작업** 페이지에서 **기존 인증서 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="4e81f-250">**인증서 할당** 페이지의 목록에서 **내부에 지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="4e81f-251">**인증서 저장소** 페이지에서 이전 절차에서 내부에 지에 대해 가져온 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="4e81f-252">**인증서 할당 요약** 페이지에서 설정을 검토 하 고 **다음** 을 클릭 하 여 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="4e81f-253">마법사 완료 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="4e81f-254">이 절차를 사용 하 여 내부에 지 인증서를 할당 한 후에 각 서버에서 인증서 스냅인을 열고, **인증서 (로컬 컴퓨터)** 를 확장 하 고, **개인**을 확장 하 고, **인증서**를 클릭 한 다음 세부 정보 창에서 내부에 지 인증서가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="4e81f-255">배포에 여러 개의 Edge 서버가 포함 된 경우 각 Edge 서버에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e81f-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

