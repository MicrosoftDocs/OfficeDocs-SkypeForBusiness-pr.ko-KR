---
title: 영구 채팅 관리자 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 요약:이 항목을 읽으면 비즈니스용 Skype Server 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용 하도록 설정 하는 영구 채팅 서버 관리자 역할을 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3692169a65d73c3951ce58e77b132a4f118c54e9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239772"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="afd6b-103">영구 채팅 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="afd6b-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="afd6b-104">**요약:** 이 항목을 읽으면 비즈니스용 Skype Server 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용 하도록 설정 하는 영구 채팅 서버 관리자 역할을 만드는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="afd6b-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="afd6b-105">비즈니스용 Skype Server에서 특정 작업을 수행 하는 사용자는 하나 이상의 특정 그룹의 구성원으로 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="afd6b-106">사용자를 미리 정의 된 비즈니스용 Skype 서버 관리 역할에 할당 하 여 권한을 부여 하는 데는 RBAC (역할 기반 액세스 제어)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="afd6b-107">이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="afd6b-108">영구 채팅 관리자 보안 그룹의 구성원에 게는 비즈니스용 skype 서버 관리 셸 또는 비즈니스용 Skype를 사용 하 여 실행할 수 있는 영구 채팅 서버 cmdlet에 대 한 액세스 권한이 부여 됩니다. CsPersistentChatAdministrator 서버 제어판.</span><span class="sxs-lookup"><span data-stu-id="afd6b-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="afd6b-109">영구 채팅 서버를 구성 하 고 관리 하기 전에 적절 한 사용자 권한 및 사용 권한이 있는지 확인 하 고 영구 채팅 관리자의 역할을 하는 사용자가 영구 채팅 관리자 보안 그룹에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="afd6b-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="afd6b-111">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="afd6b-112">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd6b-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="afd6b-113">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="afd6b-114">영구 채팅 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="afd6b-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="afd6b-115">영구 채팅 관리자 보안 그룹 CsPersistentChatAdministrator에 사용자를 추가 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="afd6b-116">Active Directory 그룹의 구성원 자격을 수정할 권한이 있는 계정을 사용 하 여 Active Directory 사용자 및 컴퓨터가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="afd6b-117">시작을 클릭 하 고 모든 프로그램을 클릭 한 다음 관리 도구를 클릭 하 고 Active Directory 사용자 및 컴퓨터를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="afd6b-118">Active Directory 사용자 및 컴퓨터에서 도메인의 이름을 확장 하 고 사용자 컨테이너를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="afd6b-119">보안 그룹 CsPersistentChatAdministrator을 마우스 오른쪽 단추로 클릭 한 다음 속성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="afd6b-120">속성 대화 상자의 구성원 탭에서 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="afd6b-121">사용자, 컴퓨터, 연락처 또는 그룹 선택 대화 상자에서 선택할 개체 이름 입력 상자에 그룹에 추가할 사용자의 사용자 이름 또는 표시 이름을 입력 하 고 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="afd6b-122">속성 대화 상자에서 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd6b-122">In the Properties dialog box, click OK.</span></span>
    

