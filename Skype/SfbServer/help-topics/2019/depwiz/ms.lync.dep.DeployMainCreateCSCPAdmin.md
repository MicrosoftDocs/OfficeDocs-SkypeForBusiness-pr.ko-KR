---
title: 비즈니스용 Skype 서버 제어판 관리자 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버에 대한 액세스 권한을 부여하기 위해 다음을 실행합니다.
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824968"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="d0c3b-103">비즈니스용 Skype 서버 제어판 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="d0c3b-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="d0c3b-104">비즈니스용 Skype 서버에 대한 액세스 권한을 부여하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="d0c3b-105">Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d0c3b-106">**Active Directory 사용자 및 컴퓨터** 를 열고 도메인을 확장한 다음 **사용자** 컨테이너를 마우스 오른쪽 단추로 클릭하고 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="d0c3b-107">**CSAdministrator 속성** 에서 **구성원** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="d0c3b-p101">구성원 탭에서 **추가** 를 클릭합니다. **사용자, 연락처, 컴퓨터, 서비스 계정 또는 그룹 선택** 에서 **선택할 개체 이름을 입력하십시오.** 를 찾습니다. CSAdministrators 그룹에 추가할 사용자 이름 또는 그룹 이름을 입력합니다. **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="d0c3b-p102">구성원 탭에서 선택한 사용자 또는 그룹이 있는지 확인합니다. **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="d0c3b-114">비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="d0c3b-115">CsAdministrator 그룹의 구성원 자격은 비즈니스용 Skype 서버 제어판을 사용하는 사용자에게 사용 가능한 모든 구성 기능에 대한 모든 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="d0c3b-116">특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="d0c3b-117">사용자가 관리 그룹의 구성원으로 설정하기 위해 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="d0c3b-118">기타 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-118">Other roles include:</span></span>
  
- <span data-ttu-id="d0c3b-119">**CsArchiving:** 이 그룹의 구성원은 보관 서버 역할 구성 및 관리와 같은 모든 보관 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="d0c3b-p104">**CsHelpDesk:** 이 그룹의 구성원은 사용자 속성 및 정책을 비롯한 구성과 배포를 볼 수 있습니다. 또한 구성원은 특정 문제 해결 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="d0c3b-p105">**CsLocationAdministrator:** 구성원은 E9-1-1(고급 9-1-1) 관리와 관련된 가장 낮은 수준의 사용자 권한을 가집니다. 구성원은 E9-1-1 위치 및 네트워크 식별자를 만들고 배포에서 이들을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="d0c3b-124">**CsResponseGroupAdministrator:** 구성원은 응답 그룹 서비스를 관리 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="d0c3b-125">**CsServerAdministrator:** 구성원은 비즈니스용 Skype 서버를 실행하는 모든 서버를 관리, 모니터링 및 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="d0c3b-126">**CsUserAdministrator:** 구성원은 사용자를 관리, 사용하도록 설정 및 사용하지 않도록 설정하고 사용자에게 기존 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="d0c3b-127">**CsViewOnlyAdministrator:** 구성원은 서버 정보의 배포 및 구성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="d0c3b-128">이 멤버 자격을 사용하면 구성원이 비즈니스용 Skype 서버를 실행하는 서버의 상태 모니터링을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="d0c3b-129">**CsVoiceAdministrator:** 구성원은 비즈니스용 Skype 서버에서 음성 관련 설정을 만들고 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="d0c3b-130">보안 및 역할 기반 액세스 제어 무결성을 유지 관리하기 위해 사용자가 비즈니스용 Skype 서버 배포 관리에서 수행하는 역할을 정의하는 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0c3b-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

