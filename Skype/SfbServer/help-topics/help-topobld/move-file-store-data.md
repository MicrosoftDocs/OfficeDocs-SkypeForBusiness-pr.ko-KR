---
title: 비즈니스용 Skype 서버 2015에서 파일 저장소 데이터를 새 파일 저장소로 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 현재 비즈니스용 Skype Server 2015 배포에 대 한 파일 저장소 역할을 하는 파일 서버를 제거 해야 하거나 현재 파일 저장소를 사용할 수 없도록 하는 다른 변경 작업을 수행 해야 하는 경우에는 먼저 새 공유를 만들어야 합니다. 그런 다음 다음 단계를 수행 해야 합니다.
ms.openlocfilehash: 7334246f4de6a820339e3fff5f9c19cb86a74422
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819520"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="619d3-104">비즈니스용 Skype 서버 2015에서 파일 저장소 데이터를 새 파일 저장소로 이동</span><span class="sxs-lookup"><span data-stu-id="619d3-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="619d3-105">현재 비즈니스용 Skype Server 2015 배포에 대 한 파일 저장소 역할을 하는 파일 서버를 제거 해야 하거나 현재 파일 저장소를 사용할 수 없도록 하는 다른 변경 작업을 수행 해야 하는 경우에는 먼저 새 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="619d3-106">그런 다음 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="619d3-107">제거 하려는 파일 저장소를 사용 하는 비즈니스용 Skype 서버 2015 서비스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="619d3-108">토폴로지 작성기에서 파일 저장소를 정의 하 고 변경 내용을 게시 하 여 배포에서 새 파일 저장소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="619d3-109">데이터를 새 파일 저장소로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="619d3-110">서버 또는 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="619d3-111">필요에 따라 이전 파일 공유 및 파일 폴더를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="619d3-112">파일 저장소 데이터를 한 파일 저장소에서 새 파일 저장소로 이동 하려면 다음을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="619d3-113">비즈니스용 Skype 서버 2015, 관리 도구가 설치 되어 있는 RTCUniversersalServerAdmins 또는 CsServerAdministrator 그룹의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="619d3-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="619d3-115">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="619d3-116">제거 하려는 파일 저장소를 사용 하는 각 디렉터 풀, 디렉터, Standard Edition server 및 프런트 엔드 풀에 대해 서버 또는 풀을 선택 하 고 **작업**을 클릭 한 다음 **모든 서비스 중지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="619d3-117">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="619d3-118">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="619d3-119">파일 저장소를 사용 하는 서버 또는 풀을 선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="619d3-120">서버 또는 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="619d3-121">**속성 편집**의 **연결**에 있는 **파일 저장소**에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="619d3-122">**새 파일 저장소 정의**의 **파일 서버 fqdn**에 파일 서버의 정규화 된 도메인 이름 (fqdn)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="619d3-123">**파일 공유**에서 새 파일 공유에 대 한 폴더 이름을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="619d3-124">이 단계는 토폴로지 작성기에서 사용할 새 파일 저장소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="619d3-125">각 서버에 대해 한 번만 정의 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-125">You define it only once, not for each server.</span></span> <span data-ttu-id="619d3-126">토폴로지를 게시 하기 전에 정의 된 파일 서버에서 정의 된 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="619d3-127">자세한 내용은 프런트 엔드에서 [파일 저장소 정의](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="619d3-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="619d3-128">파일 저장소를 사용 하는 각 서버 또는 풀에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="619d3-129">서버 또는 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="619d3-130">**속성 편집**의 **연결**아래에 있는 **파일 저장소**에서 새 파일 공유를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="619d3-131">토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 비즈니스용 Skype 서버 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="619d3-132">자세한 내용은 [Lync server 및 구성 요소 제거에 대 한 일반적인 절차](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="619d3-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="619d3-133">**시작**을 클릭 하 고 **실행**을 클릭 한 다음 cmd.exe를 입력 하 여 명령 프롬프트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="619d3-134">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="619d3-135">/S 스위치는 파일, 디렉터리, 하위 디렉터리에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="619d3-136">/XF 스위치는 이름이 지정 된 모임의 모든 파일을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="619d3-137">이/MT 스위치를 사용 하는 robocopy의 현재 버전은 여러 스레드를 사용 하 여 복사 속도를 크게 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="619d3-138">/LOG 스위치의 경우 C:\Logfiles\log.txt. 형식의 디렉터리 경로와 로그 파일 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="619d3-139">이 스위치는 명명 된 위치에 작업의 로그 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="619d3-140">데이터 복사가 완료 되 면 Lync Server 제어판에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="619d3-141">서비스를 중지 한 각 서버 또는 풀에 대해 서버 또는 풀을 선택 하 고 **작업**을 클릭 한 다음 **모든 서비스 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="619d3-142">토폴로지에서 이전 파일 저장소를 제거한 다음 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="619d3-143">자세한 내용은 [파일 저장소 제거](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="619d3-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="619d3-144">) 방금 로컬 Administrators 그룹 또는 Domain Admins 그룹의 구성원으로 제거한 파일 저장소가 포함 된 컴퓨터에 로그온 한 다음 이전 파일 공유 및 디렉터리를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="619d3-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="619d3-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="619d3-145">See also</span></span>

[<span data-ttu-id="619d3-146">다른 파일 저장소에 서버 다시 할당</span><span class="sxs-lookup"><span data-stu-id="619d3-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="619d3-147">파일 저장소 제거</span><span class="sxs-lookup"><span data-stu-id="619d3-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
