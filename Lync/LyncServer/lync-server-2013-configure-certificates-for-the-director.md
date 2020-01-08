---
title: 'Lync Server 2013: 디렉터에 대한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="f06c1-102">Lync Server 2013에서 디렉터에 대한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="f06c1-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f06c1-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f06c1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f06c1-104">인증서 마법사를 실행할 때 사용할 인증서 서식 파일 형식에 대 한 적절 한 사용 권한이 할당 된 그룹의 구성원 인 계정을 사용 하 여 로그인 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="f06c1-105">기본적으로 Lync Server 2013 인증서 요청에서는 웹 서버 인증서 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="f06c1-106">RTCUniversalServerAdmins 그룹의 구성원 인 계정을 사용 하 여이 서식 파일을 사용 하 여 인증서를 요청 하는 경우 해당 서식 파일을 사용 하는 데 필요한 등록 권한이 그룹에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="f06c1-107">각 디렉터에는 기본 인증서, 웹 내부 인증서, 웹 외부 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="f06c1-108">디렉터에 대 한 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f06c1-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="f06c1-109">다음 절차를 사용 하 여 디렉터 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="f06c1-110">각 디렉터에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="f06c1-111">이 절차의 단계에서는 조직에서 배포 하 고 오프 라인 요청 처리를 사용 하 여 내부 엔터프라이즈 루트 CA (인증 기관)에서 인증서를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="f06c1-112">외부 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 지원 팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f06c1-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="f06c1-113">디렉터 또는 디렉터 풀에 대 한 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="f06c1-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="f06c1-114">Lync Server 배포 마법사의 **3 단계: 요청, 인증서 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="f06c1-115">**인증서 마법사** 페이지에서 **요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="f06c1-116">**인증서 요청** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="f06c1-117">**지연 또는 즉시 요청** 페이지에서 기본 **요청을 온라인 인증 기관에 보내기** 옵션을 적용 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="f06c1-118">**CA (인증 기관) 선택** 페이지에서 사용 하려는 내부 Windows 인증 기관을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="f06c1-119">로그인 한 계정에 인증서를 요청할 수 있는 권한이 없는 경우 **인증 기관 계정** 페이지에서 사용할 대체 자격 증명을 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="f06c1-120">**대체 인증서 템플릿 지정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="f06c1-121">**이름 및 보안 설정** 페이지에서 **이름을**지정 하 고 2048 비트 키 길이를 적용 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="f06c1-122">**조직 정보** 페이지에서 필요에 따라 조직 정보를 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="f06c1-123">**지리적 정보** 페이지에서 필요에 따라 지리 정보를 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="f06c1-124">**주체 이름/제목 대체 이름** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f06c1-125">주체 대체 이름 목록에는 디렉터를 설치 하는 컴퓨터의 이름 (단일 디렉터) 또는 디렉터 풀 이름과 조직에 대해 구성 된 간단한 URL 이름이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="f06c1-126">**SIP 도메인 설정의 san (주체 대체 이름** ) 페이지에서 디렉터를 처리할 모든 도메인에 대해 **구성 된 sip 도메인** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="f06c1-127">**추가 주체 이름 구성** 페이지에서 필요한 추가 제목 대체 이름을 추가 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="f06c1-128">**인증서 요청 요약** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="f06c1-129">**명령** 실행 페이지에서 명령이 실행을 완료 한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="f06c1-130">**온라인 인증서 요청 상태** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="f06c1-131">**인증서 할당** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f06c1-132">인증서를 확인 하려면 목록에서 인증서를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="f06c1-133">**인증서 할당 요약** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="f06c1-134">**명령 실행 페이지에서** 명령이 완료 된 후 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="f06c1-135">**인증서 마법사** 페이지에서 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06c1-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

