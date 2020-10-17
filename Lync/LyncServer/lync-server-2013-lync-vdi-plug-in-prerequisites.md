---
title: 'Lync Server 2013: Lync VDI 플러그 인 필수 구성 요소'
description: 'Lync Server 2013: Lync VDI 플러그 인 필수 구성 요소'
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
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566544"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="7905b-103">Lync Server 2013의 lync VDI 플러그 인 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7905b-103">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7905b-104">_**마지막으로 수정 된 항목:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="7905b-104">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="7905b-105">VDI (가상 데스크톱 인프라) 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가이 섹션에 설명 된 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-105">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7905b-p101">가상화된 환경을 설치하고 배포하는 방법에 대한 자세한 내용은 가상화 솔루션 공급자에게 문의하십시오. Hyper-V와 원격 데스크톱 서비스에 기반을 둔 가상화된 환경 배포에 대한 자세한 내용은 Microsoft TechNet 라이브러리에서 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7905b-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7905b-108">Hyper-v 위치 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="7905b-108">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="7905b-109">Windows Server &nbsp; 2008 R2의 원격 데스크톱 &nbsp; 서비스 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="7905b-109">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="7905b-110">다음은 데이터 센터 컴퓨터에서 실행 중인 가상 컴퓨터에 대한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-110">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="7905b-111">가상 컴퓨터는 Windows 10, Windows 8.1, Windows 8, Windows 7 또는 Windows Server 2008 R2에서 최신 서비스 팩을 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-111">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="7905b-112">다음은 사용자와 사용자의 로컬 컴퓨터에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-112">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="7905b-113">사용자가 Lync Server 2013에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-113">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="7905b-114">로컬 컴퓨터에 Windows Embedded Standard 7 SP1, windows 7 SP1, windows 8, Windows 8.1 Embedded 또는 Windows 8.1 (포함 되지 않음)가 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-114">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="7905b-115">원격 데스크톱 서비스를 사용 하는 경우 Lync VDI 플러그 인 비트 (응용 프로그램이 32 비트 또는 64 비트 인지 여부)가 로컬 컴퓨터의 운영 체제 비트와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-115">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="7905b-116">로컬 컴퓨터의 운영 체제 비트 수와 가상 컴퓨터의 운영 체제 비트 수는 일치하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-116">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="7905b-117">다른 가상화 솔루션 또는 플랫폼을 사용하는 경우 해당 가상화 솔루션 공급자의 비트 수 요구 사항에 대한 지침을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7905b-117">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="7905b-118">로컬 컴퓨터에서 최신 버전의 원격 데스크톱 클라이언트를 실행 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-118">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="7905b-119">Microsoft에서 제공하는 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치하거나 가상화 솔루션 공급자가 제공하는 최신 원격 데스크톱 클라이언트 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-119">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="7905b-120">최신 원격 데스크톱 서비스 업데이트에 대해서는를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .</span><span class="sxs-lookup"><span data-stu-id="7905b-120">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="7905b-121">로컬 컴퓨터에서 오디오가 재생되고 원격 녹음을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-121">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="7905b-122">Windows에서 원격 데스크톱 연결에 대 한 이러한 설정을 구성 하려면 다음 섹션인 "원격 데스크톱 연결 설정을 구성 하려면"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7905b-122">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="7905b-123">원격 데스크톱 연결 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="7905b-123">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="7905b-124">Windows에서 Lync VDI 플러그 인의 원격 데스크톱 연결을 준비 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-124">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="7905b-125">로컬 컴퓨터에서 Windows 8을 실행 하는 경우이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-125">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="7905b-126">로컬 컴퓨터에서 s p 1을 사용 하 여 Windows 7을 실행 하는 경우에는에서 사용할 수 있는 최신 Windows 8 버전의 원격 데스크톱 서비스 클라이언트를 설치 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-126">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="7905b-127">**시작**을 클릭하고 **원격 데스크톱 연결**을 클릭하여 원격 데스크톱 서비스 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-127">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="7905b-128">**옵션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-128">Click **Options**.</span></span>

4.  <span data-ttu-id="7905b-129">**로컬 자원** 탭을 클릭합니다. **원격 오디오**에서 **설정**을 클릭하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-129">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="7905b-130">**원격 오디오 재생**에서 **이 컴퓨터에서 재생**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-130">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="7905b-131">**원격 오디오 녹음**에서 **녹음 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-131">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="7905b-132">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-132">Click **OK**.</span></span>

5.  <span data-ttu-id="7905b-133">**작업 환경** 탭을 클릭합니다. **성능** 아래에서 **지속적인 비트맵 캐싱** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-133">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="7905b-134">**일반** 탭을 클릭합니다. **컴퓨터**에서 가상 컴퓨터 이름을 입력하고 **연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-134">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

