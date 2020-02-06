---
title: 등록자 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 탄력성은 레지스트라 풀에 대 한 고가용성 및 재해 복구를 제공 합니다. 기본 등록 기관에 장애가 발생 했을 때 백업 등록 기관을 제공 하 여, 백업 등록 자가 실패 등록자에 대해 조치를 취하여 사용자가 로그온 하 고 통신할 수 있도록 합니다. 사용자는 기본 등록 기관에서 실패 한 시스템에 따라 기능을 저하 시킬 수 있습니다.
ms.openlocfilehash: b6dd5fac05b4692e8f30f1063ab71b1bad02d810
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797239"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="8a8c8-105">등록자 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="8a8c8-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="8a8c8-106">탄력성은 레지스트라 풀에 대 한 고가용성 및 재해 복구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="8a8c8-107">기본 등록 기관에 장애가 발생 했을 때 백업 등록 기관을 제공 하 여, 백업 등록 자가 실패 등록자에 대해 조치를 취하여 사용자가 로그온 하 고 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="8a8c8-108">사용자는 기본 등록 기관에서 실패 한 시스템에 따라 기능을 저하 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="8a8c8-109">Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 **속성 편집** 대화 상자의 **복원** 구역에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="8a8c8-110">**연결 된 사용자 서비스 및 백업 등록자 풀** 드롭다운 목록에서 Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 백업 등록 기관 역할을 하는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="8a8c8-111">**장애 조치와 장애 복구 사용** 이 설정을 선택 하면 실패 한 등록자를 자동으로 검색 하 고, 기본 등록 기관에서 백업 하 고 등록자 프로세스를 다시 시작할 준비가 되었다는 자동 결정을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="8a8c8-112">**실패 검색 간격 (초)** 기본 등록 기관에 오류가 발생 하는 것으로 확인 되기까지 경과 되는 시간을 초 단위로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="8a8c8-113">기본값은 120 초입니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-113">The default value is 120 seconds.</span></span> <span data-ttu-id="8a8c8-114">**장애 조치 및 장애 복구 사용**을 선택 하는 경우이 필드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="8a8c8-115">**대체 검색 간격 (초)** 기본 등록자를 백업 하는 것으로 확인 되기까지 경과 되는 시간을 초 단위로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="8a8c8-116">기본값은 240 초입니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-116">The default value is 240 seconds.</span></span> <span data-ttu-id="8a8c8-117">**장애 조치 및 대체 사용을**선택 하는 경우이 필드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8a8c8-118">실패 검색 간격과 대체 검색 간격을 정의 하는 경우, 등록 자가 짧은 시간 동안 응답 하지 못하는 경우 장애 조치 및 fallback이 발생 하는 간격을 입력 하지 않도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="8a8c8-119">기본 등록 자가 풀 또는 서버의 로드에 따라 짧은 시간 동안 응답 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8c8-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

