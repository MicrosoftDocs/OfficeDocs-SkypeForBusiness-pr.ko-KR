---
title: 비즈니스용 Skype 서버에서 파일 공유 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 설명하는 문서입니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812238"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="ccebe-104">비즈니스용 Skype 서버에서 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="ccebe-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="ccebe-105">**요약:** 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="ccebe-106">Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ccebe-107">비즈니스용 Skype 서버에는 토폴로지 전체의 컴퓨터가 파일을 교환할 수 있도록 파일 공유가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="ccebe-108">비즈니스용 Skype 서버의 설치 프로세스에서 파일 공유를 만드는 것은 8단계 중 2단계입니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="ccebe-109">1~5단계는 순서에 따라 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ccebe-110">그러나 6, 7, 8단계를 순서대로 수행하고 다이어그램에 설명된대로 1~5단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="ccebe-111">파일 공유에 대한 계획 세부 정보는 비즈니스용 [Skype 서버](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 Skype 서버 [2019의](../../../SfBServer2019/plan/system-requirements.md)서버 요구 사항에 대한 환경 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccebe-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![개요 다이어그램](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="ccebe-113">기본 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="ccebe-113">Create a basic file share</span></span>

<span data-ttu-id="ccebe-114">이 섹션에서는 기본 Windows Server 파일 공유를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="ccebe-115">기본 Windows Server 파일 공유는 비즈니스용 Skype 서버에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="ccebe-116">그러나 고가용성을 명시적으로 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="ccebe-117">고가용성 환경의 경우 DFS(분산 파일 시스템) 파일 공유를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="ccebe-118">고가용성 파일 공유 및 DFS에 대한 자세한 내용은 비즈니스용 Skype 서버의 고가용성 및 재해 복구 [계획을 참조하세요.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="ccebe-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ccebe-119">Windows Server 2012 R2는 Windows Server 플랫폼을 사용하여 SAN(Storage Area Network) 같은 파일 공유 솔루션을 제공하는 데 주요 도약했습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="ccebe-120">기존 SAN 기반 어플라이언스와 비교할 때 Windows Server 2012 R2 저장소 솔루션은 성능에 미치는 영향을 최소화하면서 비용을 절반으로 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="ccebe-121">Windows Server 2012 R2의 파일 공유 옵션에 대한 자세한 내용은 R2 저장소의 다운로드 가능한 [Windows Server 2012 참조하십시오.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)</span><span class="sxs-lookup"><span data-stu-id="ccebe-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="ccebe-122">파일 공유 만들기를 위한 **비디오 단계를 시청하세요.**</span><span class="sxs-lookup"><span data-stu-id="ccebe-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="ccebe-123">기본 파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="ccebe-123">Create a basic file share</span></span>

1. <span data-ttu-id="ccebe-124">파일 공유를 호스팅할 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="ccebe-125">공유할 폴더를 마우스 오른쪽 단추로 클릭하고 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccebe-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="ccebe-126">공유 **탭을 선택하고** **고급 공유를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccebe-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="ccebe-127">이 **폴더 공유를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccebe-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="ccebe-128">**권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="ccebe-129">파일 공유를 호스팅하는 서버의 로컬 **Administrators** 그룹을 추가하고 **허용: 모든 권한,** 변경 및 읽기 권한을 부여한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccebe-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ccebe-130">**확인을** 다시 클릭하고 네트워크 경로를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="ccebe-131">**완료를** 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-131">Click **Done** to close the wizard.</span></span>
    
     ![폴더를 공유하기 위한 공유 탭입니다.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="ccebe-133">파일 저장소가 DFS 공유에 호스트된 경우 다음 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="ccebe-134">경고: "에 대한 공유 권한에 액세스할 수 \\ <domain> \<share> 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="ccebe-135">이 설정은 파일 서버의 관리자가 아니거나 DFS(분산 파일 시스템) 공유인 경우 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="ccebe-136">공유 권한이 이미 구성된 경우 이 경고는 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="ccebe-137">새 공유인 경우 공유 사용 권한을 수동으로 구성하는 자세한 내용은 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ccebe-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="ccebe-138">DFS 공유에 대한 공유 권한에 액세스할 수 없는 경우 비즈니스용 Skype 서버는 파일 공유에 그룹을 명시적으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="ccebe-139">비즈니스용 Skype 서버 구성 요소가 적절한 사용 권한을 사용하여 파일 공유에 액세스할 수 있도록 하기 위해 모든 권한이 있는 로컬 관리자 외에도 읽기 및 변경 수준 공유 권한으로 다음 RTC 그룹을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccebe-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="ccebe-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ccebe-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="ccebe-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ccebe-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="ccebe-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ccebe-142">RTCUniversalServerAdmins</span></span>
