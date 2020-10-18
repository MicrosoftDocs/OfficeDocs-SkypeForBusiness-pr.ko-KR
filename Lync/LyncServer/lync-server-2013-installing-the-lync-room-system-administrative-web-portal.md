---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털 설치'
description: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털을 설치 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fba239346d75142bb4009c58e0ac67e8e1f3bcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573874"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="6866a-103">Lync Server 2013에 Lync 대화방 시스템 관리 웹 포털 설치</span><span class="sxs-lookup"><span data-stu-id="6866a-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6866a-104">_**마지막으로 수정 된 항목:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="6866a-104">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="6866a-105">Microsoft 다운로드 센터에서 Microsoft Lync 대화방 System 관리 웹 포털을 다운로드할 수 있습니다 [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) .</span><span class="sxs-lookup"><span data-stu-id="6866a-105">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="6866a-106">Lync 대화방 시스템 관리 웹 포털을 설치 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-106">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="6866a-107">Lync Server 관리 셸에서 다음 cmdlet을 실행 하 여 신뢰할 수 있는 응용 프로그램 포트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-107">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="6866a-108">회의실 포털을 설치 하려면 **LyncRoomAdminPortal.exe** 다운로드 한 다음 관리자 권한으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-108">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="6866a-109">다음 위치에서 Web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-109">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="6866a-110">% Program Files% \\ Microsoft Lync Server 2013 \\ 웹 구성 요소 \\ 모임 대화방 포털 \\ Int \\ Handler</span><span class="sxs-lookup"><span data-stu-id="6866a-110">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="6866a-111">Web.Config 파일에서 PortalUserName를 "Lync 대화방 시스템 관리 포털에 대 한 선행 작업 구성" 섹션의 2 단계에서 만든 사용자 이름으로 변경 합니다 (단계의 권장 이름은 LRSApp).</span><span class="sxs-lookup"><span data-stu-id="6866a-111">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="6866a-112">LRS 관리 포털은 신뢰할 수 있는 응용 프로그램 이므로 포털 구성에 암호를 제공 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-112">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="6866a-113">이 사용자가 로컬 등록자와 다른 등록자를 사용 하는 경우 Web.Config 파일에 다음 줄을 추가 하 여 해당 등록자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-113">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="6866a-114">사용 된 포트가 5061이 아니면 Web.Config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-114">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="6866a-115">Lync 대화방 시스템 관리 웹 포털의 설치 확인</span><span class="sxs-lookup"><span data-stu-id="6866a-115">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="6866a-116">Lync 대화방 시스템 관리 웹 포털의 설치를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-116">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="6866a-117">프런트 엔드 서버에서 다음 URL로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-117">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="6866a-118">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="6866a-118">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="6866a-119">다음 이미지에 표시 된 대로 오류가 표시 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-119">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="6866a-120">![Lync 대화방 시스템 관리 포털 로그인 화면](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 대화방 시스템 관리 포털 로그인 화면")</span><span class="sxs-lookup"><span data-stu-id="6866a-120">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="6866a-121">오류가 표시 되지 않으면 토폴로지의 다른 컴퓨터에서 다음 URL에 액세스 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-121">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="6866a-122">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="6866a-122">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="6866a-123">페이지에 액세스 하려면에서 "자동 클라이언트 로그인에 필요한 DNS 레코드"에 설명 된 대로 DNS 레코드를 추가 해야 [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6866a-123">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

