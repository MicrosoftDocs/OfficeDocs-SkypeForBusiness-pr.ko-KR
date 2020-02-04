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
ms.openlocfilehash: b8c3e81379eb411b2b77129e51b59ce675887394
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="09d7c-102">Lync Server 2013에서 새 웹 서비스 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="09d7c-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09d7c-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="09d7c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="09d7c-104">**웹 서비스** 페이지를 사용 하 여 Lync Server 2013 관련 웹 서버 및 웹 서비스에 액세스 하기 위한 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="09d7c-105">새 웹 서비스 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="09d7c-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="09d7c-106">새 웹 서비스 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="09d7c-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="09d7c-107">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="09d7c-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09d7c-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09d7c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="09d7c-110">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="09d7c-111">**웹 서비스** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="09d7c-112">사이트에 대 한 웹 서비스를 구성 하려면 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="09d7c-113">**사이트 선택**에서 웹 서비스 정책이 사이트를 적용 하는 사이트를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="09d7c-114">풀에 대 한 웹 서비스를 구성 하려면 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="09d7c-115">**서비스 선택**에서 웹 서비스 정책이 적용 되는 서비스를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="09d7c-116">**새 웹 서비스 설정**에서 **windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="09d7c-117">해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="09d7c-118">Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="09d7c-119">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="09d7c-120">**인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="09d7c-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09d7c-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

