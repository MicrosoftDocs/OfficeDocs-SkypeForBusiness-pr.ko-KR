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
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497525"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b72e8-102">Lync Server 2013에서 XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="b72e8-102">Setting up XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b72e8-103">_**마지막으로 수정 된 항목:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="b72e8-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="b72e8-p101">에지 서버에 XMPP 프록시를 배포하려면 XMPP 페더레이션의 에지 서버를 구성해야 합니다. 이렇게 하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="b72e8-106">XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="b72e8-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="b72e8-107">Lync Server 배포 마법사가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b72e8-p102">프런트 엔드 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭한 후 Lync Server 구성 요소 설치 또는 제거를 클릭합니다. 다시 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="b72e8-p103">Lync Server 구성 요소 설치에서 다음을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 로그 보기를 클릭하여 사용 가능한 로그 파일을 확인합니다. 마침을 클릭하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="b72e8-p104">에지 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭한 후 Lync Server 구성 요소 설치 또는 제거를 클릭합니다. 다시 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="b72e8-p105">Lync Server 구성 요소 설치에서 다음을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 로그 보기를 클릭하여 사용 가능한 로그 파일을 확인합니다. 마침을 클릭하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="b72e8-122">에지 서버의 배포 마법사에서 3단계: 인증서 요청, 설치 또는 지정 옆에 있는 다시 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b72e8-123">에지 서버를 처음 배포하는 경우 다시 실행 대신 실행이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="b72e8-124">사용할 수 있는 인증서 작업 페이지에서 새 인증서 요청 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="b72e8-125">인증서 요청 페이지에서 외부에 지 인증서를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="b72e8-126">지연 또는 즉시 요청 페이지에서 지금 요청을 준비하고 나중에 보냅니다 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="b72e8-127">인증서 요청 파일 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예를 들어, c: \\ cert 외부에 있는 \_ \_ .cer).</span><span class="sxs-lookup"><span data-stu-id="b72e8-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="b72e8-128">대체 인증서 템플릿 지정 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 선택한 인증 기관에 대체 인증서 템플릿 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="b72e8-129">이름 및 보안 설정 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="b72e8-130">이름에 인증서 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="b72e8-131">비트 길이에서 비트 길이(일반적으로 기본값은 2048)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="b72e8-132">인증서의 개인 키를 내보낼 수 있는 것으로 표시 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="b72e8-133">조직 정보 페이지에 조직 및 조직 구성 단위의 이름(예: 사업부 또는 부서)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="b72e8-134">지역 정보 페이지에서 위치 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="b72e8-p106">주체 이름/주체 대체 이름 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다. 추가 주체 대체 이름이 필요한 경우 다음 두 단계에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="b72e8-137">주체 대체 이름 (San)에 대 한 SIP 도메인 설정 페이지에서 sip를 추가 하려면 도메인 확인란을 선택 합니다.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="b72e8-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="b72e8-138">주체 대체 이름 목록에 항목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-138">entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="b72e8-139">추가 주체 대체 이름 구성 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-139">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b72e8-p108">XMPP 프록시가 설치된 경우 기본적으로 도메인 이름(예: contoso.com)이 SAN 항목에 채워집니다. 추가 항목이 필요하면 이 단계에서 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p108">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="b72e8-142">요청 요약 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-142">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="b72e8-143">명령 실행이 완료되면 로그를 보거나 다음을 클릭하여 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-143">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="b72e8-144">인증서 요청 파일 페이지에서 보기를 클릭하여 생성된 CSR(인증서 서명 요청) 파일을 보거나 마침을 클릭하여 인증서 마법사를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-144">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="b72e8-145">요청 파일을 복사하고 공용 인증 기관에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-145">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="b72e8-p109">공용 인증서를 받아 가져오고 할당한 후 에지 서버 서비스를 중지한 다음 다시 시작해야 합니다. 이는 Lync Server 관리 콘솔에서 다음을 입력해서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p109">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="b72e8-148">XMPP 페더레이션을 사용 하도록 DNS를 구성 하려면 외부 DNS: \_ xmpp-server에 다음 SRV 레코드를 추가 합니다. \_ rdp-tcp.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="b72e8-148">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="b72e8-149">SRV 레코드는 포트 값이 5269 인에 지 서버의 액세스에 지 FQDN을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-149">The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="b72e8-150">또한 액세스에 지 서버의 IP 주소를 가리키는 ' A ' 호스트 레코드 (예: xmpp.contoso.com)를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-150">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b72e8-p111">여러 사이트에 에지 풀이 있는 경우 XMPP 페더레이션에 대해 여러 SRV 레코드를 추가하는 것이 좋습니다. 조직 내 모든 에지 풀에 대해 SRV 레코드를 추가하고 이러한 각 SRV 레코드에 서로 다른 우선 순위를 지정합니다. 모든 에지 풀이 실행될 때 XMPP 요청은 우선 순위가 가장 높은 에지 풀에서 처리됩니다. 하지만 해당 에지 풀이 다운된 경우 XMPP 페더레이션 기능을 다시 확보하기 위해 새로운 SRV 레코드를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p111">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="b72e8-154">프런트 엔드에서 Lync Server 관리 셸을 열고 다음을 입력하여 모든 사용자를 사용하도록 설정하기 위해 새로운 외부 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-154">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="b72e8-155">다음을 입력하여 외부 사용자에 대해 XMPP 액세스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-155">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="b72e8-156">XMPP 프록시가 배포 되는에 지 서버에서 명령 프롬프트나 Windows PowerShell™ 명령줄 인터페이스를 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-156">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="b72e8-157">**Netstat – ano** 명령은 네트워크 통계 명령, netstat가 모든 연결 및 수신 대기 포트, 주소 및 포트를 숫자 형식으로 표시 하 고 소유 프로세스 ID가 각 연결과 연결 되도록 하는 매개 변수 **-ano** 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-157">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="b72e8-158">문자는 **|** 다음 command, **findstr**또는 find 문자열에 대 한 파이프를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-158">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="b72e8-159">Findstr에 매개 변수로 전달 되는 번호 5269 및 23456는 findstr이 문자열 5269 및 23456에 대 한 netstat의 출력을 검색 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-159">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="b72e8-160">XMPP가 올바르게 구성 되어 있으면 명령 결과에에 지 서버의 외부 (포트 5269) 및 내부 (포트 23456) 인터페이스를 통해 수신 대기 및 설정 된 연결이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-160">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="b72e8-161">명령이 5269 및 23456에서 설정되었거나 수신 대기 중인 포트를 반환하지 않으면 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-161">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="b72e8-162">XMPP 페더레이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b72e8-162">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="b72e8-163">XMPP 프록시가 실행 중인지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-163">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="b72e8-164">XMPP 프록시 서비스를 실행 중인 에지 서버에 로컬 관리자 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-164">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="b72e8-165">**시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 클릭한 다음 **서비스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-165">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="b72e8-p113">서비스에서 Lync Server XMPP Translating Gateway Proxy를 찾습니다. 이 서비스는 **시작됨** 상태여야 합니다. 시작되지 않았으면 도구 모음에서 **시작** 아이콘을 클릭합니다. 아이콘은 녹색 오른쪽 화살표로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p113">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="b72e8-p114">서비스가 **시작됨**으로 변경되었는지 확인합니다. 성공적으로 시작되었으면 **서비스**를 닫고 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-p114">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="b72e8-172">서비스가 성공적으로 시작되지 않았으면 관리 도구에서 이벤트 뷰어를 열고 **응용 프로그램 및 서비스 로그** 아래의 **Lync Server** 부분에서 오류 및 경로를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-172">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="b72e8-173">**Lync Server XMPP Translating Gateway** 서비스가 실행되면 이전에 사용한 netstat 명령을 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-173">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="b72e8-174">설정 또는 수신 대기 세션이 표시 되지 않는 경우 토폴로지 작성기에서 **Xmpp 페더레이션 경로가** 올바르게 구성 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b72e8-174">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="b72e8-175">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-175">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="b72e8-176">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-176">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="b72e8-177">토폴로지 작성기에서 XMPP 페더레이션 경로의 사이트를 선택 하 고 검토를 통해 **Xmpp** 페더레이션에 대 한 **사이트 페더레이션 경로** 지정이 선택한 xmpp 페더레이션 경로 할당으로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-177">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="b72e8-178">경로 지정이 잘못되었거나 설정되지 않았으면 사이트를 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-178">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="b72e8-179">XMPP 페더레이션 확인란을 선택 하 고 올바른에 지 서버 또는에 지 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-179">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="b72e8-180">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-180">Publish the topology.</span></span> <span data-ttu-id="b72e8-181">자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b72e8-181">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b72e8-182">필수는 아니지만 일반적으로 필요 하지는 않지만에 지 서버를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-182">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="b72e8-183">이전에 사용 된 netstat 프로세스를 사용 하 여 이제에 지 서버가 포트 5269 및 포트 23456의 세션을 수신 대기 중이거나 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-183">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="b72e8-184">여전히 예상한 세션이 표시되지 않으면 이벤트 뷰어에서 통신 관련 문제가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b72e8-184">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b72e8-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b72e8-185">See Also</span></span>


[<span data-ttu-id="b72e8-186">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="b72e8-186">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="b72e8-187">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="b72e8-187">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

