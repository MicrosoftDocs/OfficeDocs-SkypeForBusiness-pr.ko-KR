---
title: Exchange Online에서 허용 된 보낸 사람 도메인으로 팀 SMTP 도메인 추가
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: 팀 구성원에 게 알림을 보내기 위해 Exchange Online에서 허용 된 보낸 사람 도메인으로 Microsoft 팀 SMTP 도메인을 추가 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582055"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="478c6-103">Exchange Online에서 Microsoft 팀 SMTP 도메인을 허용 된 보낸 사람 도메인으로 추가</span><span class="sxs-lookup"><span data-stu-id="478c6-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="478c6-104">관리 콘솔에서 Microsoft 365 그룹을 만들거나 Outlook을 사용 하는 경우 Exchange Online은 그룹에 추가 되는 팀 구성원의 알림을 보내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c6-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="478c6-105">이러한 메시지는 사용자의 기본 도메인 SMTP FQDN을 나타내므로 테 넌 트에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c6-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![그룹에 추가 된 사용자를 보여 주는 메시지 머리글의 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="478c6-107">팀에서 Microsoft Exchange Online을 사용 하는 것은 물론, 추가 된 구성원에 게 알림을 보내는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="478c6-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="478c6-108">SMTP 메시지의 도메인 FQDN에 대 한 차이점은 상업용/비즈니스 테 넌 트에 대 한 @email "teams.microsoft.com"이 고, 정부 테 넌 트의 경우 "@GCC-email.teams.microsoft.com"이 고 스팸 필터링을 통해이를 찾아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478c6-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![그룹에 추가 된 사용자를 보여 주는 메시지 머리글의 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="478c6-110">최상의 결과와 원활한 작업을 위해서는 Exchange Online 스팸 구성에서 Microsoft 팀 SMTP 도메인을 "허용 된 보낸 사람 도메인" 목록에 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="478c6-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![스팸 구성 설정의 허용 목록 섹션 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
