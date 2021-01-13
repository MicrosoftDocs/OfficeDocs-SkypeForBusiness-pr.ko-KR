---
title: 비즈니스용 Skype 서버에서 영구 채팅 관리자 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '요약: 이 항목을 통해 영구 채팅 서버 관리자 역할을 만들어 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용하도록 설정하는 방법을 배울 수 있습니다.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802098"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="14c2a-103">비즈니스용 Skype 서버에서 영구 채팅 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="14c2a-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14c2a-104">**요약:** 이 항목을 통해 영구 채팅 서버 관리자 역할을 만들어 비즈니스용 Skype 서버 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용하도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="14c2a-105">비즈니스용 Skype 서버에서는 특정 작업을 수행하는 사용자를 하나 이상의 특정 그룹의 구성원으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="14c2a-106">Role-Based 액세스 제어(RBAC)는 사용자를 미리 정의한 비즈니스용 Skype 서버 관리 역할에 할당하여 권한을 부여하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="14c2a-107">이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="14c2a-108">영구 채팅 관리자 보안 그룹인 CsPersistentChatAdministrator의 구성원에게는 영구 채팅 서버 cmdlet에 대한 액세스 권한이 부여됩니다. 영구 채팅 서버 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 제어판을 사용하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="14c2a-109">영구 채팅 서버를 구성 및 관리하기 전에 적절한 사용자 권한 및 사용 권한이 설정되고 영구 채팅 관리자로 사용할 모든 사용자가 영구 채팅 관리자 보안 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="14c2a-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="14c2a-111">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="14c2a-112">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="14c2a-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="14c2a-113">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="14c2a-114">영구 채팅 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="14c2a-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="14c2a-115">영구 채팅 관리자 보안 그룹인 CsPersistentChatAdministrator에 사용자를 추가하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="14c2a-116">Active Directory 그룹의 구성원 자격을 수정할 수 있는 권한이 있는 계정을 사용하여 Active Directory 사용자 및 컴퓨터가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="14c2a-117">시작, 모든 프로그램, 관리 도구를 클릭한 다음 Active Directory 사용자 및 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="14c2a-118">Active Directory 사용자 및 컴퓨터에서 도메인 이름을 확장하고 Users 컨테이너를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="14c2a-119">보안 그룹 CsPersistentChatAdministrator를 마우스 오른쪽 단추로 클릭한 다음 속성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="14c2a-120">속성 대화 상자의 구성원 탭에서 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="14c2a-121">사용자, 컴퓨터, 연락처 또는 그룹 선택 대화 상자에서 개체 이름 입력 상자에 그룹에 추가할 사용자의 사용자 이름 또는 표시 이름을 입력하고 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="14c2a-122">속성 대화 상자에서 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14c2a-122">In the Properties dialog box, click OK.</span></span>
    

