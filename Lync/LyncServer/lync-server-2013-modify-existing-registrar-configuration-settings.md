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
ms.openlocfilehash: 32d59c31497f4a7d1a67087f47175184bd5665f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5a214-102">Lync Server 2013에서 기존 등록자 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="5a214-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a214-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a214-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a214-104">등록자를 사용하여 프록시 서버 인증 프토토콜을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="5a214-105">사용 가능한 프로토콜에 대 한 자세한 내용은 [Create 등록자 구성 설정의 Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a214-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a214-p102">서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="5a214-110">다음 단계에 따라 기존의 등록자를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="5a214-111">기존 등록자 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="5a214-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="5a214-112">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5a214-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a214-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a214-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a214-115">왼쪽 탐색 표시줄에서 **보안**, **등록자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="5a214-116">**등록자** 페이지에서 서비스를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5a214-117">환경의 지원 및 클라이언트 기능에 따라 **등록자 설정 편집**에서 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="5a214-118">**Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="5a214-119">**NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="5a214-120">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="5a214-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

