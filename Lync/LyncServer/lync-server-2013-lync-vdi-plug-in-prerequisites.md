---
title: 'Lync Server 2013: Lync VDI 플러그 인 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51fb0081188618b6a5ea2951968effb0d55c4af7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="d266e-102">Lync Server 2013의 Lync VDI 플러그 인 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d266e-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d266e-103">_**마지막으로 수정한 주제:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="d266e-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="d266e-104">VDI (가상 데스크톱 인프라) 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가이 섹션에 설명 된 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d266e-105">가상 환경을 설치 하 고 배포 하는 방법에 대 한 자세한 내용은 가상화 솔루션 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d266e-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="d266e-106">Hyper-v 및 원격 데스크톱 서비스를 기반으로 가상화 된 환경을 배포 하는 방법에 대 한 자세한 내용은 Microsoft TechNet 라이브러리의 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d266e-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d266e-107">V h/<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="d266e-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="d266e-108">Windows Server&nbsp;2008&nbsp;R2의 원격 데스크톱 서비스<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="d266e-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="d266e-109">다음은 데이터 센터 컴퓨터에서 실행 되는 가상 컴퓨터에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="d266e-110">최신 서비스 팩을 사용 하 여 Windows 10, Windows 8.1, Windows 8, Windows 7 또는 Windows Server 2008 R2를 사용 하 여 가상 컴퓨터를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="d266e-111">다음은 사용자 및 사용자의 로컬 컴퓨터에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="d266e-112">사용자는 Lync Server 2013에서 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="d266e-113">로컬 컴퓨터는 SP1, Windows 7 for SP1, windows 8, Windows 8.1 Embedded 또는 Windows 8.1 (포함 되지 않음)으로 Windows Embedded 표준 7을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="d266e-114">원격 데스크톱 서비스를 사용 하는 경우 Lync VDI 플러그 인 비트 (즉, 응용 프로그램이 32 비트 인지 아니면 64 비트)가 로컬 컴퓨터의 운영 체제 비트와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="d266e-115">로컬 컴퓨터의 운영 체제 비트와 가상 컴퓨터의 운영 체제는 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="d266e-116">다른 가상화 솔루션 또는 플랫폼을 사용 하는 경우에는 가상화 솔루션 공급자의 비트 요구 사항에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d266e-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="d266e-117">로컬 컴퓨터는 최신 버전의 원격 데스크톱 클라이언트를 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="d266e-118">Microsoft 또는 가상화 솔루션 공급자의 최신 원격 데스크톱 클라이언트 소프트웨어에서 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="d266e-119">최신 원격 데스크톱 서비스 업데이트는를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)하세요.</span><span class="sxs-lookup"><span data-stu-id="d266e-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="d266e-120">로컬 컴퓨터에서 오디오를 재생 하 고 원격 기록을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="d266e-121">Windows에서 원격 데스크톱 연결에 대해 이러한 설정을 구성 하려면 다음 섹션인 "원격 데스크톱 연결 설정 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d266e-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="d266e-122">원격 데스크톱 연결 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="d266e-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="d266e-123">Windows에서 Lync VDI 플러그 인에 대 한 원격 데스크톱 연결을 준비 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="d266e-124">로컬 컴퓨터에서 Windows 8을 실행 하는 경우에는이 단계를 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="d266e-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="d266e-125">로컬 컴퓨터에서 SP1을 사용 하 여 Windows 7을 실행 하는 경우에는에서 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)사용할 수 있는 최신 Windows 8 버전의 원격 데스크톱 서비스 클라이언트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="d266e-126">**시작**을 클릭 한 다음 **원격 데스크톱 연결**을 클릭 하 여 원격 데스크톱 서비스 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="d266e-127">**옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-127">Click **Options**.</span></span>

4.  <span data-ttu-id="d266e-128">**로컬 리소스** 탭을 클릭 합니다. **원격 오디오**에서 **설정을**클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="d266e-129">**원격 오디오 재생**에서 **이 컴퓨터에서 재생**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="d266e-130">**원격 오디오 기록**에서 **녹화 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="d266e-131">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-131">Click **OK**.</span></span>

5.  <span data-ttu-id="d266e-132">**환경** 탭을 클릭 합니다. **성능**에서 **영구적 비트맵 캐싱** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="d266e-133">**일반** 탭을 클릭 합니다. **컴퓨터**에서 가상 컴퓨터의 이름을 입력 한 다음 **연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d266e-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

