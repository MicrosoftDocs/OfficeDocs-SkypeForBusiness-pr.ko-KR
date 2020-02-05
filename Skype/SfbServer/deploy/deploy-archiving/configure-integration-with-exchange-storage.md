---
title: 비즈니스용 Skype 서버에 Exchange 저장소 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '요약: 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: cee41a52593a90490ec8da90637ee4ec5de33d03
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768891"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="1a1f1-103">비즈니스용 Skype 서버에 Exchange 저장소 통합 구성</span><span class="sxs-lookup"><span data-stu-id="1a1f1-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="1a1f1-104">**요약:** 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="1a1f1-105">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자 용 비즈니스용 Skype Server 보관 정책을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="1a1f1-106">대신 Exchange에 있는 사용자의 보관을 지원 하도록 Exchange 원본 위치 유지 정책을 구성 하면 해당 사서함이 원본 위치 유지에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="1a1f1-107">Exchange 저장소와의 통합을 구성 하기 전에 [비즈니스용 Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)읽기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="1a1f1-108">Exchange 원본 위치 유지 정책에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="1a1f1-109">Microsoft Exchange 저장소와 통합 구성</span><span class="sxs-lookup"><span data-stu-id="1a1f1-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="1a1f1-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a1f1-111">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1a1f1-112">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="1a1f1-113">보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="1a1f1-114">Exchange 저장소와의 통합을 사용 하도록 설정 하려면 **Microsoft Exchange 통합** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="1a1f1-115">Exchange 저장소와의 통합을 사용 하지 않도록 설정 하려면 **Microsoft Exchange 통합** 확인란을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="1a1f1-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="1a1f1-117">비즈니스용 Skype 서버와 Microsoft Exchange가 서로 다른 포리스트에 배포 되는 경우</span><span class="sxs-lookup"><span data-stu-id="1a1f1-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="1a1f1-118">Microsoft Exchange 통합을 사용 하는 경우 Microsoft Exchange Server가 비즈니스용 Skype 서버와 동일한 포리스트에 배포 되지 않은 경우 다음 Exchange Active Directory 특성이 포리스트에 대 한 Skype와 동기화 되었는지 확인 해야 합니다. 비즈니스 서버 배포 됨:</span><span class="sxs-lookup"><span data-stu-id="1a1f1-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="1a1f1-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="1a1f1-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="1a1f1-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1a1f1-120">proxyAddresses</span></span>
    
<span data-ttu-id="1a1f1-121">이것은 다중 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-121">This is a multi-value attribute.</span></span> <span data-ttu-id="1a1f1-122">이 특성을 동기화 할 때 기존 값이 손실 되지 않도록 값을 바꾸지 않고 병합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1f1-122">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

