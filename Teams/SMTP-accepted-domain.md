---
title: Exchange Online에서 허용 된 보낸 사람 도메인으로 팀 SMTP 도메인 추가
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: b0efec3be7bbd9cf14ee7d0f1ca826ca76996795
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637747"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Exchange Online에서 Microsoft 팀 SMTP 도메인을 허용 된 보낸 사람 도메인으로 추가 
=============================================================================

관리 콘솔에서 Microsoft 365 그룹을 만들거나 Outlook을 사용 하는 경우 Exchange Online은 그룹에 추가 되는 팀 구성원의 알림을 보내는 데 사용 됩니다. 이러한 메시지는 사용자의 기본 도메인 SMTP FQDN을 나타내므로 테 넌 트에서 생성 됩니다.

![그룹에 추가 된 사용자를 보여 주는 메시지 머리글의 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

팀에서 Microsoft Exchange Online을 사용 하는 것은 물론, 추가 된 구성원에 게 알림을 보내는 경우입니다. SMTP 메시지의 도메인 FQDN에 대 한 차이점은 상업용/비즈니스 테 넌 트에 대 한 @email "teams.microsoft.com"이 고, 정부 테 넌 트의 경우 "@GCC-email.teams.com"이 고 스팸 필터링을 통해이를 찾아낼 수 있습니다.

![그룹에 추가 된 사용자를 보여 주는 메시지 머리글의 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

최상의 결과와 원활한 작업을 위해서는 Exchange Online 스팸 구성에서 Microsoft 팀 SMTP 도메인을 "허용 된 보낸 사람 도메인" 목록에 추가 하는 것이 좋습니다.

![스팸 구성 설정의 허용 목록 섹션 스크린샷](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
