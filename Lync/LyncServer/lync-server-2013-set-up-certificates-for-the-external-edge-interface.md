---
title: 'Lync Server 2013: 외부에 지 인터페이스에 대 한 인증서 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2bad8f01e773d50f8d722ddbbf4be0757cb31d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="5aff9-102">Lync Server 2013의 외부에 지 인터페이스에 대 한 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="5aff9-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5aff9-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5aff9-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5aff9-104">인증서 마법사를 실행할 때는 사용할 인증서 템플릿의 유형에 대해 적절한 권한이 할당된 그룹 구성원인 계정을 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="5aff9-105">기본적으로 Lync Server 인증서 요청은 웹 서버 인증서 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="5aff9-106">RTCUniversalServerAdmins 그룹 구성원인 계정을 사용하여 이 템플릿을 사용하는 인증서를 요청하는 경우 이 그룹에 해당 템플릿을 사용하는 데 필요한 등록 권한이 할당되었는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5aff9-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="5aff9-107">각 에지 서버에는 경계 네트워크와 인터넷 간의 인터페이스에 대한 공용 인증서가 필요하며, 인증서의 주체 대체 이름에 액세스 에지 서비스 및 웹 회의 에지 서비스 FQDN(정규화된 도메인 이름)의 외부 이름이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="5aff9-108">이 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5aff9-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="5aff9-109">통합 통신 인증서에 대 한 특정 요구 사항을 준수 하 고 Microsoft와 제휴 하 여 Lync Server 2013 인증서 마법사와 함께 사용할 수 있도록 하는 인증서를 제공 하는 공용 Ca (인증 기관) 목록은 Microsoft 기술 자료 문서 929395, "Exchange Server 및 통신 서버용 통합 커뮤니케이션 인증서 파트너"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="5aff9-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="5aff9-110">외부 인터페이스에 대한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="5aff9-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="5aff9-111">사이트의 외부 에지 인터페이스에 대한 인증서를 설정하려면 이 섹션의 절차를 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="5aff9-112">에지 서버의 외부 인터페이스에 대한 인증서 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="5aff9-113">공용 CA에 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="5aff9-114">각 에지 서버의 외부 인터페이스에 대한 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="5aff9-115">각 에지 서버의 외부 인터페이스에 대한 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="5aff9-p102">배포에 여러 에지 서버가 포함된 경우 해당 개인 키와 함께 인증서를 내보낸 다음 다른 에지 서버에 복사합니다. 그런 다음 각 에지 서버에 대해 앞서 설명한 대로 인증서를 가져와 할당합니다. 각 에지 서버에 대해 이 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="5aff9-p103">공용 인증서를 공용 CA(인증 기관)에 직접 요청(예: 공용 CA 웹 사이트에서)할 수 있습니다. 이 섹션의 절차에서는 대부분의 인증서 작업에 인증서 마법사를 사용합니다. 공용 CA에 직접 인증서를 요청하려면 인증서 요청, 전송 및 가져오기와 인증서 체인 가져오기에 적절하게 각 절차를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="5aff9-p104">외부 CA에 인증서를 요청할 때는 해당 CA에 인증서를 요청할 권한이 있는 자격 증명을 제공해야 합니다. 각 CA에는 인증서 요청, 발급, 관리 또는 읽기가 허용되는 자격 증명(즉, 특정 사용자 및 그룹 이름)을 정의한 보안 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="5aff9-124">인증서 MMC(Microsoft Management Console)를 사용하여 인증서 체인 및 인증서를 가져오려면 해당 인증서 체인 및 인증서를 컴퓨터의 인증서 저장소로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="5aff9-125">사용자 또는 서비스 인증서 저장소로 가져오는 경우 Lync Server 2013 인증서 마법사에서 해당 인증서를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="5aff9-126">에지 서버의 외부 인터페이스에 대한 인증서 요청을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="5aff9-127">에지 서버의 배포 마법사에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aff9-128">조직에서 AOL과의 공용 IM(인스턴트 메시징) 연결을 지원하려는 경우에는 Lync Server 배포 마법사를 사용하여 인증서를 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="5aff9-129">대신, 이 항목의 뒷부분에 나오는 "AOL과의 공용 IM 연결을 지원하도록 에지 서버의 외부 인터페이스에 대한 인증서 요청을 만들려면" 절차를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="5aff9-130">풀의 한 위치에 여러 개의에 지 서버가 있는 경우에 지 서버 중 하나에서 Lync Server 2013 인증서 마법사를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="5aff9-131">**사용할 수 있는 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="5aff9-132">**인증서 요청** 페이지에서 **외부 에지 인증서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="5aff9-133">**지연 또는 즉시 요청** 페이지에서 **지금 요청을 준비하고 나중에 보냅니다** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="5aff9-134">**인증서 요청 파일** 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예를 들어, c:\\cert\_외부\_에 있는 .cer).</span><span class="sxs-lookup"><span data-stu-id="5aff9-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="5aff9-135">**대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 **선택한 인증 기관에 대체 인증서 템플릿 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="5aff9-136">**이름 및 보안 설정** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="5aff9-137">**대화명**에 인증서 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="5aff9-138">**비트 길이**에서 비트 길이(일반적으로 기본값은 **2048**)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="5aff9-139">**인증서의 개인 키를 내보낼 수 있는 것으로 표시** 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="5aff9-140">**조직 정보** 페이지에 조직 및 조직 구성 단위의 이름(예: 사업부 또는 부서)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="5aff9-141">**지역 정보** 페이지에서 위치 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="5aff9-p107">**주체 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다. 추가 주체 대체 이름이 필요한 경우 다음 두 단계에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="5aff9-144">**주체 대체 이름 (san)에 대 한 Sip 도메인 설정** 페이지에서 sip를 추가 하려면 도메인 확인란을 선택 합니다. \<주체\> 대체 이름 목록에 microsoft.rtc.management.xds.sipdomain object 항목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="5aff9-145">**추가 주체 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="5aff9-146">**요청 요약** 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="5aff9-147">명령 실행이 완료되면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="5aff9-148">인증서 요청 로그를 보려면 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="5aff9-149">인증서 요청을 완료하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="5aff9-150">**인증서 요청 파일** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="5aff9-151">생성된 CSR(인증서 서명 요청) 파일을 보려면 **보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="5aff9-152">마법사를 닫으려면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="5aff9-153">공용 CA에 제출할 수 있는 위치로 출력 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="5aff9-154">AOL과의 공용 IM 연결을 지원하도록 에지 서버의 외부 인터페이스에 대한 인증서 요청을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="5aff9-155">CA에서 필요한 템플릿을 사용할 수 있는 경우에 지 서버에서 다음 Windows PowerShell cmdlet을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="5aff9-156">Lync Server 2013에 제공 되는 템플릿의 기본 인증서 이름은 웹 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="5aff9-157">기본 서식 파일과 \<다른 서식\> 파일을 사용 해야 하는 경우에만 서식 파일 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aff9-158">조직에서 AOL과의 공용 IM 연결을 지원 하려면 인증서 마법사 대신 Windows PowerShell을 사용 하 여 액세스에 지 서비스의 외부에 지에 대해 인증서를 할당 하도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="5aff9-159">인증서 마법사가 인증서를 요청 하는 데 사용 하는 Lync Server 2013 웹 서버 템플릿은 클라이언트 EKU 구성을 지원 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="5aff9-160">Windows PowerShell을 사용 하 여 인증서를 만들기 전에 CA 관리자가 클라이언트 EKU를 지 원하는 새 템플릿을 만들고 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="5aff9-161">공용 인증 기관에 요청을 제출하려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="5aff9-162">출력 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-162">Open the output file.</span></span>

