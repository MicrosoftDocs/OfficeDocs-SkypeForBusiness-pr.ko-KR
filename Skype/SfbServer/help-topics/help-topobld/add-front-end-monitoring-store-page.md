---
title: 프론트 엔드 모니터링 저장소 페이지 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 다음 속성을 구성 하 여 모니터링 SQL Server 저장소를 정의 합니다.
ms.openlocfilehash: 789083ad0743ed7baf94630c86e4647e218c336c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820860"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="588ac-103">프론트 엔드 모니터링 저장소 페이지 추가</span><span class="sxs-lookup"><span data-stu-id="588ac-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="588ac-104">다음 속성을 구성 하 여 **모니터링 SQL Server 저장소를 정의 합니다** .</span><span class="sxs-lookup"><span data-stu-id="588ac-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="588ac-105">**Sql server 스토어 모니터링**: 목록에서 sql server의 정규화 된 도메인 이름 (및 선택적으로 인스턴스)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="588ac-106">**새로** 만들기를 클릭 하 여 SQL Server의 새 FQDN 정의 및 선택적으로 모니터링 서버 저장소에 대 한 인스턴스 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="588ac-107">모니터링 서버에 대 한 데이터베이스 미러링을 추가 하려면 **SQL Server 스토어 미러링 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="588ac-108">목록에서 기존 **모니터링 SQL Server 저장소 미러** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="588ac-109">**새로** 만들기를 클릭 하 여 새 SQL Server FQDN 정의를 만들고 선택적으로 미러 저장소의 인스턴스 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="588ac-110">**Sql server store 미러링 사용**을 선택한 경우 선택적으로 **sql server 미러링 미러링 모니터 사용** 을 선택 하 여 자동 장애 조치를 사용 하도록 설정 하 여 목록에서 sql server 미러링 감시 저장소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="588ac-111">**새로** 만들기를 클릭 하 여 새 SQL Server FQDN 정의를 만들고 선택적으로 미러링 감시 저장소에 대 한 인스턴스 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="588ac-112">이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="588ac-113">이 대화 상자에 대 한 옵션을 모두 입력 하 고 구성을 진행 하는 과정을 완료 한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="588ac-114">모든 변경 내용을 취소 하 고 마법사를 종료 하려면 **취소** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="588ac-115">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="588ac-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="588ac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="588ac-116">See also</span></span>

[<span data-ttu-id="588ac-117">비즈니스용 Skype 서버 2015의 프런트 엔드 풀에 모니터링 저장소 연결</span><span class="sxs-lookup"><span data-stu-id="588ac-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
