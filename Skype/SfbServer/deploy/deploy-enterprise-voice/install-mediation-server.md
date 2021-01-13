---
title: 비즈니스용 Skype 서버에 중재 서버용 파일 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '요약: 비즈니스용 Skype 서버에서 중재 서버용 파일을 설치하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830798"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="54d73-103">비즈니스용 Skype 서버에 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="54d73-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="54d73-104">**요약:** 비즈니스용 Skype 서버에서 중재 서버용 파일을 설치하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="54d73-105">이 절차를 성공적으로 완료하려면 최소한 로컬 관리자 및 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 도메인 사용자로 서버에 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="54d73-106">이 항목의 단계에 따라 비즈니스용 Skype 서버 배포 마법사를 실행하여 토폴로지 작성기에서 풀을 정의하고 게시한 후 중재 서버 풀에 추가한 컴퓨터에 중재 서버용 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="54d73-107">중재 서버 파일을 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서도 설치하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="54d73-108">이 항목에서는 비즈니스용 [Skype](deploy-a-mediation-server.md)서버의 토폴로지 작성기에서 중재 서버 배포에 설명된 바와 같이 토폴로지에서 독립 실행형 중재 서버 풀을 이미 정의하고 게시했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="54d73-109">독립 실행형 중재 서버 풀에 대한 파일을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="54d73-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="54d73-110">설치 미디어에서 마우스 오른쪽 단추로\Setup\amd64\Setup.exe관리자 _\<installation media\>_ \*\*\*\* **권한으로 실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="54d73-111">설치 **위치 페이지에서** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="54d73-112">최종 **사용자 사용권** 계약 페이지에서 동의를 **클릭한** 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="54d73-113">(계속하려면 필요합니다.)</span><span class="sxs-lookup"><span data-stu-id="54d73-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="54d73-114">비즈니스용 **Skype 서버** 배포 마법사 페이지에서 비즈니스용 Skype 서버 시스템 설치 또는 **업데이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="54d73-115">**1단계 옆: 로컬** 구성 저장소 설치, **실행을** 클릭한 다음 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="54d73-116">중앙 관리 **저장소의 로컬 복제본** 구성 페이지에서 중앙 관리 저장소에서 직접 기본 검색을 적용하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="54d73-117">명령 실행 **페이지에서** 작업 상태가 **완료된** 것으로 표시되면 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="54d73-118">**2단계:** 비즈니스용 Skype 서버 구성 요소 설치 또는 제거 옆에 있는 **실행을** 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="54d73-119">명령 실행 **페이지에서** 작업 상태가 **완료된** 것으로 표시되면 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="54d73-120">**3단계:** 인증서 요청, 설치 또는 할당 옆에 있는 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="54d73-121">기본 설정을 수락하여 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="54d73-122">중재 서버에는 하나의 인증서가 필요하며, 따라서 **3단계를** 두 번 실행합니다. 한 번은 필수 인증서를 발급하고 한 번 더 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="54d73-123">인증서가 발급되고 올바르게 할당되면 **4단계:** 서비스 시작, 실행을 클릭한 다음 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="54d73-124">**4단계가** 성공적으로 완료되면 서버를 다시 시작하고 DomainAdmins 그룹의 구성원으로 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="54d73-125">비즈니스용 Skype 서버 제어판을 실행하는 컴퓨터에서 비즈니스용  Skype 서버 제어판의 토폴로지 페이지에서 중재 서버의 서비스 상태가 녹색 확인 표시로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="54d73-126">빨간색 X가 나타나면 중재 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="54d73-127">작업 **메뉴에서** 모든 서비스 **시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54d73-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="54d73-128">중재 서버 풀에 컴퓨터를 두 대 이상 추가한 경우 중재 서버 풀의 다른 모든 컴퓨터에서 이 절차의 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="54d73-129">다른 컴퓨터의 중재 서버에 대한 파일을 설치할 필요가 없는 경우 비즈니스용 [Skype](configure-trunks.md) 서버의 트렁크 구성 절차에 따라 이 중재 서버 풀(또는 사이트의 모든 중재 서버)와 피어 간의 트렁크 연결에 대한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="54d73-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