2.  <span data-ttu-id="5aff9-163">CSR(인증서 서명 요청) 내용을 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="5aff9-164">메시지가 나타나면 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="5aff9-165">**Microsoft** - 서버 플랫폼</span><span class="sxs-lookup"><span data-stu-id="5aff9-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="5aff9-166">**IIS** - 버전</span><span class="sxs-lookup"><span data-stu-id="5aff9-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="5aff9-167">**웹 서버** - 사용 유형</span><span class="sxs-lookup"><span data-stu-id="5aff9-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="5aff9-168">**PKCS7** - 응답 형식</span><span class="sxs-lookup"><span data-stu-id="5aff9-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="5aff9-169">공용 CA에서 사용자 정보를 확인하면 인증서에 필요한 텍스트가 포함된 전자 메일 메시지가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="5aff9-170">전자 메일 메시지의 텍스트를 복사하여 로컬 컴퓨터의 텍스트 파일(.txt)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="5aff9-171">에지 서버의 외부 인터페이스에 대한 인증서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="5aff9-172">인증서 요청을 만든 에지 서버에 Administrators 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="5aff9-173">배포 마법사의 **에지 서버 배포** 페이지에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="5aff9-174">**사용 가능한 인증서 작업** 페이지에서 **.p7b, pfx 또는 .cer 파일에서 인증서 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="5aff9-p110">**인증서 가져오기** 페이지에서 **찾아보기**를 클릭하여 사용자가 에지 서버의 외부 인터페이스에 대해 요청한 인증서를 찾아서 선택합니다. 또는 전체 경로 및 파일 이름을 입력할 수도 있습니다. 인증서에 개인 키가 포함된 경우 **인증서 파일에 인증서의 개인 키가 있음**을 선택한 후 개인 키에 대한 암호를 입력합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="5aff9-178">**인증서 가져오기 요약** 페이지에서 요약 내용을 검토한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="5aff9-179">**명령 실행**에서 가져오기 결과를 검토한 후 필요에 따라 **로그 보기**를 클릭하여 자세한 내용을 확인하고 인증서 가져오기를 완료하려면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="5aff9-p111">에지 서버 풀을 구성할 경우 이 항목의 뒷부분에 있는 "풀의 에지 서버에 대해 개인 키를 사용하여 인증서를 내보내려면" 절차에 설명된 대로 해당 개인 키를 사용하여 인증서를 내보냅니다. 내보낸 인증서 파일을 다른 에지 서버에 복사하고 각 에지 서버의 컴퓨터 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="5aff9-182">풀의 에지 서버에 대해 개인 키를 사용하여 인증서를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="5aff9-183">인증서를 가져온 것과 동일한 에지 서버에 Administrators 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="5aff9-184">**시작**, **실행**을 차례로 클릭하고 **mmc**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="5aff9-185">MMC(Microsoft Management Console) 콘솔에서 **파일**을 클릭한 후 **스냅인 추가/제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="5aff9-186">**스냅인 추가/제거**에서 **인증서**를 클릭한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="5aff9-187">**인증서** 대화 상자에서 **컴퓨터 계정**을 선택한 후 **다음**을 클릭하고, **컴퓨터 선택**에서 **로컬 컴퓨터: (이 콘솔이 실행 중인 컴퓨터)** 를 선택하고, **마침**을 클릭한 후 **확인**을 클릭하여 MMC 콘솔의 구성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="5aff9-188">**인증서(로컬 컴퓨터)** 를 두 번 클릭하여 인증서 저장소를 확장하고, **개인**을 두 번 클릭한 후 **인증서**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5aff9-p112">인증서 개인 저장소에 로컬 컴퓨터에 대한 인증서가 없으면 가져온 인증서와 연관된 개인 키도 없습니다. 요청 및 가져오기 단계를 검토하십시오. 문제가 계속되면 인증 기관 관리자 또는 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="5aff9-192">**로컬 컴퓨터의 인증서 개인 저장소**에서 내보내려는 인증서를 마우스 오른쪽 단추로 클릭하고, **모든 작업**을 클릭한 후 **내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="5aff9-193">인증서 내보내기 마법사에서 **다음**을 클릭하고 **예, 개인 키를 내보냅니다.** 를 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aff9-p113"><STRONG>예, 개인 키를 내보냅니다.</STRONG> 선택 항목을 사용할 수 없으면 이 인증서와 연관된 개인 키가 내보내기용으로 표시되지 않은 것입니다. 인증서를 다시 요청하여 내보내기를 계속하기 전에 개인 키의 내보내기가 허용되도록 인증서가 표시되었는지 확인해야 합니다. 인증 기관 관리자 또는 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="5aff9-197">파일 형식 내보내기 대화 상자에서 **개인 정보 교환-PKCS\#12 (을 클릭 합니다. PFX)** 를 선택한 후 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="5aff9-198">가능하면 인증 경로에 있는 인증서를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="5aff9-199">모든 확장된 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="5aff9-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="5aff9-p114">에지 서버에서 인증서를 내보낼 때는 <STRONG>내보내기가 완료되면 개인 키 삭제</STRONG>를 선택하지 마십시오. 이 옵션을 선택하면 인증서 및 개인 키를 이 에지 서버로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="5aff9-202">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-202">Click **Next**.</span></span>

