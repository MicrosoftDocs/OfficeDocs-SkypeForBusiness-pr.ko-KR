---
title: 비즈니스용 Skype 서버와 비즈니스용 Skype Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에 대한 통합 단계를 검토합니다.'
ms.openlocfilehash: 6b5c63c0ad6783c11fd8fde25d1b00dc84d7e15a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833738"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="a8a01-103">비즈니스용 Skype 서버와 비즈니스용 Skype Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a8a01-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="a8a01-104">**요약:** Exchange Server 2013 이상 및 비즈니스용 Skype 서버에 대한 통합 단계를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a01-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="a8a01-105">Exchange Server 2013 이상 및 비즈니스용 Skype 서버는 호환 및 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8a01-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="a8a01-106">예를 들어 비즈니스용 Skype 사용자 현재 상태 정보는 Microsoft Outlook에서 보고할 수 있습니다. 마찬가지로 비즈니스용 Skype는 사용자의 Outlook 일정에 액세스하고, 사용자가 모임을 예약하고, 모임 중에 사용자의 현재 상태는 다른 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8a01-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="a8a01-107">비즈니스용 Skype 서버를 Exchange Server 실행하기 위해 두 제품을 함께 실행하면 서로의 사용자 환경이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8a01-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="a8a01-108">이 설명서에서는 비즈니스용 Skype 서버와 Exchange Server 2016 또는 Exchange Server 2013을 통합하는 데 대한 정보를 제공하지만 이러한 두 제품의 초기 설정 및 구성이 이미 발생했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a01-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="a8a01-109">비즈니스용 Skype 서버 배포에 대한 자세한 내용은 비즈니스용 [Skype 서버 기술 센터를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=246127)</span><span class="sxs-lookup"><span data-stu-id="a8a01-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="a8a01-110">배포에 대한 자세한 Exchange Server Exchange 버전에 대한 배포 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8a01-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="a8a01-111">비즈니스용 Skype 서버의 프레미스 설치를 비즈니스용 Skype 서버와 통합하는 Microsoft Exchange Online 비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 통합 [구성을](outlook-web-app.md)Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="a8a01-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="a8a01-112">비즈니스용 Skype Online과 비즈니스용 Skype online을 Exchange Server 비즈니스용 Skype Online과 Exchange on premises 간에 OAuth 구성을 [참조하세요.](oauth-with-online-and-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="a8a01-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a8a01-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a8a01-113">In this section</span></span>

[<span data-ttu-id="a8a01-114">비즈니스용 Skype 서버 및 2016에서 파트너 응용 프로그램 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a8a01-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="a8a01-115">비즈니스용 Skype 서버가 보관을 사용하도록 Exchange Server 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="a8a01-116">보관된 비즈니스용 Skype 데이터를 검색하도록 SharePoint Server 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="a8a01-117">통합 연락처 저장소를 사용하도록 비즈니스용 Skype 서버 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="a8a01-118">비즈니스용 Skype 서버에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="a8a01-119">비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="a8a01-120">비즈니스용 Skype 서버 및 Microsoft Outlook Web App 2013 통합</span><span class="sxs-lookup"><span data-stu-id="a8a01-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="a8a01-121">비즈니스용 Skype 서버의 클라이언트 컴퓨터에서 개인 연락처 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="a8a01-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="a8a01-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8a01-122">See also</span></span>

[<span data-ttu-id="a8a01-123">비즈니스용 Skype 및 Exchange 통합 계획</span><span class="sxs-lookup"><span data-stu-id="a8a01-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
