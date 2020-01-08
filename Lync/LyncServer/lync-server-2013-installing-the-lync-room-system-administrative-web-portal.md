---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="b2fce-102">Lync Server 2013에서 Lync 채팅방 시스템 관리 웹 포털 설치</span><span class="sxs-lookup"><span data-stu-id="b2fce-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2fce-103">_**마지막으로 수정한 주제:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="b2fce-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="b2fce-104">Microsoft 다운로드 센터에서 Microsoft Lync 채팅방 시스템 관리 웹 포털을 다운로드할 수 있습니다 [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span><span class="sxs-lookup"><span data-stu-id="b2fce-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="b2fce-105">Lync 채팅방 시스템 관리 웹 포털을 설치 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="b2fce-106">Lync Server Management Shell에서 다음 cmdlet을 실행 하 여 신뢰할 수 있는 응용 프로그램 포트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="b2fce-107">회의실 포털을 설치 하려면 **LyncRoomAdminPortal** 를 다운로드 한 다음 관리자 권한으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="b2fce-108">다음 위치에서 web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="b2fce-109">% Program Files%\\Microsoft Lync Server 2013\\웹 구성\\요소 모임 채팅방\\포털\\Int 처리기</span><span class="sxs-lookup"><span data-stu-id="b2fce-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="b2fce-110">Web.config 파일에서 PortalUserName을 2 단계에서 만든 사용자 이름 "Lync 대화방 시스템 관리 포털에 대 한 필수 구성 요소 구성" 섹션의 "(단계에서 권장 되는 이름: LRSApp)"으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="b2fce-111">LRS 관리 포털은 신뢰할 수 있는 응용 프로그램 이므로 포털 구성에 암호를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="b2fce-112">이 사용자가 로컬 등록 기관 이외의 다른 등록 기관을 사용 하는 경우 web.config 파일에 다음 줄을 추가 하 여 등록 기관에 대 한 등록자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="b2fce-113">사용 된 포트가 5061이 아니면 web.config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="b2fce-114">Lync 채팅방 시스템 관리 웹 포털의 설치 확인</span><span class="sxs-lookup"><span data-stu-id="b2fce-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="b2fce-115">Lync 채팅방 시스템 관리 웹 포털의 설치를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="b2fce-116">프런트 엔드 서버에서 다음 URL을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="b2fce-117">https://\<fe-서버\>/lrs</span><span class="sxs-lookup"><span data-stu-id="b2fce-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="b2fce-118">다음 이미지와 같이 오류가 표시 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="b2fce-119">![Lync 채팅방 시스템 관리 포털 로그인 화면](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 대화방 시스템 관리 포털 로그인 화면")</span><span class="sxs-lookup"><span data-stu-id="b2fce-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="b2fce-120">오류가 표시 되지 않으면 토폴로지의 다른 컴퓨터에서 다음 URL에 액세스 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b2fce-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="b2fce-121">https://\<fe-서버\>/lrs</span><span class="sxs-lookup"><span data-stu-id="b2fce-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="b2fce-122">페이지에 액세스 하려면 "자동 클라이언트 로그인에 필요한 DNS 레코드"의 설명에 따라 DNS 레코드를 추가 해야 [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fce-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