11. <span data-ttu-id="5aff9-203">개인 키에 대한 암호를 입력하고, 확인을 위해 암호를 다시 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="5aff9-p115">파일 확장명 .pfx를 사용하여 내보낸 인증서에 대한 경로 및 파일 이름을 입력합니다. 경로는 풀의 다른 모든 에지 서버에서 액세스할 수 있거나 USB 플래시 드라이브와 같은 이동식 미디어를 사용하여 전송할 수 있어야 합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="5aff9-207">**인증서 내보내기 마법사 완료**에서 요약 내용을 검토한 후 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="5aff9-208">내보내기 성공 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="5aff9-209">이 항목의 앞부분에 있는 "에지 서버의 외부 인터페이스에 대해 인증서를 가져오려면" 절차에 설명된 단계에 따라 내보낸 인증서 파일을 다른 에지 서버로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="5aff9-210">에지 서버의 외부 인터페이스에 대한 인증서를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="5aff9-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="5aff9-211">각 에지 서버의 배포 마법사에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="5aff9-212">**사용할 수 있는 인증서 작업** 페이지에서 **기존 인증서 할당**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="5aff9-213">**인증서 할당** 페이지에서 **외부 에지 인증서**를 클릭하고 **고급 인증서 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="5aff9-214">**고급 인증서 사용** 페이지에서 모든 사용에 대해 인증서를 할당할 확인란을 모두 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="5aff9-215">**인증서 저장소** 페이지에서 에지 서버의 외부 인터페이스에 대해 요청하고 가져온 공용 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aff9-216">요청하고 가져온 인증서가 목록에 없는 경우 인증서의 주체 이름 및 주체 대체 이름이 인증서에 대한 모든 요구 사항을 충족하는지 확인하고, 인증서 및 인증서 체인을 이전 절차를 사용하는 대신 수동으로 가져온 경우 해당 인증서가 올바른 인증서 저장소(사용자 또는 서비스 인증서가 아니라 컴퓨터 인증서 저장소)에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="5aff9-217">**인증서 지정 요약** 페이지에서 설정을 검토하고 **다음**을 클릭하여 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="5aff9-218">마법사 완료 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="5aff9-219">이 절차를 사용하여 에지 인증서를 할당한 후에는 각 서버에서 인증서 스냅인을 열고 **인증서(로컬 컴퓨터)**, **개인**을 차례로 확장한 다음 **인증서**를 클릭하고 세부 정보 창에서 인증서가 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="5aff9-220">배포에 여러 에지 서버가 포함된 경우 각 에지 서버에 대해 이 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5aff9-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

