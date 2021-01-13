---
title: 프런트 엔드 모니터링 저장소 추가 페이지
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
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 다음 속성을 구성하여 모니터링 SQL Server 저장소 정의를 수행합니다.
ms.openlocfilehash: 5f8a3ccb22aea1efde0b214b9afa61c140e63014
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803548"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="8dd1e-103">프런트 엔드 모니터링 저장소 추가 페이지</span><span class="sxs-lookup"><span data-stu-id="8dd1e-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="8dd1e-104">다음 속성을 구성하여 **모니터링 SQL Server 저장소 정의** 를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="8dd1e-105">**저장소 SQL Server** 모니터링: 목록에서 SQL Server 도메인 이름 및 인스턴스(선택 사항)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="8dd1e-106">새  FQDN 정의를 SQL Server 모니터링 서버 저장소의 인스턴스 이름을 선택적으로 만들려면 새로 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="8dd1e-107">모니터링 서버에 **SQL Server** 미러링을 추가하려면 저장소 미러링 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="8dd1e-108">목록에서 기존 **모니터링 SQL Server 저장소 미러** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="8dd1e-109">새  FQDN 정의를 SQL Server 미러 저장소의 인스턴스 이름을 선택적으로 만들려면 새로 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="8dd1e-110">저장소 미러링 SQL Server 사용하도록 설정한 경우 선택적으로 SQL Server 미러링 미러링을 사용하여 자동 장애 조치(failover)를 사용하도록 설정하여 목록에서 SQL Server 미러링된 미러링 SQL Server 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="8dd1e-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="8dd1e-111">새로 **만들기를** 클릭하여 새 FQDN SQL Server 미러링된 미러링된 저장소의 인스턴스 이름을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="8dd1e-112">이전 풀 정의 대화 상자로 돌아가려면 **뒤로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="8dd1e-113">이 대화 상자의 옵션을 모두 입력한 후 구성을 계속하려면 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="8dd1e-114">모든 변경 내용을 취소하고 마법사를 종료하려면 **취소** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="8dd1e-115">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd1e-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8dd1e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dd1e-116">See also</span></span>

[<span data-ttu-id="8dd1e-117">비즈니스용 Skype 서버 2015에서 모니터링 저장소를 프런트 엔드 풀과 연결</span><span class="sxs-lookup"><span data-stu-id="8dd1e-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
