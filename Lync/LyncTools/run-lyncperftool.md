---
title: L Cperf도구 실행
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daf46c5e34558a719cdf4fafa15a57f273c4030d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="2b468-102">L Cperf도구 실행</span><span class="sxs-lookup"><span data-stu-id="2b468-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b468-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2b468-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2b468-104">Lync Server 2013 스트레스 및 성능 도구 (L Cperftool. exe)를 실행 하기 전에 사용자, 연락처 및 시나리오를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="2b468-105">도구를 사용 하 여 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 [사용자 및 연락처 만들기](create-users-and-contacts.md) 및 [사용자 프로필 구성을](configure-user-profile.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b468-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="2b468-106">이러한 도구를 실행 하면 필수 매개 변수를 포함 하는 배치 파일의 일부로 L를 사용 하는 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="2b468-107">Lync Server 2013 스트레스 및 성능 도구 실행</span><span class="sxs-lookup"><span data-stu-id="2b468-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="2b468-108">UserProfileGenerator 도구는 L Cperftool 성능 카운터를 등록 하 고 XML 구성 파일을 로드 하 여 l Cperftool을 실행할 수 있는 배치 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="2b468-109">일괄 처리 파일은 각 구성 파일에 대해 L Cperftool의 인스턴스 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="2b468-110">배치 파일을 실행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="2b468-111">구성 폴더 및 파일을 포함 하는 폴더를 각 클라이언트 컴퓨터의 LyncStressTool를 포함 하는 디렉터리에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="2b468-112">예를 들어 1.28\_13.16.16 이라는 폴더에 있는 구성 파일을 생성 한 경우 각 클라이언트에서 L Cperftool이 포함 된 폴더로 해당 폴더를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="2b468-113">적절 한 번호를 매긴 클라이언트 폴더로 이동 하 고 RunClient batch 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="2b468-114">Windows 탐색기에서 배치 파일을 두 번 클릭 하기만 하면 해당 클라이언트 번호에 대 한 모든 구성 파일이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="2b468-115">다음 구문을 사용 하 여 적절 한 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="2b468-116">L Cperftool을 직접 실행 하려면 명령 프롬프트를 열고 명령줄에 다음 명령을 입력 합니다 (이 항목의 뒷부분에 나오는 노트에 표시 된 대로 성능 카운터 regsvr32/i/n/s L Ccptoolperf: dll을 등록 해야 합니다.). L Cperftool. exe/file:\<configxml\></span><span class="sxs-lookup"><span data-stu-id="2b468-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="2b468-117">도구가 구성 파일의 값을 표시 하도록 하려면 다음과 같이 앞의 명령에/displayfile 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="2b468-118">프로세스를 종료 하려면 Ctrl + C를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b468-119">L Cperf도구를 직접 실행 하기 전에 성능 카운터를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="2b468-120">다음 명령을 입력 하 여 성능 카운터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="2b468-121">시작 하는 L Cperftool의 모든 인스턴스는 사용자의 로그인을 즉시 시작 하 고, 일반적으로 초 당 한 명의 사용자에 게 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="2b468-122">풀의 최고 사용자 로그인 속도는 초당 약 12입니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="2b468-123">즉, 사용자가 계속 해 서 로그인 하는 동안 12 개의 L Cperftool 인스턴스를 동시에 시작 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="2b468-124">1000 사용자는 1 초에 완전히 로그인 하는 데 20 분 정도 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b468-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b468-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b468-125">See Also</span></span>


[<span data-ttu-id="2b468-126">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="2b468-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="2b468-127">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="2b468-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

