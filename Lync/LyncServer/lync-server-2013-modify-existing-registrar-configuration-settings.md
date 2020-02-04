---
title: 'Lync Server 2013: 기존 등록자 구성 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe12f85f7ea8501f478d570612ad52cd350fdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b836b-102">Lync Server 2013에서 기존 등록자 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="b836b-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b836b-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b836b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b836b-104">레지스트라를 사용 하 여 프록시 서버 인증 프로토콜을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="b836b-105">사용할 수 있는 프로토콜에 대 한 자세한 내용은 [Lync Server 2013에서 등록자 구성 설정 만들기](lync-server-2013-create-registrar-configuration-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b836b-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b836b-106">서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="b836b-107">Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-107">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="b836b-108">이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-108">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="b836b-109">엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-109">If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="b836b-110">기존 등록자를 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b836b-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="b836b-111">기존 등록자 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="b836b-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="b836b-112">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b836b-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b836b-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b836b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b836b-115">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="b836b-116">**등록자** 페이지에서 서비스를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b836b-117">**등록자 편집 설정**에서 해당 환경의 클라이언트 및 지원의 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="b836b-118">Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="b836b-119">**Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="b836b-120">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="b836b-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b836b-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

