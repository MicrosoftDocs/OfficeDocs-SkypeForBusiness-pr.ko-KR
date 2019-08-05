---
title: 비즈니스용 Skype 서버에서 중재 서버용 파일 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '요약: 비즈니스용 Skype 서버에서 중재 서버용 파일을 설치 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 8ecd5b20f7f3dfac625851c94f313a50fa71af29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197041"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="e126f-103">비즈니스용 Skype 서버에서 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="e126f-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e126f-104">**요약:** 비즈니스용 Skype 서버에서 중재 서버용 파일을 설치 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="e126f-105">이 절차를 성공적으로 완료 하려면 로컬 관리자와 최소한 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 도메인 사용자로 서버에 최소한으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="e126f-106">이 항목의 단계를 따라 비즈니스용 Skype Server 배포 마법사를 실행 하 여 토폴로지 작성기를 사용 하 여 풀을 정의 하 고 게시 한 후 중재 서버 풀에 추가한 컴퓨터에 중재 서버용 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="e126f-107">파일 조정 서버를 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서를 설치 하 고 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e126f-108">이 항목에서는 [비즈니스용 Skype 서버의 토폴로지 작성기에 중재 서버 배포](deploy-a-mediation-server.md)에 설명 된 대로 사용자가 이미 토폴로지에 독립 실행형 중재 서버 풀을 정의 하 고 게시 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="e126f-109">독립 실행형 중재 서버 풀에 대 한 파일을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="e126f-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="e126f-110">설치 미디어에서 _ \<설치\> 미디어_ **\Setup\amd64\Setup.exe**을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="e126f-111">**설치 위치** 페이지에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="e126f-112">**최종 사용자 사용권 계약** 페이지에서 **동의 함**을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="e126f-113">(계속 하는 데 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e126f-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="e126f-114">**비즈니스용 Skype 서버 배포 마법사** 페이지에서 비즈니스용 **Skype server System 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="e126f-115">**1 단계: 로컬 구성 저장소 설치**, **실행**을 차례로 클릭 한 다음 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="e126f-116">**중앙 관리 저장소의 로컬 복제본 구성** 페이지에서 **중앙 관리 저장소에서 직접 기본 검색**을 수락 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e126f-117">**명령 실행** 페이지에서 작업 상태가 **완료**로 표시 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="e126f-118">**2 단계: 비즈니스용 Skype 서버 구성 요소 설정 또는 제거**에서 **실행**을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="e126f-119">**명령 실행** 페이지에서 작업 상태가 **완료**로 표시 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="e126f-120">**3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="e126f-121">화면에 나타나는 지시에 따라 기본 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="e126f-122">중재 서버에는 하나의 인증서가 필요 하므로 **3 단계** 를 두 번 (필요한 인증서를 발급 하기 위해 한 번) 한 번 실행 하 고 더 많은 작업을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="e126f-123">인증서가 올바르게 발급 되 고 지정 된 경우 **4 단계: 서비스 시작**, **실행**을 차례로 클릭 한 다음 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="e126f-124">**4 단계가** 성공적으로 완료 되 면 서버를 다시 시작 하 고 서버에 domainadmins 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="e126f-125">비즈니스용 Skype Server 제어판을 실행 중인 컴퓨터에서 조정 서버의 서비스 상태가 녹색 확인 표시로 표시 되는 비즈니스용 Skype Server 제어판의 **토폴로지** 페이지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="e126f-126">대신 빨간색 X가 나타나면 중재 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="e126f-127">**작업** 메뉴에서 **모든 서비스 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="e126f-128">중재 서버 풀에 둘 이상의 컴퓨터를 추가한 경우 조정 서버 풀의 다른 모든 컴퓨터에서이 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e126f-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="e126f-129">다른 컴퓨터에 대 한 중재 서버용 파일을 설치할 필요가 없는 경우 [비즈니스용 Skype Server에서 Trunks 구성](configure-trunks.md) 의 절차에 따라이 중재 서버 풀 간의 트렁크 연결에 대 한 설정을 구성 합니다 (또는 모두 중재). 사이트의 서버) 및 해당 피어.</span><span class="sxs-lookup"><span data-stu-id="e126f-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

