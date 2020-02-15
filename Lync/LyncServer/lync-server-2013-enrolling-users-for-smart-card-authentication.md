---
title: 'Lync Server 2013: 스마트 카드 인증용 사용자 등록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1d60a29eff876ef362d15c90e2615fd70bc8774
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41993813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="511d2-102">Lync Server 2013에서 스마트 카드 인증을 위한 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="511d2-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="511d2-103">_**마지막으로 수정 된 항목:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="511d2-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="511d2-104">스마트 카드 인증용으로 사용자를 등록 하는 방법에는 일반적으로 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="511d2-105">보다 쉬운 방법은 사용자가 웹 등록을 사용 하 여 직접 스마트 카드 인증을 등록 하도록 하는 반면, 복잡 한 방법은 등록 에이전트를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="511d2-106">이 항목에서는 스마트 카드 인증서의 자체 등록에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="511d2-107">사용자를 대신 하 여 등록 에이전트로 등록 하는 방법에 대 한 자세한 내용은 다른 사용자 대신 인증서 등록을 참조 하십시오 [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="511d2-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="511d2-108">스마트 카드 인증을 위해 사용자를 등록 하려면</span><span class="sxs-lookup"><span data-stu-id="511d2-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="511d2-109">Lync 사용 가능 사용자의 자격 증명을 사용 하 여 Windows 8 워크스테이션에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="511d2-110">Internet Explorer를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="511d2-111">**인증 기관 웹 등록** 페이지로 이동 합니다 (예:) https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="511d2-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="511d2-112">Internet Explorer 10을 사용 하는 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="511d2-113">**시작** 페이지에서 **인증서 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="511d2-114">그런 다음 **고급 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="511d2-115">**이 CA에 요청을 만들어 제출 합니다를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="511d2-116">**인증서 템플릿** 섹션 아래의 **스마트 카드 사용자** 를 선택 하 고 다음 값을 사용 하 여 고급 인증서 요청을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="511d2-117">**키 옵션** 에서 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="511d2-118">**새 키 집합 만들기** 라디오 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="511d2-119">**CSP**의 경우 **Microsoft 기본 스마트 카드 암호화 공급자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="511d2-120">**키 사용**에 대해 **Exchange** 를 선택 합니다 (사용 가능한 유일한 옵션).</span><span class="sxs-lookup"><span data-stu-id="511d2-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="511d2-121">**키 크기**에 **2048** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="511d2-122">**자동 키 컨테이너 이름이** 선택 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="511d2-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="511d2-123">다른 확인란은 선택 하지 않은 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="511d2-124">**추가 옵션** 에서 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="511d2-125">**요청 형식** 에 대해 **CMC**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="511d2-126">**해시 알고리즘** 의 경우 **sha1**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="511d2-127">**이름** 으로 **Smardcard 인증서**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="511d2-128">실제 스마트 카드 판독기를 사용 하는 경우 장치에 스마트 카드로 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="511d2-129">**제출을** 클릭 하 여 인증서 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="511d2-130">메시지가 나타나면 가상 스마트 카드를 만드는 데 사용 된 PIN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="511d2-131">기본 가상 스마트 카드 PIN 값은 ' 12345678 '입니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="511d2-132">인증서가 발급 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="511d2-133">"이 웹 브라우저가 인증서 요청 생성을 지원 하지 않습니다." 라는 오류로 인해 인증서 요청이 실패 하면 문제를 해결할 수 있는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="511d2-134">Internet Explorer에서 호환성 보기 사용</span><span class="sxs-lookup"><span data-stu-id="511d2-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="511d2-135">Internet Explorer에서 인트라넷 설정 켜기 옵션을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="511d2-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="511d2-136">Internet Explorer 옵션 메뉴의 보안 탭에 있는 모든 영역을 기본 수준으로 다시 설정 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="511d2-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

