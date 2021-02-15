---
title: 단일 Standard Edition Server 준비(호출)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 명령 실행 페이지에서 SQL Server Express를 설치하고 중앙 관리 저장소 역할을 하도록 구성하는 작업을 작업 창에서 볼 수 있습니다. 기본적으로 RTC라는 SQL Server 데이터베이스의 인스턴스가 만들어집니다. 서버 및 클라이언트가 데이터베이스 및 인스턴스와 통신할 수 있도록 인바운드 및 아웃바운드 액세스를 허용하기 위한 방화벽 규칙도 만들어집니다. 작업이 완료된 후 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일의 이름은 부트스트랩 로컬 컴퓨터입니다. 로그 파일을 선택한 후 로그 보기를 클릭합니다. 로그 파일을 검토하여 오류 및 경고가 있는 지 확인합니다. 계속할 준비가 되면 마침을 클릭합니다. 토폴로지 작성기에서 토폴로지 정의를 아직 수행하지 않은 경우 토폴로지가 정의됩니다.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829748"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="82a2c-111">단일 Standard Edition Server 준비(호출)</span><span class="sxs-lookup"><span data-stu-id="82a2c-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="82a2c-112">명령  실행 페이지에서 SQL Server Express를 설치하고 중앙 관리 저장소 역할을 하도록 구성하는 작업을 작업 창에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="82a2c-113">기본적으로 RTC라는 SQL Server 데이터베이스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="82a2c-114">서버 및 클라이언트가 데이터베이스 및 인스턴스와 통신할 수 있도록 인바운드 및 아웃바운드 액세스를 허용하기 위한 방화벽 규칙도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="82a2c-115">작업이 완료된 후 드롭다운 목록에서 로그 파일을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="82a2c-116">로그 파일의 이름은 **부트스트랩 로컬 컴퓨터** 입니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="82a2c-117">로그 파일을 선택한 후 **로그 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="82a2c-118">로그 파일을 검토하여 오류 및 경고가 있는 지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="82a2c-119">계속할 준비가 되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="82a2c-120">토폴로지 작성기에서 토폴로지 정의를 아직 수행하지 않은 경우 토폴로지가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="82a2c-121">SQL Server Express 설치를 완료하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="82a2c-122">설치하는 동안 화면이나 작업 창에 진행률이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="82a2c-123">설치를 모니터링하려면 Windows 작업 관리자를 사용하여 MSIExec 프로세스 및 설치 파일을 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82a2c-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="82a2c-124">이 방법으로 설치 상태를 보고 설치가 진행 중인지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="82a2c-125">이 도움말 항목의 범위를 벗어났던 요소에 따라 설치가 완료되는 데 최대 15분 SQL Server 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a2c-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

