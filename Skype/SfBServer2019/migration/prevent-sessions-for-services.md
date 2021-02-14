---
title: 서비스에 대한 세션 방지
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 설치 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 레거시 서비스에 대한 새 세션을 방지하거나 특정 레거시 서비스에 대한 새 세션을 방지할 수 있습니다.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752290"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="b9a65-103">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="b9a65-103">Prevent sessions for services</span></span>

<span data-ttu-id="b9a65-104">레거시 설치 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 레거시 서비스에 대한 새 세션을 방지하거나 특정 레거시 서비스에 대한 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="b9a65-105">컴퓨터에서 서비스에 대한 새 세션을 방지하려면</span><span class="sxs-lookup"><span data-stu-id="b9a65-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="b9a65-106">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버 2019를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="b9a65-107">비즈니스용 Skype 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="b9a65-108">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="b9a65-109">**상태** 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="b9a65-110">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="b9a65-111">**모든 서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="b9a65-112">특정 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="b9a65-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="b9a65-113">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버 2019를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="b9a65-114">비즈니스용 Skype 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="b9a65-115">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="b9a65-116">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="b9a65-117">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="b9a65-118">필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="b9a65-119">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="b9a65-120">**서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="b9a65-121">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a65-121">Click **Close**.</span></span>
    

