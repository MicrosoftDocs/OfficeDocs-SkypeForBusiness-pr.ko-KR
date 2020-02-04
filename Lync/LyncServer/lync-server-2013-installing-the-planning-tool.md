---
title: 'Lync Server 2013: 계획 도구 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7a427ab99368d74180e1d0321741117a9ed97e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="c548b-102">Lync Server 2013에서 계획 도구 설치</span><span class="sxs-lookup"><span data-stu-id="c548b-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c548b-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c548b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c548b-104">Microsoft Lync Server 2013 계획 도구를 사용 하 여 Lync Server 2013 인프라 디자인 및 계획을 시작 하기 전에 먼저 계획 도구를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="c548b-105">Lync Server 2013을 설치 하려는 도메인 또는 인프라의 일부인 워크스테이션 또는 서버에 계획 도구를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="c548b-106">계획 도구와 함께 제공 되는 Readme 파일은 도구 설치 및 사용에 대 한 중요 한 정보를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="c548b-107">이해를 돕기 위해 Readme 파일의 일부 정보가 여기에 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c548b-108">계획 도구는 관리자 권한이 있는 사용자가 설치 하 고 도구를 설치할 컴퓨터에 대 한 사용 권한을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="c548b-109">계획 도구의 설치 및 작동을 위해 지원 되는 운영 체제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="c548b-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="c548b-110">Windows 8</span></span>

  - <span data-ttu-id="c548b-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c548b-111">Windows 8.1</span></span>

  - <span data-ttu-id="c548b-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c548b-112">Windows Server 2012</span></span>

  - <span data-ttu-id="c548b-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c548b-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="c548b-114">Windows 7, 32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="c548b-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="c548b-115">Windows 7, 64 비트 edition (w)에서 Windows를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c548b-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="c548b-116">Windows Server 2008 R2, WOW 사용</span><span class="sxs-lookup"><span data-stu-id="c548b-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="c548b-117">또한 계획 도구에는 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="c548b-118">사전 설치 요구 사항이 충족 되 면 계획 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="c548b-119">계획 도구를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="c548b-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="c548b-120">로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c548b-121">Windows 탐색기나 명령 창을 사용 하 여 계획 도구 설치 파일을 다운로드 한 디렉터리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="c548b-122">LyncPlanningTool를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="c548b-123">Windows 탐색기에서 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="c548b-124">명령 창에 파일 이름을 입력 한 다음 **enter 키를 눌러 파일을 실행** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="c548b-125">Microsoft Lync Server 2013의 시작 페이지에 있는 **계획 도구 설정 마법사**에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="c548b-126">라이선스 계약의 사용 약관에 동의 하기로 선택한 경우 **최종 사용자 사용권 계약**을 확인 하 고 **사용권 계약에** 동의 함을 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="c548b-127">계획 도구 파일을 설치할 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="c548b-128">기본 위치는 C:\\Program Files (x86)\\Microsoft Lync Server 2013\\계획 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="c548b-129">설치 위치를 변경 하려면 **변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="c548b-130">**대상 폴더 변경**에서 파일을 설치할 위치를 찾아보거나 입력 하 고 **확인**을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="c548b-131">이제 설치 관리자가 계획 도구를 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="c548b-132">설치 **를 클릭 하** 여 설치 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="c548b-133">설치가 시작 되 고 진행률이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="c548b-134">설치가 성공적으로 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="c548b-135">계획 도구를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c548b-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c548b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c548b-136">See Also</span></span>


[<span data-ttu-id="c548b-137">Lync Server 2013에서 선택적 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="c548b-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

