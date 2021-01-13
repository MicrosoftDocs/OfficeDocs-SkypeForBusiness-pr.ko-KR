---
title: 비즈니스용 Skype 서버에서 새 파일 저장소로 파일 저장소 데이터 이동
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 현재 비즈니스용 Skype 서버 배포에 대해 파일 저장소로 사용 중인 파일 서버를 제거해야 하는 경우 또는 현재 파일 저장소를 사용할 수 없게 만드는 다른 변경을 해야 하는 경우 먼저 새 공유를 만들어야 합니다. 그런 다음 다음 단계를 수행해야 합니다.
ms.openlocfilehash: 6121083d736075fa9ec58380dbc09ef6a8c4ef68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819608"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="cd083-104">비즈니스용 Skype 서버에서 새 파일 저장소로 파일 저장소 데이터 이동</span><span class="sxs-lookup"><span data-stu-id="cd083-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="cd083-105">현재 비즈니스용 Skype 서버 배포에 대한 파일 저장소로 사용 중인 파일 서버를 제거해야 하는 경우 또는 현재 파일 저장소를 사용할 수 없게 만드는 다른 변경을 해야 하는 경우 먼저 새 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="cd083-106">그런 다음 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="cd083-107">제거할 파일 저장소를 사용하는 비즈니스용 Skype 서버 서비스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="cd083-108">토폴로지 작성기에서 파일 저장소를 정의하고 배포에서 새 파일 저장소를 사용할 수 있도록 변경 내용을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="cd083-109">데이터를 새 파일 저장소로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd083-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="cd083-110">서버 또는 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="cd083-111">선택적으로 이전 파일 공유 및 파일 폴더를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="cd083-112">하나의 파일 저장소에서 새 파일 저장소로 파일 저장소 데이터를 이동하려면</span><span class="sxs-lookup"><span data-stu-id="cd083-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="cd083-113">비즈니스용 Skype 서버, 관리 도구가 설치된 RTCUniversersalServerAdmins 또는 CsServerAdministrator 그룹의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="cd083-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="cd083-115">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="cd083-116">제거할 파일 저장소를 사용하는 각 Director 풀, Director, Standard Edition Server 및 프런트 엔드 풀에 대해 서버 또는 풀을 선택하고 작업을 클릭한 다음 모든 서비스 중지를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="cd083-117">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="cd083-118">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 토폴로지 **작성기** 클릭</span><span class="sxs-lookup"><span data-stu-id="cd083-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="cd083-119">파일 저장소를 사용하는 서버 또는 풀을 선택하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="cd083-120">서버 또는 풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="cd083-121">속성 **편집의** **연결 아래에 있는** 파일 **저장소에서** 새로 **고치기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="cd083-122">새 **파일 저장소** 정의의 파일 서버 **FQDN** 아래에서 파일 서버의 FQDN(정식 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="cd083-123">파일 **공유 아래에서** 새 파일 공유의 폴더 이름을 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="cd083-124">이 단계에서는 토폴로지 작성기에서 사용할 새 파일 저장소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="cd083-125">각 서버에 대해 정의하는 것이 아니라 한 번만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-125">You define it only once, not for each server.</span></span> <span data-ttu-id="cd083-126">토폴로지를 게시하기 전에 정의된 파일 서버에서 정의된 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="cd083-127">자세한 내용은 [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd083-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="cd083-128">파일 저장소를 사용하는 각 서버 또는 풀에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="cd083-129">서버 또는 풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="cd083-130">속성 **편집의** **연결 아래에** **있는 파일** 저장소에서 새 파일 공유를 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="cd083-131">토폴로지 게시, 복제 상태 확인 및 필요한 경우 비즈니스용 Skype 서버 배포 마법사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="cd083-132">자세한 내용은 [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd083-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="cd083-133">명령 프롬프트 시작:  **시작,** 실행을 클릭한 다음 명령 프롬프트를 cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="cd083-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="cd083-134">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="cd083-135">/S 스위치는 파일, 폴더 및 하위irector를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="cd083-136">/XF 스위치는 Meeting.Active라는 모든 파일을 건너뜁습니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="cd083-137">현재 버전의 robocopy.exe에 /MT 스위치를 사용하면 다중 스레드를 사용하여 복사 속도를 크게 향상시켜 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="cd083-138">/LOG 스위치의 경우 디렉터리 경로 및 로그 파일 이름을 디렉터리 경로 형식의 C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="cd083-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="cd083-139">이 스위치는 명명된 위치에 작업 로그 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="cd083-140">데이터 복사본이 완료되면 Lync Server 제어판에서 토폴로지 및 상태를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="cd083-141">서비스를 중지한 각 서버 또는 풀에 대해 서버 또는 풀을 선택하고 작업을 클릭한 다음 모든 서비스 **시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd083-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="cd083-142">토폴로지에서 오래된 파일 저장소를 제거한 후 토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="cd083-143">자세한 내용은 [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd083-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="cd083-144">(선택 사항) 바로 전에 제거한 파일 저장소가 포함된 컴퓨터에 로컬 Administrators 그룹 또는 도메인 관리자 그룹의 구성원으로 로그온한 후 오래된 파일 공유 및 디렉터리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd083-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd083-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd083-145">See also</span></span>

[<span data-ttu-id="cd083-146">서버를 다른 파일 저장소에 다시 할당</span><span class="sxs-lookup"><span data-stu-id="cd083-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="cd083-147">파일 저장소 제거</span><span class="sxs-lookup"><span data-stu-id="cd083-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
