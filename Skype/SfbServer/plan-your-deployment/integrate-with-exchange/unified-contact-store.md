---
title: 비즈니스용 Skype 서버의 통합 연락처 저장소 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '요약: 비즈니스용 Skype 서버와 Exchange 2013의 통합을 계획하는 동안 이 항목을 검토합니다.'
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816258"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="adc92-103">비즈니스용 Skype 서버 2015의 통합 연락처 저장소 계획</span><span class="sxs-lookup"><span data-stu-id="adc92-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="adc92-104">**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016의 통합을 계획하는 동안 이 항목을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="adc92-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="adc92-105">통합 연락처 저장소는 여러 Microsoft Office 일관된 연락처 환경을 제공하며 사용자는 Exchange 2013에 모든 연락처 정보를 저장할 수 있지만 비즈니스용 Skype, Exchange, Outlook 및 Outlook Web Access에서 정보를 전역적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc92-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="adc92-106">통합 연락처 저장소에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="adc92-106">Requirements for unified contact store</span></span>

<span data-ttu-id="adc92-107">비즈니스용 Skype 서버에서 통합 연락처 저장소를 구현하는 경우:</span><span class="sxs-lookup"><span data-stu-id="adc92-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="adc92-108">비즈니스용 Skype 서버 및 Exchange 2013 또는 2016을 실행하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc92-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="adc92-109">사용자는 비즈니스용 Skype를 사용하여 비즈니스용 Skype 서버에서 Exchange 2013 또는 2016으로 연락처를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc92-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="adc92-110">사용자 사서함은 Exchange 2013으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc92-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="adc92-111">비즈니스용 Skype 서버와 Exchange 2013 또는 2016 간에 서버 간 인증을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc92-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="adc92-112">비즈니스용 Skype 서버와 Exchange 2013 또는 2016 간의 인증 설정에 대한 자세한 요구 사항은 작업 설명서에서 비즈니스용 Skype 서버의 서버 간 [인증(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) 및 파트너 응용 프로그램 관리를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="adc92-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="adc92-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adc92-113">See also</span></span>

[<span data-ttu-id="adc92-114">비즈니스용 Skype 서버에서 통합 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="adc92-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
