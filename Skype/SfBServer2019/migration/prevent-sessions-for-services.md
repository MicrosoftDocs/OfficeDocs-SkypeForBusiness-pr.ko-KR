---
title: 서비스에 대 한 세션 방지
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 설치 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 레거시 서비스에 대 한 새 세션을 방지 하거나 특정 레거시 서비스에 대 한 새 세션을 방지할 수 있습니다.
ms.openlocfilehash: 4728f68c8f7b9392b99a6a49eefe699fa48a4d47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197186"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="cb9a5-103">서비스에 대 한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="cb9a5-103">Prevent sessions for services</span></span>

<span data-ttu-id="cb9a5-104">레거시 설치 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 레거시 서비스에 대 한 새 세션을 방지 하거나 특정 레거시 서비스에 대 한 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="cb9a5-105">컴퓨터에서 서비스에 대 한 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="cb9a5-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="cb9a5-106">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. 2019.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="cb9a5-107">비즈니스용 Skype 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="cb9a5-108">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="cb9a5-109">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 새 세션을 방지 하려는 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="cb9a5-110">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="cb9a5-111">**모든 서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="cb9a5-112">특정 서비스에 대 한 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="cb9a5-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="cb9a5-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. 2019.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="cb9a5-114">비즈니스용 Skype 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="cb9a5-115">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="cb9a5-116">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="cb9a5-117">**속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="cb9a5-118">필요한 경우 서비스 목록을 정렬 하 고 새 세션을 방지 하려는 서비스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="cb9a5-119">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="cb9a5-120">**서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="cb9a5-121">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a5-121">Click **Close**.</span></span>
    

