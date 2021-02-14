---
title: 등록자 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818298"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="a5f4b-105">등록자 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="a5f4b-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="a5f4b-p102">탄성은 등록자 풀에 대해 고가용성 및 재해 복구를 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 실패한 시스템에 따라 잠재적으로 사용할 수 있는 기능이 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="a5f4b-109">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 **속성 편집** 대화 상자에 있는 **복구** 섹션에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="a5f4b-110">**연결된 사용자 서비스 및 백업 등록자 풀** 드롭다운 목록에서 Survivable Branch Appliance 또는 Survivable Branch Server의 백업 등록자 역할을 할 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="a5f4b-111">**장애 조치(Failover) 및 장애 조치(Failback) 사용** 실패한 등록자 자동 검색 및 기본 등록자가 백업되어 등록자 프로세스를 다시 시작할 준비가 되어 있는 자동 확인을 허용하려면 이 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="a5f4b-112">**오류 검색 간격(초)** 기본 등록자가 실패한 것으로 결정되기 전에 경과해야 하는 시간(초)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="a5f4b-113">기본값은 120초입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-113">The default value is 120 seconds.</span></span> <span data-ttu-id="a5f4b-114">장애 조치(failover) 및 장애 **조치(Failback) 사용(Failback)을** 선택하는 경우 이 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="a5f4b-115">**폴백 검색 간격(초)** 기본 등록자가 백업된 것으로 결정되기 전에 경과해야 하는 시간(초)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="a5f4b-116">기본값은 240초입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-116">The default value is 240 seconds.</span></span> <span data-ttu-id="a5f4b-117">장애 조치(Failover) 및 Fallback 사용(Fallback)을 선택하는 경우 이 **필드가 필요합니다.**</span><span class="sxs-lookup"><span data-stu-id="a5f4b-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a5f4b-p105">실패 검색 및 대체 검색 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 발생하지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f4b-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

