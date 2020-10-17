---
title: 'Lync Server 2013: 새 웹 서비스 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44e86ad1d587bd3dddb921cdeea3ed2a65ea26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515575"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6ef48-102">Lync Server 2013에서 새 웹 서비스 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="6ef48-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ef48-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6ef48-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6ef48-104">**웹 서비스** 페이지를 사용 하 여 Lync Server 2013 관련 웹 서버 및 웹 서비스에 액세스 하기 위한 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="6ef48-105">다음 단계에 따라 새 웹 서비스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="6ef48-106">새 웹 서비스 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6ef48-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="6ef48-107">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6ef48-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ef48-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ef48-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ef48-110">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="6ef48-111">**웹 서비스** 페이지에서 **새로 만들기**를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6ef48-p102">사이트에 대해 웹 서비스를 구성하려면 **사이트 구성**을 클릭합니다. **사이트 선택**에서 웹 서비스 정책을 적용할 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-p102">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="6ef48-p103">풀에 대해 웹 서비스를 구성하려면 **풀 구성**을 클릭합니다. **서비스 선택**에서 웹 서비스 정책을 적용할 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-p103">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="6ef48-116">**새 웹 서비스 설정**의 **통합 Windows 인증**에서 **협상**, **통합 Windows 인증** 또는 **없음** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="6ef48-117">환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="6ef48-118">**PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="6ef48-119">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="6ef48-120">**인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다</span><span class="sxs-lookup"><span data-stu-id="6ef48-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="6ef48-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef48-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

