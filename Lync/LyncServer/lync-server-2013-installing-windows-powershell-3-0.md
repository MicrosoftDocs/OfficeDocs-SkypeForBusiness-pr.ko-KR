---
title: 'Lync Server 2013: Windows PowerShell 3.0 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a799ba54fe7677ed2ccfa8051f295b2b775cdc0e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="94dd3-102">Lync Server 2013 용 Windows PowerShell 3.0 설치</span><span class="sxs-lookup"><span data-stu-id="94dd3-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94dd3-103">_**마지막으로 수정 된 항목:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="94dd3-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="94dd3-104">Lync Server 2013을 성공적으로 배포 하려면 Lync Server 토폴로지의 일부인 각 컴퓨터에 Windows PowerShell 3.0이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="94dd3-105">이제 Windows Server 2012 또는 Windows Server 2012 r 2를 실행 하는 시스템의 경우에는이 작업을 수행할 필요가 없으며, 이러한 운영 체제에 PowerShell 3.0이 포함 되어 있으므로 다음 배포 단계를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94dd3-106">그러나 Windows Server 2008 R2 s p 1을 실행 하는 시스템의 경우 Lync Server 2013을 설치 하기 전에 PowerShell 3.0을 필수 구성 요소로 설치 해야 하며, 그렇지 않은 경우에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="94dd3-107">PowerShell 3.0을 설치 하려면 <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94dd3-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="94dd3-108">PowerShell 3.0 다운로드 페이지에 대 한 직접 링크 이며 성공적인 설치와 관련 된 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="94dd3-109">설치를 완료 한 후 또는 Lync Server 배포를 계속 하기 전에 확인 하려는 경우에는이 작업을 수행 하는 경우 PowerShell 3.0이 서버에 있는지 확인 하는 것이 아주 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="94dd3-110">확인할 서버에서 **시작**, **모든 프로그램**, **보조 프로그램**, **windows powershell**, **windows**powershell을 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="94dd3-111">Windows PowerShell 콘솔에서 명령 프롬프트에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="94dd3-112">Windows PowerShell 3.0이 설치 되어 있으면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dd3-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

