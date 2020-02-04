---
title: 'Lync Server 2013: 자동 검색을 위한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="2eef7-102">Lync Server 2013에서 자동 검색을 위한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="2eef7-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eef7-103">_**마지막으로 수정한 주제:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="2eef7-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="2eef7-104">디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 인증서는 Lync 클라이언트와의 보안 연결을 지원 하기 위해 추가 주제 대체 이름 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eef7-105"><STRONG>Get-CsCertificate</STRONG> cmdlet을 사용 하 여 현재 할당 된 인증서에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="2eef7-106">그러나 기본 보기에서는 인증서의 속성을 자르고 SubjectAlternativeNames 속성에 모든 값이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="2eef7-107"><STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate 및 <STRONG>Set CsCertificate</STRONG> cmdlet을 사용 하 여 일부 정보를 보고 인증서를 요청 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="2eef7-108">그러나 현재 인증서의 SAN (주체 대체 이름) 속성에 대해 잘 모르는 경우에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="2eef7-109">인증서 및 모든 속성 구성원을 보려면 <EM>MMC (Microsoft Management Console)</EM> 에서 인증서 스냅인을 사용 하거나 Lync Server 배포 마법사를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="2eef7-110">Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="2eef7-111">Lync Server 관리 셸과 <EM>MMC (Microsoft Management Console)</EM> 를 사용 하 여 인증서를 보거나 지정 하는 절차는 다음 절차에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="2eef7-112">Lync Server 배포 마법사를 사용 하려면 옵션 디렉터 또는 디렉터 풀을 배포한 경우 여기에서 세부 정보를 참조 하세요. <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013에서 디렉터에 대 한 인증서를 구성</A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="2eef7-113">프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 자세한 내용은 다음을 참조 하세요. <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013에서 서버의 인증서를 구성</A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="2eef7-114">이 절차의 초기 단계는 현재 인증서가 재생 되는 역할을 표시 하는 준비 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="2eef7-115">기본적으로 인증서에는 lyncdiscover이 없습니다. &lt;sipdomain&gt; 또는 lyncdiscoverinternal. &lt;이전에 모바일&gt; 서비스를 설치 하지 않았거나 인증서를 미리 준비한 경우가 아니면 내부 도메인 이름 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="2eef7-116">이 절차에서는 예제 SIP 도메인 이름 ' contoso.com ' 및 내부 도메인 이름 ' contoso.net '의 예를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="2eef7-117">Lync Server 2013 및 Lync Server 2010의 기본 인증서 구성은 기본 (웹 서비스를 제외한 모든 용도), Webservice외부 Nal 및 Web서비스 내부에 대 한 단일 인증서 (' Default ')를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="2eef7-118">선택적 구성은 각 용도에 대해 별도의 인증서를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="2eef7-119">인증서는 Lync Server 관리 셸 및 Windows PowerShell cmdlet을 사용 하거나 Lync Server 배포 마법사의 인증서 마법사를 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="2eef7-120">Lync Server Management Shell을 사용 하 여 새 주체의 대체 이름을 사용 하 여 인증서를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="2eef7-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="2eef7-121">로컬 관리자 권한 및 사용 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="2eef7-122">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2eef7-123">서버에 지정 된 인증서 및 사용 유형에 대 한 자세한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="2eef7-124">업데이트 된 인증서를 할당 하려면 다음 단계에서이 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="2eef7-125">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="2eef7-126">이전 단계의 출력을 확인 하 여 단일 인증서가 여러 용도로 지정 되었는지 또는 각 용도에 대해 다른 인증서가 지정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="2eef7-127">사용 매개 변수를 확인 하 여 인증서 사용 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="2eef7-128">표시 된 인증서의 손도장 매개 변수를 비교 하 여 동일한 인증서가 여러 용도로 사용 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="2eef7-129">인증서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-129">Update the certificate.</span></span> <span data-ttu-id="2eef7-130">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="2eef7-131">예를 들어 CsCertificate cmdlet이 기본적으로 사용 하는 인증서를 표시 하는 경우, 그 밖의 Web서비스 사용, 그리고 Webservice외부를 사용 하는 다른 경우와 모두 동일한 손도장 (Thumbprint **)** 값이 동일한 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="2eef7-132">**중요:**</span><span class="sxs-lookup"><span data-stu-id="2eef7-132">**Important:**</span></span>
    
    <span data-ttu-id="2eef7-133">각 사용에 대해 별도의 인증서가 할당 되는 경우 (손도장 값은 각 인증서에 대해 다르므로) **CsCertificate** cmdlet을 여러 형식으로 실행 하지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="2eef7-134">이 경우 각 사용에 대해 **Set-CsCertificate** cmdlet을 개별적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="2eef7-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="2eef7-136">인증서를 보려면 **시작**을 클릭 하 고 **실행 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="2eef7-137">MMC를 입력 하 여 Microsoft Management Console을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="2eef7-138">MMC 메뉴에서 **파일**을 선택 하 고, **스냅인 추가/제거**를 선택 하 고, 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="2eef7-139">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-139">Click **Add**.</span></span> <span data-ttu-id="2eef7-140">메시지가 표시 되 면 **컴퓨터 계정을**선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="2eef7-141">인증서가이 컴퓨터에 있는 경우 **로컬 컴퓨터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="2eef7-142">인증서가 다른 컴퓨터에 있는 경우 **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름을 입력 하거나 **찾아보기를** 클릭 **하 여 선택할 개체 이름을 입력 하**고 컴퓨터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="2eef7-143">**이름 확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-143">Click **Check Names**.</span></span> <span data-ttu-id="2eef7-144">컴퓨터의 이름이 확인 되 면 밑줄로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="2eef7-145">**확인**을 클릭 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="2eef7-146">**확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2eef7-147">콘솔에 인증서가 표시 되지 않으면 사용자 또는 서비스를 선택 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="2eef7-148">컴퓨터를 선택 해야 하며, probper 인증서를 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="2eef7-149">인증서의 속성을 보려면 **인증서**를 확장 하 고, **개인**을 확장 하 고, **인증서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="2eef7-150">보려는 인증서를 선택 하 고, 인증서를 마우스 오른쪽 단추로 클릭 하 고 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="2eef7-151">**인증서** 보기에서 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="2eef7-152">여기에서 **주체** 를 선택 하 고 지정 된 제목 이름과 연결 된 속성이 표시 되도록 하 여 인증서 주체 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="2eef7-153">지정 된 제목 대체 이름을 보려면 **제목 대체 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="2eef7-154">지정 된 모든 제목 대체 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="2eef7-155">속성에 있는 주체 대체 이름은 기본적으로 **DNS 이름** 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="2eef7-156">DNS 호스트 (A 또는 IPv6 AAAA) 레코드에 표시 되는 것으로 정규화 된 도메인 이름이 되어야 하는 다음 구성원이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="2eef7-157">이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름</span><span class="sxs-lookup"><span data-stu-id="2eef7-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="2eef7-158">인증서가 할당 된 서버 이름</span><span class="sxs-lookup"><span data-stu-id="2eef7-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="2eef7-159">간단한 URL 레코드, 일반적으로 모임 및 전화 접속</span><span class="sxs-lookup"><span data-stu-id="2eef7-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="2eef7-160">웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의 된 웹 서비스 선택 항목을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="2eef7-161">이미 할당 된 경우 lyncdiscover. \<sipdomain\> 및 lyncdiscoverinternal. \<레코드\> 를 sipdomain.</span><span class="sxs-lookup"><span data-stu-id="2eef7-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="2eef7-162">마지막 항목은 사용자가 가장 관심을 가지 며, lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="2eef7-163">이 정보가 있으면 인증서 보기와 MMC를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="2eef7-164">자동 검색 서비스 인 경우 lyncdiscover를 의미 합니다. \>도메인 이름\> 및 lyncdiscoverinternal. \<도메인 이름\> (외부 또는 내부 인증서 인지 여부) 제목 대체 이름이 없고 기본 인 Web서비스 내부 및 webserviceexternal 형식에 대해 단일 기본 인증서를 사용 하 고 있는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="2eef7-165">Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2eef7-166">SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="2eef7-167">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="2eef7-168">DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="2eef7-169">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="2eef7-170">인증서를 할당 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="2eef7-171">여기서 "지문"은 새로 발급 된 인증서에 대해 표시 되는 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="2eef7-172">기본, Web서비스 내부 및 Webservice외부 이름에 별도의 인증서를 사용 하는 경우 내부 자동 검색 주체의 대체 이름이 없는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="2eef7-173">Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2eef7-174">SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="2eef7-175">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="2eef7-176">DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 적절 한 접두사를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="2eef7-177">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="2eef7-178">외부 자동 검색 주체의 대체 이름이 없는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2eef7-179">SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="2eef7-180">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="2eef7-181">DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 적절 한 접두사를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="2eef7-182">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="2eef7-183">개별 인증서 종류를 할당 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="2eef7-184">여기서 "지문"은 새로 발급 된 개별 인증서에 대해 표시 되는 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="2eef7-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

