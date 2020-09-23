---
title: 등록자 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 탄성은 등록자 풀에 대해 고가용성 및 재해 복구를 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 실패한 시스템에 따라 잠재적으로 사용할 수 있는 기능이 축소될 수 있습니다.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217159"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="192d1-105">등록자 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="192d1-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="192d1-p102">탄성은 등록자 풀에 대해 고가용성 및 재해 복구를 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 실패한 시스템에 따라 잠재적으로 사용할 수 있는 기능이 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="192d1-109">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 **속성 편집** 대화 상자에 있는 **복구** 섹션에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="192d1-110">**연결 된 사용자 서비스 및 백업 등록자 풀** 드롭다운 목록에서 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에 대 한 백업 등록자 역할을 할 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="192d1-111">**장애 조치 (Failover) 및 장애 복구 사용** 오류가 발생 한 등록자를 자동으로 감지 하 고 기본 등록 자가 백업 하 고 등록자 프로세스를 다시 시작할 준비가 되었음을 자동으로 확인 하려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="192d1-112">**실패 검색 간격 (초)** 기본 등록 자가 실패 한 것으로 확인 되기 전까지 경과 해야 하는 시간을 초 단위로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="192d1-113">기본값은 120초입니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-113">The default value is 120 seconds.</span></span> <span data-ttu-id="192d1-114">이 필드는 **장애 조치 (Failover) 및 장애 복구 사용**을 선택 하는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="192d1-115">**대체 검색 간격 (초)** 기본 등록 자가 백업 됨을 확인 하기 전에 경과 해야 하는 시간 (초)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="192d1-116">기본값은 240 초입니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-116">The default value is 240 seconds.</span></span> <span data-ttu-id="192d1-117">**장애 조치 (Failover) 및 대체 사용**을 선택 하는 경우이 필드는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="192d1-p105">실패 검색 및 대체 검색 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 발생하지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192d1-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

