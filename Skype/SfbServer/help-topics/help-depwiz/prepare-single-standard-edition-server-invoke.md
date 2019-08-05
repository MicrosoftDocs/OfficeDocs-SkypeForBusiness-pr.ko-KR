---
title: 단일 Standard Edition Server 준비 (호출)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 명령 실행 페이지에서 SQL Server Express를 설치 하 고 중앙 관리 저장소로 작동 하도록 구성 하는 작업을 작업창에서 볼 수 있습니다. 기본적으로 RTC 라는 SQL Server 기반 데이터베이스의 인스턴스가 만들어집니다. 또한 서버 및 클라이언트에 대 한 인바운드 및 아웃 바운드 액세스를 허용 하 고 데이터베이스 및 인스턴스와 통신 하는 방화벽 규칙도 생성 됩니다. 작업이 완료 되 면 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일 이름은 부트스트랩 로컬 컴퓨터입니다. 로그 파일을 선택한 후 로그 보기를 클릭 합니다. 오류 및 경고가 있는지 로그 파일을 검토 합니다. 계속할 준비가 되 면 마침을 클릭 합니다. 이제 아직 토폴로지 작성기를 사용 하 여 토폴로지를 정의 해야 합니다.
ms.openlocfilehash: ec9d3dd8cd1eeadd4d7a69bacdcf6d7e89b1af7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196221"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="fda21-111">단일 Standard Edition Server 준비 (호출)</span><span class="sxs-lookup"><span data-stu-id="fda21-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="fda21-112">**명령 실행** 페이지에서 SQL Server Express를 설치 하 고 중앙 관리 저장소로 작동 하도록 구성 하는 작업을 작업창에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="fda21-113">기본적으로 RTC 라는 SQL Server 기반 데이터베이스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="fda21-114">또한 서버 및 클라이언트에 대 한 인바운드 및 아웃 바운드 액세스를 허용 하 고 데이터베이스 및 인스턴스와 통신 하는 방화벽 규칙도 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="fda21-115">작업이 완료 되 면 드롭다운 목록에서 로그 파일을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="fda21-116">로그 파일 이름은 **부트스트랩 로컬 컴퓨터**입니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="fda21-117">로그 파일을 선택한 후 **로그 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="fda21-118">오류 및 경고가 있는지 로그 파일을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="fda21-119">계속할 준비가 되 면 **마침을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fda21-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="fda21-120">이제 아직 토폴로지 작성기를 사용 하 여 토폴로지를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fda21-121">SQL Server Express 설치는 완료 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="fda21-122">설치 하는 동안 화면이 나 작업창에 진행률이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="fda21-123">설치를 모니터링 하려면 Windows 작업 관리자를 사용 하 여 SQL Server 용 설치 파일 및 MSIExec 프로세스를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="fda21-124">이 방법으로 설치 상태를 확인 하 고 설치가 진행 되 고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="fda21-125">이 도움말 항목의 범위를 벗어나는 요인에 따라, SQL Server 인스턴스 설치를 완료 하는 데 최대 15 분 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda21-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

