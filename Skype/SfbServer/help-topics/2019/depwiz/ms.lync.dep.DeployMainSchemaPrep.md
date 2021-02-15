---
title: 스키마 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory 도메인 서비스에 대한 Schema를 준비하려면 비즈니스용 Skype 서버 배포 마법사에서 Schema 준비 단계를 실행합니다. 실행을 클릭하여 스키마 준비를 시작합니다.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833778"
---
# <a name="prepare-schema"></a><span data-ttu-id="d634b-104">스키마 준비</span><span class="sxs-lookup"><span data-stu-id="d634b-104">Prepare Schema</span></span>
 
<span data-ttu-id="d634b-105">Active Directory 도메인 서비스에 대한 Schema를 준비하려면 비즈니스용 Skype 서버 배포 마법사에서 Schema 준비 단계를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d634b-106">**실행** 을 클릭하여 스키마 준비를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="d634b-107">Schema 준비 단계에서는 배포 마법사를 실행 중인 시스템의 \Program Files\Skype for Business Server 2019\Deployment\Setup 디렉터리에 제공된 Schema 정의 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="d634b-108">이러한 파일은 \Support\Schema 디렉터리의 설치 미디어에서도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="d634b-109">스키마 준비 단계에서 스키마를 확장하고 프로세스의 상태를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="d634b-110">또한 프로세스가 완료되면 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="d634b-111">요약 화면에서 프로세스 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="d634b-112">로그를 검토하여 준비가 완료 및 성공되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d634b-113">스키마를 확장하려면 Schema Admins 그룹 및 Enterprise Admins 그룹의 구성원으로 도메인에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="d634b-114">클래스 및 특성은 비즈니스용 Skype 서버 서버, 서비스 및 사용자 개체를 지원하도록 Active Directory 도메인 서비스 schema를 확장하기 위해 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="d634b-115">스키마를 확장하기 전에 스키마 마스터 역할이 보관된 도메인 컨트롤러의 시스템 상태 백업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d634b-116">스키마 확장은 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="d634b-117">가능한 모든 작업을 통해 실패한 스키마 확장의 잠재적 영향을 제한해야 하며, 스키마가 정상적으로 확장되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="d634b-118">이 작업은 서버에서 통신 장애 또는 기타 오류가 발생할 경우 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="d634b-119">또한 Schema 마스터 도메인 컨트롤러의 백업과 Active Directory의 전체 백업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="d634b-120">Schema 마스터 도메인 컨트롤러의 백업 및 Active Directory의 전체 백업을 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d634b-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="d634b-121">네트워크에서 스키마 마스터 역할이 보관된 도메인 컨트롤러의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="d634b-122">스키마 마스터가 보관된 도메인 컨트롤러의 시스템 상태 백업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="d634b-123">스키마를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="d634b-124">스키마 확장이 성공하면 도메인 컨트롤러를 네트워크에 다시 연결하고 복제가 활성 상태이고 작동 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="d634b-125">가능성은 낮지만, 이 경우 앞에서 수행한 시스템 상태 백업을 사용하여 도메인 컨트롤러 및 Active Directory의 시스템 상태를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d634b-126">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터의 해당 단계를 실행한 Active Directory 사용자의 Users 디렉터리에서 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="d634b-127">예를 들어 사용자가 도메인 Contoso.net 도메인 관리자로 로그인한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d634b-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

