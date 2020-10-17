---
title: LyncPerfTool 실행
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4221eaf042fcaee163491d7688b7097e9bcca7a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509115"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="4a89e-102">LyncPerfTool 실행</span><span class="sxs-lookup"><span data-stu-id="4a89e-102">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a89e-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4a89e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4a89e-104">Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool.exe)를 실행 하기 전에 사용자, 연락처 및 시나리오를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="4a89e-105">도구를 사용 하 여 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md) 및 [Configure User Profile](configure-user-profile.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a89e-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="4a89e-106">이러한 도구를 실행 하면 필요한 매개 변수가 포함 된 배치 파일의 일부로 LyncPerfTool.exe를 실행 하는 파일도 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="4a89e-107">Lync Server 2013 스트레스 및 성능 도구 실행</span><span class="sxs-lookup"><span data-stu-id="4a89e-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="4a89e-108">UserProfileGenerator.exe 도구는 LyncPerfTool 성능 카운터를 등록 하 고 XML 구성 파일을 로드 하 여 LyncPerfTool.exe 실행 하는 데 사용할 수 있는 배치 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="4a89e-109">일괄 파일은 구성 파일당 LyncPerfTool.exe 인스턴스 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="4a89e-110">배치 파일을 실행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="4a89e-111">구성 폴더 및 파일이 포함 된 폴더를 각 클라이언트 컴퓨터의 LyncStressTool.exe를 포함 하는 디렉터리에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="4a89e-112">예를 들어 1.28 13.16.16 이라는 폴더에 구성 파일을 생성 \_ 한 경우 각 클라이언트에 LyncPerfTool.exe를 포함 하는 폴더에 해당 폴더를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="4a89e-113">적절 하 게 번호가 매겨진 클라이언트 폴더로 이동 하 고 RunClient batch 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="4a89e-114">Windows 탐색기에서 배치 파일을 두 번 클릭 하기만 하면 해당 클라이언트 번호에 대 한 모든 구성 파일이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="4a89e-115">다음 구문을 사용 하 여 해당 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="4a89e-116">LyncPerfTool.exe를 직접 실행 하려면 명령 프롬프트를 열고 명령줄에서 다음 명령을 입력 합니다 (이 항목의 뒷부분에 나오는 참고 사항에 나오는 것 처럼, 처음으로이 작업을 수행 하는 경우에는 성능 카운터 regsvr32/i/n/s LyncPerfToolPerf.dll를 등록 해야 합니다.) :LyncPerfTool.exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="4a89e-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="4a89e-117">도구에서 구성 파일의 값을 표시 하도록 하려면 다음과 같이 위 명령에/displayfile 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="4a89e-118">프로세스를 종료 하려면 Ctrl + C를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a89e-119">LyncPerfTool를 직접 실행 하기 전에 성능 카운터를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="4a89e-120">다음 명령을 입력 하 여 성능 카운터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="4a89e-121">시작 하는 LyncPerfTool.exe의 모든 인스턴스는 사용자에 게 즉시 로그인을 시작 하 고, 일반적으로 초당 1 명의 사용자에 대 한 작업을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="4a89e-122">풀에 대 한 최고 사용자 로그인 속도는 초당 약 12입니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="4a89e-123">즉, 사용자가 계속 해 서 로그인 하는 동안 12 개 이상의 LyncPerfTool 인스턴스를 동시에 시작 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="4a89e-124">1000 사용자는 초당 1 초에 완전히 로그인 하는 데 약 20 분 정도 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a89e-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a89e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a89e-125">See Also</span></span>


[<span data-ttu-id="4a89e-126">사용자 및 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="4a89e-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="4a89e-127">사용자 프로필 구성</span><span class="sxs-lookup"><span data-stu-id="4a89e-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

