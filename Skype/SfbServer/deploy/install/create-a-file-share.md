---
title: 비즈니스용 Skype 서버에서 파일 공유 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '요약: 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 설명 합니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028299"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="b9fac-104">비즈니스용 Skype 서버에서 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="b9fac-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="b9fac-105">**요약:** 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="b9fac-106">Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="b9fac-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b9fac-107">비즈니스용 Skype 서버에는 파일 공유가 필요 하므로 토폴로지 전체 컴퓨터에서 파일을 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="b9fac-108">파일 공유를 만드는 작업은 비즈니스용 Skype 서버에 대 한 설치 프로세스의 2 ~ 8 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="b9fac-109">순서에 관계 없이 1 ~ 5 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b9fac-110">그러나 다이어그램에 나와 있는 1 ~ 5 단계를 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="b9fac-111">파일 공유에 대 한 세부 정보를 계획 하려면 비즈니스용 [Skype 서버에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 [비즈니스용 skype 서버 2019의 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9fac-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![개요 다이어그램](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="b9fac-113">기본 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="b9fac-113">Create a basic file share</span></span>

<span data-ttu-id="b9fac-114">이 섹션에서는 기본 Windows Server 파일 공유를 만드는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="b9fac-115">기본 Windows Server 파일 공유는 비즈니스용 Skype 서버에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="b9fac-116">그러나 고가용성을 명시적으로 제공 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="b9fac-117">고가용성 환경의 경우 DFS (분산 파일 시스템) 파일 공유를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="b9fac-118">고가용성 파일 공유 및 DFS에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9fac-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9fac-119">Windows Server 2012 R2는 Windows Server 플랫폼을 사용 하 여 SAN (저장 영역 네트워크)과 같은 파일 공유 솔루션을 제공 하기 위해 주요 leaps 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="b9fac-120">전통적인 SAN 기반 기기와 비교 하는 경우 Windows Server 2012 R2 저장소 솔루션은 성능에 거의 영향을 미치지 않고 비용을 절반까지 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="b9fac-121">Windows Server 2012 r 2의 파일 공유 옵션에 대 한 자세한 내용은 다운로드 가능한 백서 [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9fac-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="b9fac-122">**파일 공유를 만들기**위한 비디오 단계를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9fac-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="b9fac-123">기본 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="b9fac-123">Create a basic file share</span></span>

1. <span data-ttu-id="b9fac-124">파일 공유를 호스트 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="b9fac-125">공유할 폴더를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="b9fac-126">**공유** 탭을 선택 하 고 **고급 공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="b9fac-127">**이 폴더 공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="b9fac-128">**권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="b9fac-129">파일 공유를 호스트 하는 서버의 로컬 **관리자** 그룹을 추가 하 고 **허용: 모든 권한, 변경 및 읽기** 권한을 부여 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="b9fac-130">**확인** 을 다시 클릭 하 고 네트워크 경로를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="b9fac-131">**완료** 를 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-131">Click **Done** to close the wizard.</span></span>
    
     ![폴더 공유를 위한 공유 탭](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="b9fac-133">파일 저장소가 DFS 공유에 호스트 되는 경우 다음 경고가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="b9fac-134">경고: "\\<domain>\<공유>"에 대 한 공유 사용 권한에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="b9fac-135">이는 파일 서버의 관리자가 아니거나 DFS (분산 파일 시스템) 공유 인 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="b9fac-136">공유 사용 권한이 이미 구성 되어 있는 경우에는이 경고를 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="b9fac-137">새 공유 인 경우 수동으로 공유 사용 권한을 구성 하는 방법에 대 한 자세한 내용은 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9fac-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="b9fac-138">DFS 공유에 대 한 공유 사용 권한에 액세스할 수 없기 때문에 비즈니스용 Skype 서버가 파일 공유에서 그룹을 명시적으로 설정 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fac-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="b9fac-139">비즈니스용 Skype 서버 구성 요소가 적절 한 사용 권한을 사용 하 여 파일 공유에 액세스할 수 있도록 하려면 모든 권한 공유를 사용 하 여 로컬 관리자 외에도 읽기 및 변경 수준 공유 사용 권한을 사용 하 여 다음 RTC 그룹을 추가 해야 합니다. 사용.</span><span class="sxs-lookup"><span data-stu-id="b9fac-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="b9fac-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b9fac-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="b9fac-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b9fac-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="b9fac-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b9fac-142">RTCUniversalServerAdmins</span></span>
