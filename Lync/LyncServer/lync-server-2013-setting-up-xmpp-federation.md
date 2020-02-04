---
title: 'Lync Server 2013: XMPP 페더레이션 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="2cbca-102">Lync Server 2013에서 XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="2cbca-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cbca-103">_**마지막으로 수정한 주제:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="2cbca-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="2cbca-104">Edge 서버에서 XMPP 프록시를 배포 하려면 XMPP 페더레이션에 대 한 Edge 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="2cbca-105">이 작업을 수행 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="2cbca-106">XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="2cbca-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="2cbca-107">Lync Server 배포 마법사가 설치 되어 있는 컴퓨터에 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2cbca-108">프런트 엔드 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="2cbca-109">Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="2cbca-110">다시 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-110">Click Run Again.</span></span>

3.  <span data-ttu-id="2cbca-111">Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="2cbca-112">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="2cbca-113">배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="2cbca-114">마침을 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="2cbca-115">Edge 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="2cbca-116">Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="2cbca-117">다시 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-117">Click Run Again.</span></span>

5.  <span data-ttu-id="2cbca-118">Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="2cbca-119">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="2cbca-120">배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="2cbca-121">마침을 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="2cbca-122">Edge 서버에서 배포 마법사의 3 단계: 인증서 요청, 설치 또는 할당에서 다음을 다시 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2cbca-123">Edge 서버를 처음 배포 하는 경우에는가 다시 실행 되는 대신 실행이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="2cbca-124">사용 가능한 인증서 작업 페이지에서 새 인증서 요청 만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="2cbca-125">인증서 요청 페이지에서 외부에 지 인증서를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="2cbca-126">지연 또는 즉시 요청 페이지에서 지금 요청 준비, 나중에 보내기 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="2cbca-127">인증서 요청 파일 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예: c:\\cert\_외부\_가장자리만).</span><span class="sxs-lookup"><span data-stu-id="2cbca-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="2cbca-128">대체 인증서 템플릿 지정 페이지에서 기본 WebServer 템플릿 이외의 서식 파일을 사용 하려면 선택한 인증 기관에 대체 인증서 서식 파일 사용 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="2cbca-129">이름 및 보안 설정 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="2cbca-130">대화명에 인증서의 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="2cbca-131">비트 길이에서 비트 길이를 지정 합니다 (일반적으로 2048의 기본값).</span><span class="sxs-lookup"><span data-stu-id="2cbca-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="2cbca-132">인증서 개인 키를 내보낼 수 있도록 표시 확인란을 선택 했는지 확인</span><span class="sxs-lookup"><span data-stu-id="2cbca-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="2cbca-133">조직 정보 페이지에서 조직과 조직 구성 단위 이름 (예: 부서 또는 부서)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="2cbca-134">지역 정보 페이지에서 위치 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="2cbca-135">제목 이름/주체 대체 이름 페이지에 마법사에서 자동으로 채워지는 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="2cbca-136">추가 주제 대체 이름이 필요한 경우 다음 두 단계에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="2cbca-137">SIP 도메인 설정의 San (주체 대체 이름) 페이지에서 도메인 확인란을 선택 하 여 sip를 추가 합니다. \<주제\> 대체 이름 목록에 항목을 sipdomain.</span><span class="sxs-lookup"><span data-stu-id="2cbca-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="2cbca-138">추가 주제 대체 이름 구성 페이지에서 필요한 추가 주체 대체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2cbca-139">XMPP 프록시를 설치 하면 기본적으로 도메인 이름 (예: contoso.com)이 SAN 항목에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="2cbca-140">더 많은 항목이 필요한 경우이 단계에서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="2cbca-141">요청 요약 페이지에서 요청을 생성 하는 데 사용할 인증서 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="2cbca-142">명령 실행이 완료 되 면 로그를 보거나 다음을 클릭 하 여 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="2cbca-143">인증서 요청 파일 페이지에서 마침을 클릭 하 여 인증서 마법사를 종료 하 고 보기를 클릭 하 여 생성 된 CSR (인증서 서명 요청) 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="2cbca-144">요청 파일을 복사 하 고 공용 인증 기관에 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="2cbca-145">공개 인증서를 받고, 가져오고, 할당 한 후에는 Edge 서버 서비스를 중지 하 고 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="2cbca-146">Lync Server 관리 콘솔에서 입력 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="2cbca-147">XMPP 페더레이션을 위해 DNS를 구성 하려면 외부 DNS:\_xmpp-server에 다음 SRV 레코드를 추가 합니다. \_tcp. \<도메인 이름\> SRV 레코드가 EDGE 서버의 액세스 가장자리 FQDN으로 확인 되며 포트 값은 5269입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="2cbca-148">또한 액세스에 지 서버의 IP 주소를 가리키는 ' A ' 호스트 레코드 (예: xmpp.contoso.com)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2cbca-149">여러 사이트에 Edge 풀을 사용 하는 경우 XMPP 페더레이션에 대해 여러 개의 SRV 레코드를 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="2cbca-150">조직의 모든 Edge 풀에 대해 SRV 레코드를 추가 하 고 각 SRV 레코드에 다른 우선 순위를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="2cbca-151">모든 Edge 풀이 실행 되는 경우 XMPP 요청은 첫 번째 우선 순위로 Edge 풀에서 처리 되지만 해당 Edge 풀이 중단 되 면 XMPP 페더레이션 기능을 다시 가져오기 위해 새 SRV 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="2cbca-152">프런트 엔드에서 Lync Server Management Shell을 열고 입력 하 여 모든 사용자를 사용할 수 있도록 하는 새 외부 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="2cbca-153">다음과 같이 입력 하 여 외부 사용자에 대해 XMPP 액세스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="2cbca-154">XMPP 프록시가 배포 되는 Edge 서버에서 명령 프롬프트 또는 Windows PowerShell™ 명령줄 인터페이스를 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="2cbca-155">명령 매개 변수 – **ano** 는 네트워크 통계 명령으로, 모든 연결 및 수신 대기 포트, 주소 및 포트를 표시 하는 **ano** 요청을 숫자 형식으로 표시 하 고 소유 프로세스 ID가 각 연결에 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="2cbca-156">문자 **|** 는 다음 command, **findstr**또는 find 문자열에 대 한 파이프를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="2cbca-157">Findstr에 매개 변수로 전달 되는 숫자 5269 및 23456는 문자열 5269 및 23456에 대 한 netstat의 출력을 검색 하도록 findstr에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="2cbca-158">XMPP가 올바르게 구성 되어 있으면 명령 결과에 Edge 서버의 외부 (포트 5269) 및 내부 (포트 23456) 인터페이스를 통해 연결을 수신 하 고 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="2cbca-159">명령에 설정 된 포트나 수신 대기 하는 포트 (5269 및 23456)가 반환 되지 않으면 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="2cbca-160">XMPP 페더레이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cbca-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="2cbca-161">XMPP 프록시가 실행 중인지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="2cbca-162">XMPP 프록시 서비스를 로컬 관리자 그룹의 구성원으로 실행 하는 Edge 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="2cbca-163">**시작**, **모든 프로그램**, **관리 도구**, **서비스** 를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="2cbca-164">서비스에서 Lync Server XMPP 번역 게이트웨이 프록시를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="2cbca-165">서비스는 **시작 됨** 상태 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="2cbca-166">시작 되지 않은 경우 도구 모음에서 **시작** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="2cbca-167">아이콘이 녹색으로 오른쪽을 가리키는 화살표로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="2cbca-168">서비스가 **시작**됨으로 변경 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="2cbca-169">성공적으로 시작 되 면 **서비스** 를 종료 하 고 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="2cbca-170">서비스를 성공적으로 시작 하지 않은 경우 관리 도구에서 이벤트 뷰어를 열고 **응용 프로그램 및 서비스 로그**의 **Lync Server** 부분에서 오류 및 경고를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbca-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="2cbca-171">**Lync Server XMPP 번역 게이트웨이** 서비스가 실행 되 고 나면 이전에 사용 된 netstat 명령을 다시 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="2cbca-172">설정 또는 수신 대기 중인 세션이 표시 되지 않는 경우 토폴로지 작성기에서 **Xmpp 페더레이션 경로가** 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="2cbca-173">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="2cbca-174">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="2cbca-175">토폴로지 작성기에서 xmpp 페더레이션 경로의 사이트를 선택 하 고 검토를 통해 **xmpp 페더레이션** 에 대 한 **사이트 페더레이션 경로 할당이** 선택한 xmpp 페더레이션 경로 할당으로 edge 서버 또는 edge 풀을 표시 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="2cbca-176">경로 할당이 올바르지 않거나 설정 되어 있지 않으면 사이트를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="2cbca-177">XMPP 페더레이션 확인란을 선택 하 고 올바른 Edge 서버 또는 Edge 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="2cbca-178">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-178">Publish the topology.</span></span> <span data-ttu-id="2cbca-179">자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbca-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2cbca-180">필수는 아니지만 일반적으로 필요 하지는 않지만 Edge 서버를 다시 시작 해야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="2cbca-181">이전에 사용 된 netstat 프로세스를 사용 하 여 Edge 서버가 지금 수신 대기 중이거나 포트 5269 및 포트 23456에서 세션을 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="2cbca-182">여전히 예상 되는 세션이 표시 되지 않으면 통신 문제가 발생할 수 있는 원인이 이벤트 뷰어를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbca-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cbca-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cbca-183">See Also</span></span>


[<span data-ttu-id="2cbca-184">Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="2cbca-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="2cbca-185">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="2cbca-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

