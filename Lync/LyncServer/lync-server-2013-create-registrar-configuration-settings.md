---
title: 'Lync Server 2013: 등록자 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf2f9eac959e9061e42bdc05982593c9f21aa2b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="30ac3-102">Lync Server 2013에서 등록자 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="30ac3-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30ac3-103">_**마지막으로 수정 된 항목:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="30ac3-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="30ac3-104">등록자를 사용 하 여 프록시 서버 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-104">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="30ac3-105">사용자가 지정 하는 인증 프로토콜에 따라 풀의 서버가 클라이언트에 발급할 문제 유형이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-105">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="30ac3-106">사용 가능한 프로토콜은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-106">The available protocols are:</span></span>

  - <span data-ttu-id="30ac3-107">**Kerberos**   클라이언트에서 사용할 수 있는 가장 강력한 암호 기반 인증 구성표 이며, 일반적으로 키 배포 센터 (Kerberos 도메인 컨트롤러)에 대 한 클라이언트 연결이 필요 하기 때문에 엔터프라이즈 클라이언트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="30ac3-108">이 설정은 서버에서 엔터프라이즈 클라이언트만 인증 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="30ac3-109">**NTLM**   암호에 챌린지 응답 해시 구성표를 사용 하는 클라이언트에서 사용할 수 있는 암호 기반 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="30ac3-110">이 인증 양식은 원격 사용자와 같은 키 배포 센터 (Kerberos 도메인 컨트롤러)에 연결 하지 않고는 클라이언트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="30ac3-111">서버에서 원격 사용자만 인증 하는 경우 NTLM을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="30ac3-112">**인증서 인증**   서버가 lync Phone Edition 클라이언트, 공통 영역 전화, lync 2013 및 lync Windows 스토어 앱에서 인증서를 가져와야 할 때 사용할 수 있는 새로운 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="30ac3-113">Lync Phone Edition 클라이언트에서 사용자가 로그인 하 고 개인 식별 번호 (PIN)를 제공 하 여 인증 되 면 Lync Server 2013는 SIP URI를 휴대폰에 프로 비전 하 고, SN=joe@contoso.com를 식별 하는 Lync Server 서명 인증서 또는 사용자 인증서를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="30ac3-114">이 인증서는 등록자 및 웹 서비스를 사용 하 여 인증 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30ac3-p105">서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="30ac3-119">Lync Windows 스토어 앱 클라이언트를 사용 하는 경우에는 인증서 인증을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="30ac3-120">새 등록자를 만들려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="30ac3-121">새 등록자 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="30ac3-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="30ac3-122">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="30ac3-123">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30ac3-124">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30ac3-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30ac3-125">왼쪽 탐색 표시줄에서 **보안**, **등록자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="30ac3-126">**등록자** 페이지에서 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="30ac3-127">**서비스 선택**에서 등록자를 적용할 서비스를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="30ac3-128">**새 등록자 설정**에서 환경의 클라이언트 기능 및 지원에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="30ac3-129">**Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="30ac3-130">**NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="30ac3-131">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="30ac3-132">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac3-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

