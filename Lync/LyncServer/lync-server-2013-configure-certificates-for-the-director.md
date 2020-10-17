---
title: 'Lync Server 2013: 디렉터에 대 한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e257d62e761b33dad737f9d37da5f561703183ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521055"
---
# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="430f7-102">Lync Server 2013에서 디렉터에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="430f7-102">Configure certificates for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="430f7-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="430f7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="430f7-104">인증서 마법사를 실행할 때는 사용할 인증서 템플릿의 유형에 대해 적절한 권한이 할당된 그룹 구성원인 계정을 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="430f7-105">기본적으로 Lync Server 2013 인증서 요청은 웹 서버 인증서 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="430f7-106">RTCUniversalServerAdmins 그룹 구성원인 계정을 사용하여 이 템플릿을 사용하는 인증서를 요청하는 경우 이 그룹에 해당 템플릿을 사용하는 데 필요한 등록 권한이 할당되었는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="430f7-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="430f7-107">각 디렉터에는 기본 인증서, 웹 내부 인증서 및 웹 외부 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="430f7-108">디렉터에 대 한 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="430f7-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="430f7-109">다음 절차에 따라 디렉터 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="430f7-110">각 디렉터에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="430f7-111">이 절차의 단계에서는 조직 및 오프 라인 요청 처리를 통해 배포 된 내부 엔터프라이즈 루트 CA (인증 기관)에서 인증서를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="430f7-112">외부 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 지원 팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="430f7-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="430f7-113">디렉터 또는 디렉터 풀에 대 한 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="430f7-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="430f7-114">Lync Server 배포 마법사의 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="430f7-115">**인증서 마법사** 페이지에서 **요청**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="430f7-116">**인증서 요청** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="430f7-117">**지연 또는 즉시 요청** 페이지에서 기본 **요청을 온라인 인증 기관에 즉시 보내기** 옵션을 수락 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="430f7-118">**CA (인증 기관) 선택** 페이지에서 사용할 내부 Windows 인증 기관을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="430f7-119">**인증 기관 계정** 페이지에서 로그온 하는 데 사용 하는 계정에 인증서 요청 권한이 없는 경우 사용할 대체 자격 증명을 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="430f7-120">**대체 인증서 템플릿 지정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="430f7-121">**이름 및 보안 설정** 페이지에서 **대화명**을 지정 하 고, 2048 비트 키 길이를 적용 하 고, **다음**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="430f7-122">**조직 정보** 페이지에서 선택적으로 조직 정보를 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="430f7-123">**지역 정보** 페이지에서 선택적으로 지역 정보를 지정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="430f7-124">**주체 이름/주체 대체 이름** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="430f7-125">주체 대체 이름 목록에는 디렉터를 설치할 컴퓨터의 이름 (디렉터가 하나인 경우) 또는 디렉터 풀 이름이 있고 조직에 대해 구성 된 단순 URL 이름이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="430f7-126">**주체 대체 이름 (san)에 대 한 SIP 도메인 설정** 페이지에서 디렉터가 처리할 모든 도메인에 대해 **구성 된 SIP 도메인** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="430f7-127">**추가 주체 대체 이름 구성** 페이지에서 필요한 주체 대체 이름을 추가 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="430f7-128">**인증서 요청 요약** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="430f7-129">**명령** 실행 중 페이지에서, 해당 명령이 완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="430f7-130">**온라인 인증서 요청 상태** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="430f7-131">**인증서 지정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="430f7-132">인증서를 보려면 목록에서 인증서를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="430f7-133">**인증서 지정 요약** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="430f7-134">명령을 실행 한 후 **명령 실행** 페이지에서 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="430f7-135">**인증서 마법사** 페이지에서 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="430f7-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

