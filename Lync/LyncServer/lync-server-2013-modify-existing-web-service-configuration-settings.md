---
title: 'Lync Server 2013: 기존 웹 서비스 구성 설정 수정'
description: 'Lync Server 2013: 기존 웹 서비스 구성 설정을 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455ddf60d171fe584115d646b16f63595285a906
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566994"
---
# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e77a7-103">Lync Server 2013에서 기존 웹 서비스 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="e77a7-103">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e77a7-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e77a7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e77a7-105">**웹 서비스** 페이지를 사용 하 여 Lync Server 2013 관련 웹 서버 및 웹 서비스에 액세스 하기 위한 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="e77a7-106">다음 단계에 따라 기존의 웹 서비스 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-106">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="e77a7-107">기존 웹 서비스 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="e77a7-107">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="e77a7-108">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e77a7-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e77a7-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e77a7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e77a7-111">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="e77a7-112">**웹 서비스** 페이지에서 구성을 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-112">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e77a7-113">**웹 서비스 설정 편집**의 **windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-113">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="e77a7-114">환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-114">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="e77a7-115">**PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-115">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="e77a7-116">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-116">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="e77a7-117">**인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다</span><span class="sxs-lookup"><span data-stu-id="e77a7-117">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="e77a7-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a7-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e77a7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e77a7-119">See Also</span></span>


[<span data-ttu-id="e77a7-120">Lync Server 2013 제어판에서 인증 구성</span><span class="sxs-lookup"><span data-stu-id="e77a7-120">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

