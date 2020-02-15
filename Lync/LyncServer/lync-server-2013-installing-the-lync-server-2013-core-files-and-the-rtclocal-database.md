---
title: Lync Server 2013 코어 파일 및 RTCLocal 데이터베이스 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8502e1af9ddb607c25ed04429f6b5bb7fbfe980
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="120e3-102">Lync Server 2013 코어 파일 및 RTCLocal 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="120e3-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="120e3-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="120e3-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="120e3-104">컴퓨터에 Lync Server 2013 코어 파일을 설치 하려면 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="120e3-105">RTCLocal 데이터베이스는 핵심 파일을 설치하면 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="120e3-106">감시자 노드에는 SQL Server를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="120e3-107">대신 SQL Server Express가 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="120e3-108">Lync Server 2013 코어 파일 및 RTCLocal 데이터베이스를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="120e3-109">감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="120e3-110">콘솔 창에서 다음 명령을 입력 한 다음 Lync Server 설치 파일의 적절 한 경로를 사용 하 여 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="120e3-111">핵심 Lync Server 구성 요소가 성공적으로 설치 되었는지 확인 하려면 **시작**, **모든 프로그램**, **lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="120e3-112">Lync Server 2013 관리 셸에서 다음 Windows PowerShell 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="120e3-113">이 명령을 처음 실행하면 감시자 노드 컴퓨터를 아직 구성하지 않았기 때문에 아무런 데이터가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="120e3-114">오류가 반환 되지 않고 명령이 실행 되 면 Lync Server 설치가 완료 된 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="120e3-115">감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 다음 명령을 실행 하 여 Lync Server 2013의 설치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="120e3-116">조직에서 사용하도록 구성된 개인 ID 번호(PIN) 정책의 수에 따라 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="120e3-117">PIN 정책에 대한 정보가 표시되면 핵심 구성 요소가 올바르게 설치된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="120e3-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

