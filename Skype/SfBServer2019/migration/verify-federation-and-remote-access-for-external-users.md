---
title: 외부 사용자를 위한 페더레이션 및 원격 액세스 확인
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
description: 페더레이션 경로를 비즈니스용 Skype 서버 2019에 지 서버로 전환 하 고 나면 일부 기능 테스트를 수행 하 여 페더레이션이 예상 대로 수행 되는지 확인 해야 합니다. 외부 사용자 액세스를 위한 테스트에는 다음 중 일부 또는 모두를 포함하여 조직에서 지원하는 각각의 외부 사용자 유형이 포함됩니다.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751670"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="d56ae-104">외부 사용자를 위한 페더레이션 및 원격 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="d56ae-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="d56ae-105">페더레이션 경로를 비즈니스용 Skype 서버 2019에 지 서버로 전환 하 고 나면 일부 기능 테스트를 수행 하 여 페더레이션이 예상 대로 수행 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="d56ae-106">외부 사용자 액세스를 위한 테스트에는 다음 중 일부 또는 모두를 포함하여 조직에서 지원하는 각각의 외부 사용자 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="d56ae-107">외부 사용자 및 외부 액세스 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="d56ae-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="d56ae-108">하나 이상의 페더레이션 도메인, 비즈니스용 Skype 서버 2019의 내부 사용자 및 레거시 설치의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d56ae-109">IM(인스턴트 메시징), 현재 상태, A/V(오디오/비디오) 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="d56ae-110">조직이 지원 하 고 프로 비전이 완료 된 각 공용 IM 서비스 공급자의 사용자가 비즈니스용 Skype 서버 2019 및 레거시 설치에서 사용자와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="d56ae-111">익명 사용자가 회의에 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="d56ae-112">원격 사용자 액세스를 사용 하 여 레거시 설치에서 호스트 되는 사용자 (VPN 제외)는 비즈니스용 Skype 서버 2019 및 레거시 설치 사용자에 대 한 사용자의 로그인입니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d56ae-113">IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="d56ae-114">비즈니스용 skype 서버 2019에 사용자가 있고, VPN을 사용 하지 않고 인트라넷 외부에서 비즈니스용 Skype 서버 2019에 로그인 하 여 비즈니스용 skype 서버 2019에 호스트 되는 사용자와 레거시 설치의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d56ae-115">IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d56ae-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

