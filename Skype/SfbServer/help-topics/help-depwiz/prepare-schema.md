---
title: 스키마 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Active Directory 도메인 서비스에 대 한 스키마를 준비 하려면 비즈니스용 Skype 서버 배포 마법사에서 스키마 준비 단계를 실행 합니다. 실행을 클릭하여 스키마 준비를 시작합니다. 스키마 준비 단계에서는 배포 마법사가 실행 중인 시스템의/Program Files/Microsoft Lync Server 2013/배포/설정 디렉터리에서 제공 된 스키마 정의 파일을 읽습니다. 이러한 파일은 지원/스키마 디렉터리의 설치 미디어 에서도 사용할 수 있습니다. 스키마 준비 단계에서 스키마를 확장하고 프로세스의 상태를 보고합니다. 또한 프로세스가 완료되면 알려 줍니다. 요약 화면에서 프로세스 로그를 볼 수 있습니다. 로그를 검토하여 준비가 완료 및 성공되었는지 확인합니다.
ms.openlocfilehash: ae4c44adf8c94efa7b87c9f1a4f5f142a7117276
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823482"
---
# <a name="prepare-schema"></a><span data-ttu-id="d4f80-110">스키마 준비</span><span class="sxs-lookup"><span data-stu-id="d4f80-110">Prepare Schema</span></span>
 
<span data-ttu-id="d4f80-111">Active Directory 도메인 서비스에 대 한 스키마를 준비 하려면 비즈니스용 Skype 서버 배포 마법사에서 스키마 준비 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d4f80-112">**실행**을 클릭하여 스키마 준비를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="d4f80-113">스키마 준비 단계에서 배포 마법사가 실행되고 있는 시스템의 \Program Files\Microsoft Lync Server 2010\Deployment\Setup 디렉터리에 있는 제공된 스키마 정의 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="d4f80-114">이러한 파일은 \Support\Schema 디렉터리의 설치 미디어에서도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="d4f80-115">스키마 준비 단계에서 스키마를 확장하고 프로세스의 상태를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="d4f80-116">또한 프로세스가 완료되면 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="d4f80-117">요약 화면에서 프로세스 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="d4f80-118">로그를 검토하여 준비가 완료 및 성공되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4f80-119">스키마를 확장하려면 Schema Admins 그룹 및 Enterprise Admins 그룹의 구성원으로 도메인에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="d4f80-120">Active Directory 도메인 서비스 스키마를 확장 하 여 비즈니스용 Skype 서버 2015 서버, 서비스 및 사용자 개체를 지원 하기 위해 클래스 및 특성이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="d4f80-121">스키마를 확장 하기 전에 스키마 마스터 역할을 보유 하 고 있는 도메인 컨트롤러의 시스템 상태 백업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="d4f80-122">Windows Server 2008 R2 SP1 용 백업 프로세스에 대 한 자세한 내용은을 참조 [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)하세요.</span><span class="sxs-lookup"><span data-stu-id="d4f80-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="d4f80-123">Windows Server 2003 및 Windows Server 2003 R2의 경우를 [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4f80-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d4f80-124">스키마 확장은 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="d4f80-125">가능한 모든 작업을 통해 실패한 스키마 확장의 잠재적 영향을 제한해야 하며, 스키마가 정상적으로 확장되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="d4f80-126">이 작업은 서버에서 통신 장애 또는 기타 오류가 발생할 경우 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="d4f80-127">스키마 마스터 도메인 컨트롤러와 Active Directory의 완전 한 백업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="d4f80-128">Active Directory의 스키마 마스터 도메인 컨트롤러 및 전체 백업 백업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="d4f80-129">네트워크에서 스키마 마스터 역할이 보관된 도메인 컨트롤러의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="d4f80-130">스키마 마스터가 보관된 도메인 컨트롤러의 시스템 상태 백업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="d4f80-131">스키마를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="d4f80-132">스키마 확장이 성공하면 도메인 컨트롤러를 네트워크에 다시 연결하고 복제가 활성 상태이고 작동 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="d4f80-133">스키마 확장에 실패 하는 경우 이전에 만든 시스템 상태 백업을 사용 하 여 도메인 컨트롤러와 Active Directory의 시스템 상태를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4f80-134">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우 배포 마법사가 실행 된 컴퓨터의 파일을 해당 단계를 실행 하는 Active Directory 사용자의 사용자 디렉터리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="d4f80-135">예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f80-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

