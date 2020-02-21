---
title: 'Lync Server 2013: 중재 서버용 파일 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3172b2db7197cfec13249bdff4490128d8b664a1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="bba9a-102">Lync Server 2013에서 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="bba9a-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bba9a-103">_**마지막으로 수정 된 항목:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="bba9a-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="bba9a-104">이 절차를 성공적으로 완료 하려면 최소한 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 도메인 사용자 및 로컬 관리자에 게 서버에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="bba9a-105">이 항목의 단계를 사용 하 여 Lync server 2013 배포 마법사를 실행 하 여 토폴로지 작성기를 사용 하 여 풀을 정의 하 고 게시할 때 중재 서버 풀에 추가한 컴퓨터에 중재 서버에 대 한 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="bba9a-106">파일 중재 서버를 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서도 설치 하 고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="bba9a-107">이 사이트에서 이미 배치 된 중재 서버를 프런트 엔드 풀 또는 Standard Edition 서버에 배포한 경우에는이 항목을 건너뛰고 대신 [Lync server 2013에서 트렁크 구성을](lync-server-2013-configuring-trunks.md)계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bba9a-108">이 항목에서는 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">lync server 2013의 토폴로지 작성기에서 중재 서버 정의</A> 및 배포 설명서의 <A href="lync-server-2013-publish-the-topology.md">lync server 2013에서 토폴로지 게시</A> 에 설명 된 대로 독립 실행형 중재 서버 풀을 이미 정의 하 고 게시 했으며, 중재 서버 풀의 컴퓨터가 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync server 2013에서 enterprise Voice 용 소프트웨어 필수</A> 구성 요소에 설명 된 필수 구성 요소를 충족 하는지 확인 했으며, <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">엔터프라이즈에 대 한 보안 및 구성 선행 조건 Lync Server 2013의 음성</A></span><span class="sxs-lookup"><span data-stu-id="bba9a-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="bba9a-109">독립 실행형 중재 서버 풀 용 파일을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="bba9a-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="bba9a-110">설치 미디어에서 설치 미디어 \<\>**\\설치\\amd64\\setup.exe**를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="bba9a-111">**설치 위치** 페이지에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="bba9a-112">**최종 사용자 사용권 계약** 페이지에서 **동의 함을**클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="bba9a-113">(계속 하는 데 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="bba9a-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="bba9a-114">**Lync server 2010 배포 마법사** 페이지에서 **Lync server 시스템 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="bba9a-115">**1 단계: 로컬 구성 저장소 설치**옆에 있는 **실행**을 클릭 한 다음 화면의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="bba9a-116">**중앙 관리 저장소의 로컬 복제본 구성** 페이지에서 **중앙 관리 저장소에서 직접 기본 검색**을 수락 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="bba9a-117">**명령 실행** 페이지에서 작업 상태가 **완료**됨으로 표시 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="bba9a-118">**2 단계: Lync Server 구성 요소 설치 또는 제거**옆에 있는 **실행**을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="bba9a-119">**명령 실행** 페이지에서 작업 상태가 **완료**됨으로 표시 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="bba9a-120">**3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="bba9a-121">기본 설정을 그대로 적용 하 여 화면에 나타나는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="bba9a-122">중재 서버에는 하나의 인증서가 필요 하므로 **3 단계** 를 두 번 실행 하 여 필요한 인증서를 발급 하 고 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="bba9a-123">인증서가 올바르게 발급 및 할당 되 면 **4 단계: 서비스 시작**옆에 있는 **실행**을 클릭 한 다음 화면의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="bba9a-124">**4 단계가** 성공적으로 완료 되 면 서버를 다시 시작 하 고 domainadmins 그룹의 구성원으로 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="bba9a-125">Lync Server 제어판을 실행 중인 컴퓨터에서, 중재 서버의 서비스 상태가 녹색 확인 표시로 표시 되도록 Lync Server 제어판의 **토폴로지** 페이지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="bba9a-126">대신 빨간색 X가 나타나면 중재 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="bba9a-127">**동작** 메뉴에서 **모든 서비스 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="bba9a-128">중재 서버 풀에 둘 이상의 컴퓨터를 추가한 경우 중재 서버 풀의 다른 모든 컴퓨터에서이 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="bba9a-129">다른 컴퓨터의 중재 서버용 파일을 설치 하지 않아도 되는 경우에는 [Lync server 2013에서 트렁크 구성](lync-server-2013-configuring-trunks.md) 의 절차에 따라이 중재 서버 풀 (또는 사이트의 모든 중재 서버)과 해당 피어 간의 트렁크 연결에 대 한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba9a-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bba9a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bba9a-130">See Also</span></span>


[<span data-ttu-id="bba9a-131">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bba9a-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

